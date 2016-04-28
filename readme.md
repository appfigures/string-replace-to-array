# String replace to array

Works just like `String.replace` but outputs an array instead of a string.

### Simple example

```
var replace = require('string-replace-to-array')
replace('Hello Amy', 'Amy', { name: 'Amy' })
// output: ['Hello ', { name: 'Amy' }]
```

### Full example

```
replace(
  'Hello Hermione Granger...',
  /(Hermione) (Granger)/g,
  function (fullName, firstName, lastName, offset, string) {
    return <Person firstName={ firstName } lastName={ lastName />
  }
)

// output: ['Hello ', <Person firstName="Hermione" lastName="Granger" />, ...]
```

## API

```
(string, regexp|substr, newValue|function) => array
```

The API is designed to work just like [String.replace](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/replace). The only differences are:

- The replacer (third parameter) doesn't have to be a string
- Returns an array instead of a string

## Why?

We built this for use with React, but it's very generic and doesn't depend on any environment.

For example, given this string

```
var content = 'Hello\nworld'
```

and this React markup:

```
<span>{ content }</span>
```

The output would be:

```
<span>Hello world</span>
```

Notice how the newline got stripped out.

With this method we can do:

```
<span>{ replace(content, '\n', </br>) }</span>
```

and the output will be:

```
<span>Hello</br>world</span>
```

Yay!

## Inspiration

Mainly inspired by this conversation: https://github.com/facebook/react/issues/3386

## Why not use [react-replace-string](https://github.com/iansinnott/react-string-replace)?

Because we needed the full API of `String.replace` and the parameters it passes the replace function.

