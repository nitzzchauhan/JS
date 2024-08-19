<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>HTML Module 4</title>
    <style>
        body {
            background-color: black;
            color: white;
        }
        h1, h2, h3, h4, h5, h6 {
            color: white;
        }
    </style>
</head>
<body>

In JavaScript, `NaN` stands for "Not-a-Number." It's a special value that is returned when a mathematical operation or function that is expected to return a number fails to do so. Here are some common scenarios that result in `NaN`:

### 1. **Invalid Mathematical Operations**

When you perform an operation that doesn't produce a valid number, JavaScript returns `NaN`.

```javascript
let result = 0 / 0;
console.log(result); // NaN

let invalid = Math.sqrt(-1);
console.log(invalid); // NaN
```

### 2. **Attempting to Parse Non-Numeric Strings**

If you try to convert a non-numeric string into a number using functions like `parseInt`, `parseFloat`, or the `Number` constructor, you may get `NaN`.

```javascript
let number = parseInt("hello");
console.log(number); // NaN

let float = parseFloat("abc");
console.log(float); // NaN

let invalidNumber = Number("123abc");
console.log(invalidNumber); // NaN
```

### 3. **Operations with `undefined` or Non-Numeric Values**

If you perform arithmetic operations with `undefined` or non-numeric values, the result will be `NaN`.

```javascript
let value = undefined + 5;
console.log(value); // NaN

let obj = { x: 10 };
let result = obj.y * 2; // obj.y is undefined
console.log(result); // NaN
```

### 4. **Invalid Operations with `NaN`**

Any operation involving `NaN` will result in `NaN`.

```javascript
let value = NaN + 5;
console.log(value); // NaN

let multiply = NaN * 2;
console.log(multiply); // NaN
```

### 5. **Math Functions Returning `NaN`**

Certain `Math` functions can return `NaN` when given invalid input.

```javascript
let result = Math.log(-1); // Logarithm of a negative number
console.log(result); // NaN

let invalidRoot = Math.sqrt(-2); // Square root of a negative number
console.log(invalidRoot); // NaN
```

### Checking for `NaN`

To check if a value is `NaN`, you should use the `isNaN()` function or `Number.isNaN()` method:

```javascript
let value = 0 / 0;
console.log(isNaN(value)); // true
console.log(Number.isNaN(value)); // true
```

### Important Notes

- **`NaN` is the only value in JavaScript that is not equal to itself:**
  ```javascript
  console.log(NaN === NaN); // false
  ```
  This is why you should use `isNaN()` or `Number.isNaN()` to check for `NaN` instead of `===`.

- **`isNaN()` vs `Number.isNaN()`:**
  - `isNaN()` converts the value to a number before checking if it's `NaN`.
  - `Number.isNaN()` checks if the value is `NaN` without type conversion, which is more reliable.

If you encounter `NaN` in your code, it usually means that an operation didn't produce a valid number, and you'll need to debug the operation or function to understand why.