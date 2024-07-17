# NODEJS features you may not know about but should - 2024

## Table of Contents
1. [Introduction](#introduction)
2. [Fancy tricks](#fancy-tricks-that-i-always-forget-about)
    - [At gunpoint](#at-gunpoint)
    - [Operator wrestling](#operator-wrestling)
    - [The Flattening](#the-flattening)
3. [Node.js](#nodejs)
4. [ECMA Script 2024](#ecma-script-2024)


## Introduction
Time to time I come across some features of NodeJS that I didn't know about. I thought it would be a good idea to share some of them with you. Also I just have to add features that I'm always forgetting about.

## Fancy tricks (That I always forget about)

### At gunpoint
A better method that returns the element at the specified index in an array is using `.at()`. It's a simple way to access an element in an array without having to use bracket notation.

```javascript
const arr = [1, 2, 3, 4, 5];

console.log(arr.at(2)); // 3

console.log(arr.at(-1)); // 5 shortest way to get the last element
```

Using the `.at(-1)` syntax is a great way to access the last element in an array. This is much cleaner than using bracket notation with the length of the array like `arr[arr.length - 1]`.

### Operator wrestling

I guess most people already know about optional chaining, but I still forget about **Nullish coalescing operator**. This way you can use `??` instead of using `||` to check if a value is `null` or `undefined`.

```javascript
const count = 0;

console.log(count || 10); // 10
console.log(count ?? 10); // 0
```

This could be very important when you only want a value to be replaced if it's `null` or `undefined` and not if it's `0` or `false`.

### The Flattening
You can use `.flat()` to flatten an array of arrays. Which is already great, but I always forget that we can use `.flatMap()` too. This method first maps each element using a mapping function, then flattens the result into a new array. This is also a bit faster than `.map().flat()`.

```javascript
const arr = [[1, 2], [3, 4], [5, 6]];

console.log(arr.flat()); // [1, 2, 3, 4, 5, 6]
console.log(arr.flatMap([x, y] => [x, y, x + y])); // [1, 2, 3, 3, 4, 7, 5, 6, 11]
```

