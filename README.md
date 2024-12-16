# `String.prototype.splice`

## Status

Stage 0

## Authors

- [zion-off](https://github.com/zion-off)

## Overview

In JavaScript, `String.prototype` and `Array.prototype` share a good few
methods. However, `String.prototype` is missing `.splice()`, which happens to be
quite useful when working with arrays. Currently, the method can be simulated
when working with strings in a few different ways.

## Examples

Consider the following example, where I want add the character `c` to `myString`
at the second index.

```js
let myString = "abde";

// using `String.prototype.slice`
let firstHalf = myString.slice(0, 2);
let secondHalf = myString.slice(2);
myString = firstHalf + "c" + secondHalf;

// using `Array.prototype` methods
myString.split("").splice(2, 0, "c").join("");
```

Both of these methods get the job done, but are unnecessarily verbose. With a pure function such as `String.prototype.splice`, we can achieve the same effect far more easily.

```js
myString.splice(2, 0, "c");
```

## Specification

[Ecmarkup source](./spec.emu)  
[HTML](https://zion-off.github.io/proposal-string-splice/)

## Acknowledgements

Although a similar proposal exists [here](https://es.discourse.group/t/proposal-string-tospliced/2142), this propsal maintains consistency in nomenclature between `Array.prototype` and `String.prototype` methods.