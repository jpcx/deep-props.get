# [deep-props](https://github.com/jpcx/deep-props/blob/0.2.0/README.md).get

[![NPM](https://nodei.co/npm/deep-props.get.png)](https://nodei.co/npm/deep-props.get/)

Retrieves a nested property from a data source by iterating over a supplied path. Supports Objects, Arrays, Maps, Weakmaps, and JSON strings automatically. Supports the use of a custom extraction function to handle unsupported datasets.

Any unsupported data structure may be accessed by supplying a customizer function. See [<code>this example</code>](#customizer_example).

## Getting Started

The following installation, testing, and deployment instructions assume that deep-props.extract will be installed as a standalone module. For instructions on how to install and test all deep-props modules, please [refer to the main README](https://github.com/jpcx/deep-props/blob/0.2.0/README.md). Functionality of the module remains the same in both cases.

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

### Usage

**Nested object extraction**
```js
const nest = { foo: { bar: { baz: 'qux' } } }

// returns 'qux'
get(nest, 'foo.bar.baz')
```

**Nested Map extraction**
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

// returns 'quz'
get(nest, 'foo.bar.baz.qux')
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
get(data, ['foo', 0, 'bar', wmKey, 'baz', 0, 'qux'])
```

<a name="customizer_example"></a>

**Usage of a custom extraction function (see [<code>Options</code>](https://github.com/jpcx/deep-props.get/blob/undefined/docs/global.md#~GetCustomizer))**
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

const nest = new NonNativeDataStructure[{ foo: { bar: testAB } }]

// returns undefined
get(nest, '0.foo.bar[0]')

// returns 2
get(nest, '0.foo.bar[0]', {
  customizer: (target, key) => {
    if (target instanceof NonNativeDataStructure) {
      return target.retrieve(next)
    }
    if (target instanceof ArrayBuffer && target.byteLength === 16) {
      return new Int16Array(target)[key]
    }
  }
})
```

## Documentation

### See:
* [API Docs](https://github.com/jpcx/deep-props.get/blob/0.1.0/docs/API.md)
* [Global Docs](https://github.com/jpcx/deep-props.get/blob/0.1.0/docs/global.md)

### Module: get

Retrieves a nested property from a data source by iterating over a supplied path. Supports Objects, Arrays, Maps, Weakmaps, and JSON strings automatically. Supports the use of a custom extraction function to handle unsupported datasets.

##### Parameters:

| Name | Type | Attributes | Default | Description |
| --- | --- | --- | --- | --- |
| `host` | [deep-props~Host](https://github.com/jpcx/deep-props/blob/0.1.0/docs/global.md#~Host) |  |  | Container to search within. |
| `path` | [deep-props.get~Path](https://github.com/jpcx/deep-props.get/blob/0.1.0/docs/global.md#~Path) |  |  | Path to desired property. |
| `opt` | [deep-props.get~Options](https://github.com/jpcx/deep-props.get/blob/0.1.0/docs/global.md#~Options) | \<optional> | {} | Execution settings. |

Source:

*   [deep-props.get/index.js](https://github.com/jpcx/deep-props.get/blob/0.1.0/index.js), [line 241](https://github.com/jpcx/deep-props.get/blob/0.1.0/index.js#L241)

##### Returns:

Endpoint of path - the result of the search. Target is undefined if not found. If `opt.gen === true`, returns a generator that yields each search step.

Type

[deep-props.get~Target](https://github.com/jpcx/deep-props.get/blob/0.1.0/docs/global.md#~Target) | [deep-props~ResultGenerator](https://github.com/jpcx/deep-props/blob/0.1.0/docs/global.md#~ResultGenerator)

#

## Versioning

Versioned using [SemVer](http://semver.org/). For available versions, see the [Changelog](https://github.com/jpcx/deep-props.get/blob/0.1.0/CHANGELOG.md).

## Contribution

Please raise an issue if you find any. Pull requests are welcome!

## Author

* **Justin Collier** - [jpcx](https://github.com/jpcx)

## License

This project is licensed under the MIT License - see the [LICENSE](https://github.com/jpcx/deep-props.get/blob/0.1.0/LICENSE) file for details
