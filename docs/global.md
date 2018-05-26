# [deep-props](https://github.com/jpcx/deep-props/blob/master/README.md).get

Source:

<<<<<<< HEAD
*   [deep-props.get/index.js](https://github.com/jpcx/deep-props.get/blob/0.1.5/index.js), [line 9](https://github.com/jpcx/deep-props.get/blob/0.1.5/index.js#L9)
=======
*   [deep-props.get/index.js](https://github.com/jpcx/deep-props.get/blob/0.1.4/index.js), [line 9](https://github.com/jpcx/deep-props.get/blob/0.1.4/index.js#L9)
>>>>>>> 2a7da931740770b8415775032c0464f50496eb7a

### Methods

<a name=".getFromKey"></a>
<<<<<<< HEAD
#### (static) getFromKey(target, key, opt) → \{[deep-props.get~Target](https://github.com/jpcx/deep-props.get/blob/0.1.5/docs/global.md#~Target)}
=======
#### (static) getFromKey(target, key, opt) → \{[deep-props.get~Target](https://github.com/jpcx/deep-props.get/blob/0.1.4/docs/global.md#~Target)}
>>>>>>> 2a7da931740770b8415775032c0464f50496eb7a

Gets a value from a Target behind a Key. Checks getCustomizer first, if it is provided.

##### Parameters:

| Name | Type | Description |
| --- | --- | --- |
<<<<<<< HEAD
| `target` | [deep-props.get~Target](https://github.com/jpcx/deep-props.get/blob/0.1.5/docs/global.md#~Target) | Target object. |
| `key` | [deep-props.get~Key](https://github.com/jpcx/deep-props.get/blob/0.1.5/docs/global.md#~Key) | Access key. |
| `opt` | [deep-props.get~Options](https://github.com/jpcx/deep-props.get/blob/0.1.5/docs/global.md#~Options) | Execution settings. |

Source:

*   [deep-props.get/index.js](https://github.com/jpcx/deep-props.get/blob/0.1.5/index.js), [line 216](https://github.com/jpcx/deep-props.get/blob/0.1.5/index.js#L216)
=======
| `target` | [deep-props.get~Target](https://github.com/jpcx/deep-props.get/blob/0.1.4/docs/global.md#~Target) | Target object. |
| `key` | [deep-props.get~Key](https://github.com/jpcx/deep-props.get/blob/0.1.4/docs/global.md#~Key) | Access key. |
| `opt` | [deep-props.get~Options](https://github.com/jpcx/deep-props.get/blob/0.1.4/docs/global.md#~Options) | Execution settings. |

Source:

*   [deep-props.get/index.js](https://github.com/jpcx/deep-props.get/blob/0.1.4/index.js), [line 216](https://github.com/jpcx/deep-props.get/blob/0.1.4/index.js#L216)
>>>>>>> 2a7da931740770b8415775032c0464f50496eb7a

##### Returns:

New target, final value, or undefined.

Type

<<<<<<< HEAD
[deep-props.get~Target](https://github.com/jpcx/deep-props.get/blob/0.1.5/docs/global.md#~Target)
=======
[deep-props.get~Target](https://github.com/jpcx/deep-props.get/blob/0.1.4/docs/global.md#~Target)
>>>>>>> 2a7da931740770b8415775032c0464f50496eb7a

##### Example

```js
// all return 'bar'
getFromKey({foo: 'bar'}, 'foo', {})
getFromKey(new Map([['foo', 'bar']]), 'foo', {})
getFromKey(new Set(['foo', 'bar']), 'bar', {})
```

<a name=".getFromMap"></a>
<<<<<<< HEAD
#### (static) getFromMap(target, key) → \{[deep-props.get~Target](https://github.com/jpcx/deep-props.get/blob/0.1.5/docs/global.md#~Target)}
=======
#### (static) getFromMap(target, key) → \{[deep-props.get~Target](https://github.com/jpcx/deep-props.get/blob/0.1.4/docs/global.md#~Target)}
>>>>>>> 2a7da931740770b8415775032c0464f50496eb7a

Gets a key from a map, if it exists. Looks for key as key first; if not found, looks for insertion order as key.

##### Parameters:

| Name | Type | Description |
| --- | --- | --- |
<<<<<<< HEAD
| `target` | [deep-props.get~Target](https://github.com/jpcx/deep-props.get/blob/0.1.5/docs/global.md#~Target) | Target of Key search. |
| `key` | [deep-props.get~Key](https://github.com/jpcx/deep-props.get/blob/0.1.5/docs/global.md#~Key) | Key to find in target. |

Source:

*   [deep-props.get/index.js](https://github.com/jpcx/deep-props.get/blob/0.1.5/index.js), [line 179](https://github.com/jpcx/deep-props.get/blob/0.1.5/index.js#L179)
=======
| `target` | [deep-props.get~Target](https://github.com/jpcx/deep-props.get/blob/0.1.4/docs/global.md#~Target) | Target of Key search. |
| `key` | [deep-props.get~Key](https://github.com/jpcx/deep-props.get/blob/0.1.4/docs/global.md#~Key) | Key to find in target. |

Source:

*   [deep-props.get/index.js](https://github.com/jpcx/deep-props.get/blob/0.1.4/index.js), [line 179](https://github.com/jpcx/deep-props.get/blob/0.1.4/index.js#L179)
>>>>>>> 2a7da931740770b8415775032c0464f50496eb7a

##### Returns:

New target from key or undefined if not found.

Type

<<<<<<< HEAD
[deep-props.get~Target](https://github.com/jpcx/deep-props.get/blob/0.1.5/docs/global.md#~Target)
=======
[deep-props.get~Target](https://github.com/jpcx/deep-props.get/blob/0.1.4/docs/global.md#~Target)
>>>>>>> 2a7da931740770b8415775032c0464f50496eb7a

##### Example

```js
// all return 'bar'
getFromMap(new Map([[ 'foo', 'bar' ]]), 'foo')
getFromMap(new Map([[ 'foo', 'bar' ]]), '0')
getFromMap(new Map([[ 'foo', 'bar' ]]), 0)
```

<a name=".getFromSet"></a>
<<<<<<< HEAD
#### (static) getFromSet(target, key) → \{[deep-props.get~Target](https://github.com/jpcx/deep-props.get/blob/0.1.5/docs/global.md#~Target)}
=======
#### (static) getFromSet(target, key) → \{[deep-props.get~Target](https://github.com/jpcx/deep-props.get/blob/0.1.4/docs/global.md#~Target)}
>>>>>>> 2a7da931740770b8415775032c0464f50496eb7a

Checks to see if a Set has a key. If so, returns the key. If not found, looks for insertion order as key.

##### Parameters:

| Name | Type | Description |
| --- | --- | --- |
<<<<<<< HEAD
| `target` | [deep-props.get~Target](https://github.com/jpcx/deep-props.get/blob/0.1.5/docs/global.md#~Target) | Target of Key search. |
| `key` | [deep-props.get~Key](https://github.com/jpcx/deep-props.get/blob/0.1.5/docs/global.md#~Key) | Key to find in target. |

Source:

*   [deep-props.get/index.js](https://github.com/jpcx/deep-props.get/blob/0.1.5/index.js), [line 197](https://github.com/jpcx/deep-props.get/blob/0.1.5/index.js#L197)
=======
| `target` | [deep-props.get~Target](https://github.com/jpcx/deep-props.get/blob/0.1.4/docs/global.md#~Target) | Target of Key search. |
| `key` | [deep-props.get~Key](https://github.com/jpcx/deep-props.get/blob/0.1.4/docs/global.md#~Key) | Key to find in target. |

Source:

*   [deep-props.get/index.js](https://github.com/jpcx/deep-props.get/blob/0.1.4/index.js), [line 197](https://github.com/jpcx/deep-props.get/blob/0.1.4/index.js#L197)
>>>>>>> 2a7da931740770b8415775032c0464f50496eb7a

##### Returns:

New target from key or undefined if not found.

Type

<<<<<<< HEAD
[deep-props.get~Target](https://github.com/jpcx/deep-props.get/blob/0.1.5/docs/global.md#~Target)
=======
[deep-props.get~Target](https://github.com/jpcx/deep-props.get/blob/0.1.4/docs/global.md#~Target)
>>>>>>> 2a7da931740770b8415775032c0464f50496eb7a

##### Example

```js
// all return 'foo'
getFromSet(new Set([ 'foo', 'bar' ]), 'foo')
getFromSet(new Set([ 'foo', 'bar' ]), '0')
getFromSet(new Set([ 'foo', 'bar' ]), 0)
```

<a name=".getFromString"></a>
<<<<<<< HEAD
#### (static) getFromString(target, key) → \{[deep-props.get~Target](https://github.com/jpcx/deep-props.get/blob/0.1.5/docs/global.md#~Target)}
=======
#### (static) getFromString(target, key) → \{[deep-props.get~Target](https://github.com/jpcx/deep-props.get/blob/0.1.4/docs/global.md#~Target)}
>>>>>>> 2a7da931740770b8415775032c0464f50496eb7a

Checks for String objects and properties attached to them. If not, checks for JSON and returns property from the extracted JSON object. If not JSON, returns the character at that index.

##### Parameters:

| Name | Type | Description |
| --- | --- | --- |
<<<<<<< HEAD
| `target` | [deep-props.get~Target](https://github.com/jpcx/deep-props.get/blob/0.1.5/docs/global.md#~Target) | Target of Key search. |
| `key` | [deep-props.get~Key](https://github.com/jpcx/deep-props.get/blob/0.1.5/docs/global.md#~Key) | Key to find in target. |

Source:

*   [deep-props.get/index.js](https://github.com/jpcx/deep-props.get/blob/0.1.5/index.js), [line 154](https://github.com/jpcx/deep-props.get/blob/0.1.5/index.js#L154)
=======
| `target` | [deep-props.get~Target](https://github.com/jpcx/deep-props.get/blob/0.1.4/docs/global.md#~Target) | Target of Key search. |
| `key` | [deep-props.get~Key](https://github.com/jpcx/deep-props.get/blob/0.1.4/docs/global.md#~Key) | Key to find in target. |

Source:

*   [deep-props.get/index.js](https://github.com/jpcx/deep-props.get/blob/0.1.4/index.js), [line 154](https://github.com/jpcx/deep-props.get/blob/0.1.4/index.js#L154)
>>>>>>> 2a7da931740770b8415775032c0464f50496eb7a

##### Returns:

New target from key or undefined if not found.

Type

<<<<<<< HEAD
[deep-props.get~Target](https://github.com/jpcx/deep-props.get/blob/0.1.5/docs/global.md#~Target)
=======
[deep-props.get~Target](https://github.com/jpcx/deep-props.get/blob/0.1.4/docs/global.md#~Target)
>>>>>>> 2a7da931740770b8415775032c0464f50496eb7a

##### Examples

```js
// returns 'bar'
getFromString(JSON.stringify({ foo: 'bar' }), 'foo')
```

```js
// returns 'c'
getFromString('abc', '2')
```

```js
// returns 'bar'
let strObj = new String('abc')
strObj.foo = 'bar'
getFromString(strObj, 'foo')
```

```js
// returns 'c'
let strObj = new String('abc')
strObj.foo = 'bar'
getFromString(strObj, '2')
```

<a name=".search"></a>
<<<<<<< HEAD
#### (generator, static) search(host, path, opt) → \{[deep-props.get~Target](https://github.com/jpcx/deep-props.get/blob/0.1.5/docs/global.md#~Target)}
=======
#### (generator, static) search(host, path, opt) → \{[deep-props.get~Target](https://github.com/jpcx/deep-props.get/blob/0.1.4/docs/global.md#~Target)}
>>>>>>> 2a7da931740770b8415775032c0464f50496eb7a

Iterates along the supplied path and shifts a reference point along the way.

##### Parameters:

| Name | Type | Description |
| --- | --- | --- |
<<<<<<< HEAD
| `host` | [deep-props.get~Host](https://github.com/jpcx/deep-props.get/blob/0.1.5/docs/global.md#~Host) | Base container dataset to search within. |
| `path` | [deep-props.get~Path](https://github.com/jpcx/deep-props.get/blob/0.1.5/docs/global.md#~Path) | Path to desired property. |
| `opt` | [deep-props.get~Options](https://github.com/jpcx/deep-props.get/blob/0.1.5/docs/global.md#~Options) | Execution settings. |

Source:

*   [deep-props.get/index.js](https://github.com/jpcx/deep-props.get/blob/0.1.5/index.js), [line 263](https://github.com/jpcx/deep-props.get/blob/0.1.5/index.js#L263)
=======
| `host` | [deep-props.get~Host](https://github.com/jpcx/deep-props.get/blob/0.1.4/docs/global.md#~Host) | Base container dataset to search within. |
| `path` | [deep-props.get~Path](https://github.com/jpcx/deep-props.get/blob/0.1.4/docs/global.md#~Path) | Path to desired property. |
| `opt` | [deep-props.get~Options](https://github.com/jpcx/deep-props.get/blob/0.1.4/docs/global.md#~Options) | Execution settings. |

Source:

*   [deep-props.get/index.js](https://github.com/jpcx/deep-props.get/blob/0.1.4/index.js), [line 263](https://github.com/jpcx/deep-props.get/blob/0.1.4/index.js#L263)
>>>>>>> 2a7da931740770b8415775032c0464f50496eb7a

##### Returns:

Returns undefined if search has finished executing or if the desired value has not been found.

Type

undefined

##### Yields:

Data retrieved at each level of execution; value of Target before reassignment.

Type

<<<<<<< HEAD
[deep-props.get~Target](https://github.com/jpcx/deep-props.get/blob/0.1.5/docs/global.md#~Target)
=======
[deep-props.get~Target](https://github.com/jpcx/deep-props.get/blob/0.1.4/docs/global.md#~Target)
>>>>>>> 2a7da931740770b8415775032c0464f50496eb7a

##### Example

```js
const nest = { foo: { bar: 'baz' } }

// returns generator
const query = search(nest, [ 'foo', 'bar' ], {})

// yields { value: { bar: 'baz' }, done: false }
query.next()

// yields { value: 'baz', done: true }
query.next()

// returns { value: undefined, done: true }
query.next()
```

### Type Definitions

<a name="~Container"></a>
#### Container

Container object used as a target for child property extraction.

##### Type:

<<<<<<< HEAD
*   Object | Array | Map | WeakMap | Set | WeakSet | [deep-props.get~Custom](https://github.com/jpcx/deep-props.get/blob/0.1.5/docs/global.md#~Custom)

Source:

*   [deep-props.get/index.js](https://github.com/jpcx/deep-props.get/blob/0.1.5/index.js), [line 34](https://github.com/jpcx/deep-props.get/blob/0.1.5/index.js#L34)
=======
*   Object | Array | Map | WeakMap | Set | WeakSet | [deep-props.get~Custom](https://github.com/jpcx/deep-props.get/blob/0.1.4/docs/global.md#~Custom)

Source:

*   [deep-props.get/index.js](https://github.com/jpcx/deep-props.get/blob/0.1.4/index.js), [line 34](https://github.com/jpcx/deep-props.get/blob/0.1.4/index.js#L34)
>>>>>>> 2a7da931740770b8415775032c0464f50496eb7a

<a name="~Custom"></a>
#### Custom

Custom dataset for use as a [Container](#~Container). May be accessed via valid customizer functions.

##### Type:

*   \*

Source:

<<<<<<< HEAD
*   [deep-props.get/index.js](https://github.com/jpcx/deep-props.get/blob/0.1.5/index.js), [line 11](https://github.com/jpcx/deep-props.get/blob/0.1.5/index.js#L11)
=======
*   [deep-props.get/index.js](https://github.com/jpcx/deep-props.get/blob/0.1.4/index.js), [line 11](https://github.com/jpcx/deep-props.get/blob/0.1.4/index.js#L11)
>>>>>>> 2a7da931740770b8415775032c0464f50496eb7a

##### Example

```js
(() => {
  class CustomDataStructure {
    constructor(array) {
      this.get = i => array[i]
      this.getValues = () => array
      this.push = x => array.push(x)
    }
  }
  return new CustomDataStructure([ 'foo', 'bar' ])
})()
```

<a name="~GetCustomizer"></a>
<<<<<<< HEAD
#### GetCustomizer(target, key) → \{[deep-props.get~Target](https://github.com/jpcx/deep-props.get/blob/0.1.5/docs/global.md#~Target)}
=======
#### GetCustomizer(target, key) → \{[deep-props.get~Target](https://github.com/jpcx/deep-props.get/blob/0.1.4/docs/global.md#~Target)}
>>>>>>> 2a7da931740770b8415775032c0464f50496eb7a

Function used for custom handling of entry into next level of the dataset.

*   Allows for extraction from container objects that are not directly supported.
*   Returns new value of Target based on key.
*   Returns undefined if Target is not compatible with the filter.

##### Parameters:

| Name | Type | Description |
| --- | --- | --- |
<<<<<<< HEAD
| `target` | [deep-props.get~Target](https://github.com/jpcx/deep-props.get/blob/0.1.5/docs/global.md#~Target) | Current data being analyzed |
| `key` | [deep-props.get~Key](https://github.com/jpcx/deep-props.get/blob/0.1.5/docs/global.md#~Key) | Next key along the path |

Source:

*   [deep-props.get/index.js](https://github.com/jpcx/deep-props.get/blob/0.1.5/index.js), [line 69](https://github.com/jpcx/deep-props.get/blob/0.1.5/index.js#L69)
=======
| `target` | [deep-props.get~Target](https://github.com/jpcx/deep-props.get/blob/0.1.4/docs/global.md#~Target) | Current data being analyzed |
| `key` | [deep-props.get~Key](https://github.com/jpcx/deep-props.get/blob/0.1.4/docs/global.md#~Key) | Next key along the path |

Source:

*   [deep-props.get/index.js](https://github.com/jpcx/deep-props.get/blob/0.1.4/index.js), [line 69](https://github.com/jpcx/deep-props.get/blob/0.1.4/index.js#L69)
>>>>>>> 2a7da931740770b8415775032c0464f50496eb7a

##### Returns:

Value to pass along to the search function as the next Target. If undefined, will fall back on using standard extraction methods to find the next Target.

Type

<<<<<<< HEAD
[deep-props.get~Target](https://github.com/jpcx/deep-props.get/blob/0.1.5/docs/global.md#~Target)
=======
[deep-props.get~Target](https://github.com/jpcx/deep-props.get/blob/0.1.4/docs/global.md#~Target)
>>>>>>> 2a7da931740770b8415775032c0464f50496eb7a

##### Example

```js
(target, key) => {
  if (target instanceof ArrayBuffer && target.byteLength === 16) {
    return new Int16Array(target)[key]
  }
}
```

<a name="~Host"></a>
#### Host

A non-primitive [Container](#~Container) which represents the root of a given path.

##### Type:

<<<<<<< HEAD
*   [deep-props.get~Container](https://github.com/jpcx/deep-props.get/blob/0.1.5/docs/global.md#~Container)

Source:

*   [deep-props.get/index.js](https://github.com/jpcx/deep-props.get/blob/0.1.5/index.js), [line 40](https://github.com/jpcx/deep-props.get/blob/0.1.5/index.js#L40)
=======
*   [deep-props.get~Container](https://github.com/jpcx/deep-props.get/blob/0.1.4/docs/global.md#~Container)

Source:

*   [deep-props.get/index.js](https://github.com/jpcx/deep-props.get/blob/0.1.4/index.js), [line 40](https://github.com/jpcx/deep-props.get/blob/0.1.4/index.js#L40)
>>>>>>> 2a7da931740770b8415775032c0464f50496eb7a

<a name="~Key"></a>
#### Key

Key used for accessing a child property within a container. When its value is `'__proto__'`, it is used as a stand-in for `Object.getPrototypeOf()`.

##### Type:

<<<<<<< HEAD
*   string | [deep-props.get~Container](https://github.com/jpcx/deep-props.get/blob/0.1.5/docs/global.md#~Container)

Source:

*   [deep-props.get/index.js](https://github.com/jpcx/deep-props.get/blob/0.1.5/index.js), [line 28](https://github.com/jpcx/deep-props.get/blob/0.1.5/index.js#L28)
=======
*   string | [deep-props.get~Container](https://github.com/jpcx/deep-props.get/blob/0.1.4/docs/global.md#~Container)

Source:

*   [deep-props.get/index.js](https://github.com/jpcx/deep-props.get/blob/0.1.4/index.js), [line 28](https://github.com/jpcx/deep-props.get/blob/0.1.4/index.js#L28)
>>>>>>> 2a7da931740770b8415775032c0464f50496eb7a

<a name="~Options"></a>
#### Options

Settings for customizing behaviour.

##### Type:

*   Object

##### Properties:

| Name | Type | Attributes | Description |
| --- | --- | --- | --- |
| `gen` | Boolean | \<optional> | If true, module returns a generator that yields each search step and returns the final value. |
<<<<<<< HEAD
| `getCustomizer` | [deep-props.get~GetCustomizer](https://github.com/jpcx/deep-props.get/blob/0.1.5/docs/global.md#~GetCustomizer) | \<optional> | Allows for custom extraction. |
=======
| `getCustomizer` | [deep-props.get~GetCustomizer](https://github.com/jpcx/deep-props.get/blob/0.1.4/docs/global.md#~GetCustomizer) | \<optional> | Allows for custom extraction. |
>>>>>>> 2a7da931740770b8415775032c0464f50496eb7a
| `match` | RegExp | \<optional> | Regular expression used for custom key extraction from supplied path string. If supplied, it is used as the only argument for `path.match()`, which should return an array of key names. |

Source:

<<<<<<< HEAD
*   [deep-props.get/index.js](https://github.com/jpcx/deep-props.get/blob/0.1.5/index.js), [line 89](https://github.com/jpcx/deep-props.get/blob/0.1.5/index.js#L89)
=======
*   [deep-props.get/index.js](https://github.com/jpcx/deep-props.get/blob/0.1.4/index.js), [line 89](https://github.com/jpcx/deep-props.get/blob/0.1.4/index.js#L89)
>>>>>>> 2a7da931740770b8415775032c0464f50496eb7a

##### Example

```js
{
  gen: true,
  getCustomizer: (target, key) => {
    if (target instanceof ArrayBuffer && target.byteLength === 16) {
      return new Int16Array(target)[key]
    }
  },
  match: /[^/]+/g
}
```

<a name="~Path"></a>
#### Path

Instructions that specify which keys should be accessed at each level of the dataset.

*   A nested array `'arr'` with property `arr[0][0] === 'foo'` should be represented as `[0, 0]` or `'[0][0]'`, (or `'0.0'`, etc.) in order to retrieve `'foo'`.
*   A nested object `'nest'` with property `nest.foo.bar === 'baz'` should be represented as either `['foo', 'bar']` or `'foo.bar'` (or `'foo[bar]'`, etc.) in order to retrieve `'baz'`.
*   String paths will be converted to an array of keys based on matches of the following regex: `/[^.[\]]+/g`.
    *   In other words, anything between periods or brackets will be interpreted as keys.
    *   Paths containing any keys that are references (such as WeakMap keys) must be passed as an array, such as `['foo', 'bar', weakMapKey]`
    *   Paths containing any keys with periods or brackets must also be passed as an array, such as `['foo.bar', 'baz[qux]']` (unless a custom match regex is supplied).

##### Type:

<<<<<<< HEAD
*   Array.<[deep-props.get~Key](https://github.com/jpcx/deep-props.get/blob/0.1.5/docs/global.md#~Key)> | string

Source:

*   [deep-props.get/index.js](https://github.com/jpcx/deep-props.get/blob/0.1.5/index.js), [line 108](https://github.com/jpcx/deep-props.get/blob/0.1.5/index.js#L108)
=======
*   Array.<[deep-props.get~Key](https://github.com/jpcx/deep-props.get/blob/0.1.4/docs/global.md#~Key)> | string

Source:

*   [deep-props.get/index.js](https://github.com/jpcx/deep-props.get/blob/0.1.4/index.js), [line 108](https://github.com/jpcx/deep-props.get/blob/0.1.4/index.js#L108)
>>>>>>> 2a7da931740770b8415775032c0464f50496eb7a

##### Examples

```js
[ 'foo', 'bar', 'baz' ]
```

```js
'foo.bar.baz'
```

```js
'foo[0][0]'
```

<a name="~ResultGenerator"></a>
#### ResultGenerator

Generator object which yields stepwise operation results.

##### Type:

*   Object

Source:

<<<<<<< HEAD
*   [deep-props.get/index.js](https://github.com/jpcx/deep-props.get/blob/0.1.5/index.js), [line 46](https://github.com/jpcx/deep-props.get/blob/0.1.5/index.js#L46)
=======
*   [deep-props.get/index.js](https://github.com/jpcx/deep-props.get/blob/0.1.4/index.js), [line 46](https://github.com/jpcx/deep-props.get/blob/0.1.4/index.js#L46)
>>>>>>> 2a7da931740770b8415775032c0464f50496eb7a

<a name="~Target"></a>
#### Target

Current reference to a given level of the path; parent to the next key along the path.

*   For the host `{ foo: { bar: 'baz' } }` and a path `['foo', 'bar']`, the Target value will change during the search as follows:
    *   `{ bar: 'baz' }`
    *   `'baz'`
*   Unless Target is a primitive type, or has been extracted from within a primitive type (such as a JSON string), Target will be a reference to the host object.
    *   In this case, if any of its nested parents are mutable, modifications of a mutable object returned or yielded by get will result in changes to the host object.

##### Type:

<<<<<<< HEAD
*   [deep-props.get~Container](https://github.com/jpcx/deep-props.get/blob/0.1.5/docs/global.md#~Container) | string | undefined

Source:

*   [deep-props.get/index.js](https://github.com/jpcx/deep-props.get/blob/0.1.5/index.js), [line 52](https://github.com/jpcx/deep-props.get/blob/0.1.5/index.js#L52)

<hr>

## [Home](https://github.com/jpcx/deep-props.get/blob/0.1.5/README.md)
=======
*   [deep-props.get~Container](https://github.com/jpcx/deep-props.get/blob/0.1.4/docs/global.md#~Container) | string | undefined

Source:

*   [deep-props.get/index.js](https://github.com/jpcx/deep-props.get/blob/0.1.4/index.js), [line 52](https://github.com/jpcx/deep-props.get/blob/0.1.4/index.js#L52)

<hr>

## [Home](https://github.com/jpcx/deep-props.get/blob/0.1.4/README.md)
>>>>>>> 2a7da931740770b8415775032c0464f50496eb7a
