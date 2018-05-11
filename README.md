# [deep-props](https://github.com/jpcx/deep-props/blob/master/README.md).get

[![NPM](https://nodei.co/npm/deep-props.get.png)](https://nodei.co/npm/deep-props.get/)

Retrieves a nested property from a data source by iterating over a supplied path. Supports Objects, Arrays, Maps, Sets, WeakMaps, and JSON strings automatically. Supports the use of a custom extraction function to handle unsupported datasets.

See the [usage examples](#usage) for an overview of different types of data structures.

## Getting Started

The following installation, testing, and deployment instructions assume that deep-props.extract will be installed as a standalone module. For instructions on how to install and test all deep-props modules, please [refer to the main README](https://github.com/jpcx/deep-props/blob/master/README.md). Functionality of the module remains the same in both cases.

### Prerequisites

Node.JS version 6.0.0 or above.

### Installing

```console
npm install deep-props.get
```

### Testing

The following command will test the package for errors. It prints a large selection of examples to the console; scroll through its output if you want to learn more about the utility.

```console
npm test --prefix /path/to/node_modules/deep-props.get
```

### Deployment

```js
const get = require('deep-props.get')
```

<a name="usage"></a>

### Usage

***Note:*** For string paths using standard settings, '.' is considered the same as '[' and ']'. See [<code>Options</code>](https://github.com/jpcx/deep-props.get/blob/0.1.1/docs/global.md#~Options) for instructions for customizing this behavior.

**Nested Object Extraction**
```js
const nest = { foo: { bar: { baz: 'qux' } } }

// Both return 'qux'
get(nest, 'foo.bar.baz')
get(nest, [ 'foo', 'bar', 'baz' ])
```

**Nested Array Extraction**
```js
const nest = [ [ [ 'foo' ] ] ]

// Both return 'foo'
get(nest, '0.0.0')
get(nest, [ '0', '0', '0' ])
```

**Nested Map Extraction**
```js
const nest = new Map().set(
  'foo', new Map().set(
    'bar', new Map().set(
      'baz', new Map().set(
        'qux', 'quz'
      )
    )
  )
)

// Both return 'quz'
get(nest, 'foo.bar.baz.qux')
get(nest, [ 'foo', 'bar', 'baz', 'qux' ])
```

**Nested Map Extraction with Non-Primitive Keys**
```js
const keyA = { foo: 'bar' }
const keyB = { qux: 'quz' }
const keyC = { quux: 'quuz' }

const nest = new Map().set(
  keyA, new Map().set(
    keyB, new Map().set(
      keyC, 'thud'
    )
  )
)

// Returns 'thud'
// Note: this path must be an array of Object references.
get(nest, [ keyA, keyB, keyC ])
```

**Nested WeakMap Extraction**
```js
const keyA = { foo: 'bar' }
const keyB = { qux: 'quz' }
const keyC = { quux: 'quuz' }

const nest = new WeakMap().set(
  keyA, new WeakMap().set(
    keyB, new WeakMap().set(
      keyC, 'thud'
    )
  )
)

// Returns 'thud'
// Note: this path must be an array of Object references.
get(nest, [ keyA, keyB, keyC ])
```

**Nested Set Extraction**
```js
const setA = new Set()
const setB = new Set()
const setC = new Set()

const nest = new Set().add(
  setA.add(
    setB.add(
      setC.add('foo')
    )
  )
)

// All return 'foo'
// Note: values may be accessed via insertion order or actual references.
get(nest, '0.0.0.0')
get(nest, [ 0, 0, 0, 0 ])
get(nest, [ setA, setB, setC, 0 ])
```

**Extraction from JSON**
```js
const nest = JSON.stringify({ foo: { bar: { baz: 'qux' } } })

// returns 'qux'
get(nest, 'foo.bar.baz')
```

**Extraction from multi-typed nest**
```js
const wmKey = { baz: 'baz' }

const nest = {
  foo: [
    new Map().set(
      'bar', new WeakMap().set(
        wmKey, JSON.stringify({
          baz: [
            {
              qux: 'quz'
            }
          ]
        })
      )
    )
  ]
}


// returns 'quz'
// Array path is required here, because wmKey needs to be a reference
get(nest, ['foo', 0, 'bar', wmKey, 'baz', 0, 'qux'])
```

<a name="customizer_example"></a>

**Usage of a custom extraction function (see [<code>Options</code>](https://github.com/jpcx/deep-props.get/blob/0.1.1/docs/global.md#~Options) and [<code>GetCustomizer</code>](https://github.com/jpcx/deep-props.get/blob/0.1.1/docs/global.md#~GetCustomizer))**
```js
// Creation of a sample custom data structure which uses a 'retrieve' method for data access.
class NonNativeDataStructure {
  constructor(arr) {
    const values = [...arr]
    this.retrieve = i => values[i]
  }
}

// Addition of another data structure that, although native, requires custom extraction instructions
const testAB = new ArrayBuffer(16)
new Int16Array(testAB)[0] = 2

const nest = new NonNativeDataStructure([{ foo: { bar: testAB } }])

// returns undefined
get(nest, '0.foo.bar[0]')

// returns 2
get(nest, '0.foo.bar[0]', {
  getCustomizer: (target, key) => {
    if (target instanceof NonNativeDataStructure) {
      return target.retrieve(key)
    }
    if (target instanceof ArrayBuffer && target.byteLength === 16) {
      return new Int16Array(target)[key]
    }
  }
})
```

## Documentation

### See:
  + [API Docs](https://github.com/jpcx/deep-props.get/blob/0.1.1/docs/API.md)
  + [Global Docs](https://github.com/jpcx/deep-props.get/blob/0.1.1/docs/global.md)

### Module: get

Retrieves a nested property from a data source by iterating over a supplied path. Supports Objects, Arrays, Maps, Weakmaps, and JSON strings automatically. Supports the use of a custom extraction function to handle unsupported datasets.

##### Parameters:

| Name | Type | Attributes | Default | Description |
| --- | --- | --- | --- | --- |
| `host` | [deep-props.get~Host](https://github.com/jpcx/deep-props.get/blob/0.1.1/docs/global.md#~Host) |  |  | Container to search within. |
| `path` | [deep-props.get~Path](https://github.com/jpcx/deep-props.get/blob/0.1.1/docs/global.md#~Path) |  |  | Path to desired property. |
| `opt` | [deep-props.get~Options](https://github.com/jpcx/deep-props.get/blob/0.1.1/docs/global.md#~Options) | \<optional> | {} | Execution settings. |

Source:

*   [deep-props.get/index.js](https://github.com/jpcx/deep-props.get/blob/0.1.1/index.js), [line 282](https://github.com/jpcx/deep-props.get/blob/0.1.1/index.js#L282)

##### Returns:

Endpoint of path - the result of the search. Target is undefined if not found. If `opt.gen === true`, returns a generator that yields each search step.

Type

[deep-props.get~Target](https://github.com/jpcx/deep-props.get/blob/0.1.1/docs/global.md#~Target) | [deep-props.get~ResultGenerator](https://github.com/jpcx/deep-props.get/blob/0.1.1/docs/global.md#~ResultGenerator)

#

## Versioning

Versioned using [SemVer](http://semver.org/). For available versions, see the [Changelog](https://github.com/jpcx/deep-props.get/blob/0.1.1/CHANGELOG.md).

## Contribution

Please raise an issue if you find any. Pull requests are welcome!

## Author

  + **Justin Collier** - [jpcx](https://github.com/jpcx)

## License

This project is licensed under the MIT License - see the [LICENSE](https://github.com/jpcx/deep-props.get/blob/0.1.1/LICENSE) file for details
