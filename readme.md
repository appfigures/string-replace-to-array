# String replace to array

Works just like `String.replace` but outputs an array instead of a string.

## Differences from String.replace

- Accepts a replacer of any type, not just a string
- Always returns an array

## Inspiration

Mainly inspired by this conversation: https://github.com/facebook/react/issues/3386

## Why not use [react-replace-string](https://github.com/iansinnott/react-string-replace)?

Because we needed the full API of `String.replace` and the parameters it passes the replace function.

