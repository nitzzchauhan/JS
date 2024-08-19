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


JavaScript provides a variety of methods to work with arrays. Below is a comprehensive list of array methods available in JavaScript:

### 1. **Array Creation**
- **`Array.isArray(array)`**: Checks if a value is an array.
- **`Array.from(arrayLike, mapFn?, thisArg?)`**: Creates a new array instance from an array-like or iterable object.
- **`Array.of(element0, element1, ..., elementN)`**: Creates a new array instance with a variable number of elements.

### 2. **Adding and Removing Elements**
- **`push(element1, ..., elementN)`**: Adds one or more elements to the end of an array and returns the new length.
- **`pop()`**: Removes the last element from an array and returns that element.
- **`unshift(element1, ..., elementN)`**: Adds one or more elements to the beginning of an array and returns the new length.
- **`shift()`**: Removes the first element from an array and returns that element.
- **`splice(start, deleteCount, item1, item2, ..., itemN)`**: Changes the content of an array by removing or replacing existing elements and/or adding new elements.
- **`concat(array2, ..., arrayN)`**: Merges two or more arrays and returns a new array.

### 3. **Accessing and Iterating**
- **`indexOf(searchElement, fromIndex)`**: Returns the first index at which a given element can be found, or -1 if it is not present.
- **`lastIndexOf(searchElement, fromIndex)`**: Returns the last index at which a given element can be found, or -1 if it is not present.
- **`find(callback(element, index, array), thisArg)`**: Returns the value of the first element that satisfies the provided testing function.
- **`findIndex(callback(element, index, array), thisArg)`**: Returns the index of the first element that satisfies the provided testing function.
- **`forEach(callback(currentValue, index, array), thisArg)`**: Executes a provided function once for each array element.
- **`every(callback(element, index, array), thisArg)`**: Tests whether all elements pass the test implemented by the provided function.
- **`some(callback(element, index, array), thisArg)`**: Tests whether at least one element passes the test implemented by the provided function.
- **`includes(searchElement, fromIndex)`**: Determines whether an array includes a certain element.
- **`keys()`**: Returns a new Array Iterator object that contains the keys for each index in the array.
- **`values()`**: Returns a new Array Iterator object that contains the values for each index in the array.
- **`entries()`**: Returns a new Array Iterator object that contains key/value pairs for each index in the array.

### 4. **Transforming Arrays**
- **`map(callback(currentValue, index, array), thisArg)`**: Creates a new array with the results of calling a provided function on every element.
- **`filter(callback(element, index, array), thisArg)`**: Creates a new array with all elements that pass the test implemented by the provided function.
- **`reduce(callback(accumulator, currentValue, currentIndex, array), initialValue)`**: Applies a function against an accumulator and each element to reduce it to a single value.
- **`reduceRight(callback(accumulator, currentValue, currentIndex, array), initialValue)`**: Applies a function against an accumulator and each element (from right to left) to reduce it to a single value.
- **`flat(depth)`**: Creates a new array with all sub-array elements concatenated into it recursively up to the specified depth.
- **`flatMap(callback(element, index, array), thisArg)`**: Maps each element using a mapping function, then flattens the result into a new array.
- **`sort(compareFunction)`**: Sorts the elements of an array in place and returns the sorted array.
- **`reverse()`**: Reverses the order of the elements of an array in place and returns the reversed array.
- **`join(separator)`**: Joins all elements into a string and returns this string.
- **`slice(begin, end)`**: Returns a shallow copy of a portion of an array into a new array object.
- **`fill(value, start, end)`**: Fills all the elements with a static value.
- **`copyWithin(target, start, end)`**: Shallow copies part of an array to another location in the same array.

### 5. **Finding and Filtering**
- **`filter(callback(element, index, array), thisArg)`**: Creates a new array with all elements that pass the test implemented by the provided function.
- **`find(callback(element, index, array), thisArg)`**: Returns the value of the first element that satisfies the provided testing function.
- **`findIndex(callback(element, index, array), thisArg)`**: Returns the index of the first element that satisfies the provided testing function.

### 6. **Checking Array Properties**
- **`Array.isArray(array)`**: Determines whether the passed value is an array.

### 7. **Other Methods**
- **`toString()`**: Returns a string representing the elements of the array.
- **`toLocaleString()`**: Returns a localized string representing the array and its elements.
- **`Array.prototype[@@iterator]()`**: Returns a new Array Iterator object that contains the values for each index in the array.

This list covers most of the commonly used array methods in JavaScript. Each method serves specific use cases, making arrays a powerful and flexible data structure in JavaScript.





Let's dive into each of the array methods listed above with detailed explanations and code examples.

### 1. **Array Creation**

- **`Array.isArray(value)`**
  - **Description**: Checks if the passed value is an array.
  - **Example**:
    ```javascript
    console.log(Array.isArray([1, 2, 3])); // true
    console.log(Array.isArray('Hello'));   // false
    ```

- **`Array.from(arrayLike, mapFn?, thisArg?)`**
  - **Description**: Creates a new array instance from an array-like or iterable object.
  - **Example**:
    ```javascript
    let str = "Hello";
    let arr = Array.from(str);
    console.log(arr); // ['H', 'e', 'l', 'l', 'o']
    ```

- **`Array.of(element0, element1, ..., elementN)`**
  - **Description**: Creates a new array instance with a variable number of elements.
  - **Example**:
    ```javascript
    let arr = Array.of(1, 2, 3);
    console.log(arr); // [1, 2, 3]
    ```

### 2. **Adding and Removing Elements**

- **`push(element1, ..., elementN)`**
  - **Description**: Adds one or more elements to the end of an array and returns the new length.
  - **Example**:
    ```javascript
    let arr = [1, 2, 3];
    arr.push(4, 5);
    console.log(arr); // [1, 2, 3, 4, 5]
    ```

- **`pop()`**
  - **Description**: Removes the last element from an array and returns that element.
  - **Example**:
    ```javascript
    let arr = [1, 2, 3];
    let last = arr.pop();
    console.log(last); // 3
    console.log(arr);  // [1, 2]
    ```

- **`unshift(element1, ..., elementN)`**
  - **Description**: Adds one or more elements to the beginning of an array and returns the new length.
  - **Example**:
    ```javascript
    let arr = [2, 3];
    arr.unshift(0, 1);
    console.log(arr); // [0, 1, 2, 3]
    ```

- **`shift()`**
  - **Description**: Removes the first element from an array and returns that element.
  - **Example**:
    ```javascript
    let arr = [1, 2, 3];
    let first = arr.shift();
    console.log(first); // 1
    console.log(arr);   // [2, 3]
    ```

- **`splice(start, deleteCount, item1, item2, ..., itemN)`**
  - **Description**: Changes the contents of an array by removing or replacing existing elements and/or adding new elements.
  - **Example**:
    ```javascript
    let arr = [1, 2, 3, 4];
    arr.splice(1, 2, 'a', 'b');
    console.log(arr); // [1, 'a', 'b', 4]
    ```

- **`concat(array2, ..., arrayN)`**
  - **Description**: Merges two or more arrays and returns a new array.
  - **Example**:
    ```javascript
    let arr1 = [1, 2];
    let arr2 = [3, 4];
    let result = arr1.concat(arr2);
    console.log(result); // [1, 2, 3, 4]
    ```

### 3. **Accessing and Iterating**

- **`indexOf(searchElement, fromIndex)`**
  - **Description**: Returns the first index at which a given element can be found, or -1 if it is not present.
  - **Example**:
    ```javascript
    let arr = [1, 2, 3, 2];
    console.log(arr.indexOf(2)); // 1
    console.log(arr.indexOf(4)); // -1
    ```

- **`lastIndexOf(searchElement, fromIndex)`**
  - **Description**: Returns the last index at which a given element can be found, or -1 if it is not present.
  - **Example**:
    ```javascript
    let arr = [1, 2, 3, 2];
    console.log(arr.lastIndexOf(2)); // 3
    ```

- **`find(callback(element, index, array), thisArg)`**
  - **Description**: Returns the value of the first element that satisfies the provided testing function.
  - **Example**:
    ```javascript
    let arr = [1, 2, 3, 4];
    let found = arr.find(element => element > 2);
    console.log(found); // 3
    ```

- **`findIndex(callback(element, index, array), thisArg)`**
  - **Description**: Returns the index of the first element that satisfies the provided testing function.
  - **Example**:
    ```javascript
    let arr = [1, 2, 3, 4];
    let index = arr.findIndex(element => element > 2);
    console.log(index); // 2
    ```

- **`forEach(callback(currentValue, index, array), thisArg)`**
  - **Description**: Executes a provided function once for each array element.
  - **Example**:
    ```javascript
    let arr = [1, 2, 3];
    arr.forEach(element => console.log(element * 2)); // 2, 4, 6
    ```

- **`every(callback(element, index, array), thisArg)`**
  - **Description**: Tests whether all elements pass the test implemented by the provided function.
  - **Example**:
    ```javascript
    let arr = [1, 2, 3];
    let allPositive = arr.every(element => element > 0);
    console.log(allPositive); // true
    ```

- **`some(callback(element, index, array), thisArg)`**
  - **Description**: Tests whether at least one element passes the test implemented by the provided function.
  - **Example**:
    ```javascript
    let arr = [1, -2, 3];
    let hasNegative = arr.some(element => element < 0);
    console.log(hasNegative); // true
    ```

- **`includes(searchElement, fromIndex)`**
  - **Description**: Determines whether an array includes a certain element.
  - **Example**:
    ```javascript
    let arr = [1, 2, 3];
    console.log(arr.includes(2)); // true
    console.log(arr.includes(4)); // false
    ```

- **`keys()`**
  - **Description**: Returns a new Array Iterator object that contains the keys for each index in the array.
  - **Example**:
    ```javascript
    let arr = ['a', 'b', 'c'];
    let iterator = arr.keys();
    for (let key of iterator) {
      console.log(key); // 0, 1, 2
    }
    ```

- **`values()`**
  - **Description**: Returns a new Array Iterator object that contains the values for each index in the array.
  - **Example**:
    ```javascript
    let arr = ['a', 'b', 'c'];
    let iterator = arr.values();
    for (let value of iterator) {
      console.log(value); // 'a', 'b', 'c'
    }
    ```

- **`entries()`**
  - **Description**: Returns a new Array Iterator object that contains key/value pairs for each index in the array.
  - **Example**:
    ```javascript
    let arr = ['a', 'b', 'c'];
    let iterator = arr.entries();
    for (let [index, value] of iterator) {
      console.log(index, value); // 0 'a', 1 'b', 2 'c'
    }
    ```

### 4. **Transforming Arrays**

- **`map(callback(currentValue, index, array), thisArg)`**
  - **Description**: Creates a new array with the results of calling a provided function on every element.
  - **Example**:
    ```javascript
    let arr = [1, 2, 3];
    let squared = arr.map(x => x * x);
    console.log(squared); // [1, 4, 9]
    ```

- **`filter(callback(element, index, array), thisArg)`**
  - **Description**: Creates a new array with all elements that pass the test implemented by the provided function.
  - **Example**:
    ```javascript
    let arr = [1, 2, 3, 4, 5];
    let filtered = arr.filter(x => x > 2);
    console.log(filtered); // [3, 4, 5]
    ```

- **`reduce(callback(accumulator, currentValue, currentIndex, array), initialValue)`**
  - **Description**: Applies a function against an accumulator and each element to reduce it to a single value.
  - **Example**:
    ```javascript
    let arr = [1, 2, 3, 4];
    let sum = arr.reduce((acc, curr) => acc + curr

, 0);
    console.log(sum); // 10
    ```

Continuing with the array methods:

### 4. **Transforming Arrays (Continued)**

- **`reduceRight(callback(accumulator, currentValue, currentIndex, array), initialValue)`**
  - **Description**: Applies a function against an accumulator and each element of the array (from right to left) to reduce it to a single value.
  - **Example**:
    ```javascript
    let arr = [1, 2, 3, 4];
    let sum = arr.reduceRight((acc, curr) => acc + curr, 0);
    console.log(sum); // 10
    ```

- **`flat(depth)`**
  - **Description**: Creates a new array with all sub-array elements concatenated into it recursively up to the specified depth.
  - **Example**:
    ```javascript
    let arr = [1, 2, [3, 4, [5, 6]]];
    let flatArr = arr.flat(2);
    console.log(flatArr); // [1, 2, 3, 4, 5, 6]
    ```

- **`flatMap(callback(element, index, array), thisArg)`**
  - **Description**: First maps each element using a mapping function, then flattens the result into a new array. This is identical to a `map()` followed by a `flat()` of depth 1.
  - **Example**:
    ```javascript
    let arr = [1, 2, 3];
    let flatMapArr = arr.flatMap(x => [x, x * 2]);
    console.log(flatMapArr); // [1, 2, 2, 4, 3, 6]
    ```

### 5. **Reordering Elements**

- **`reverse()`**
  - **Description**: Reverses the order of the elements in an array in place.
  - **Example**:
    ```javascript
    let arr = [1, 2, 3];
    arr.reverse();
    console.log(arr); // [3, 2, 1]
    ```

- **`sort(compareFunction)`**
  - **Description**: Sorts the elements of an array in place and returns the sorted array. The sorting is not necessarily stable.
  - **Example**:
    ```javascript
    let arr = [3, 1, 4, 2];
    arr.sort((a, b) => a - b);
    console.log(arr); // [1, 2, 3, 4]
    ```

- **`copyWithin(target, start, end)`**
  - **Description**: Copies part of an array to another location in the same array without modifying its length.
  - **Example**:
    ```javascript
    let arr = [1, 2, 3, 4, 5];
    arr.copyWithin(0, 3);
    console.log(arr); // [4, 5, 3, 4, 5]
    ```

- **`fill(value, start, end)`**
  - **Description**: Fills all the elements of an array from a start index to an end index with a static value.
  - **Example**:
    ```javascript
    let arr = [1, 2, 3, 4];
    arr.fill(0, 1, 3);
    console.log(arr); // [1, 0, 0, 4]
    ```

### 6. **Combining and Slicing**

- **`slice(begin, end)`**
  - **Description**: Returns a shallow copy of a portion of an array into a new array object selected from `begin` to `end` (end not included).
  - **Example**:
    ```javascript
    let arr = [1, 2, 3, 4];
    let sliced = arr.slice(1, 3);
    console.log(sliced); // [2, 3]
    ```

- **`join(separator)`**
  - **Description**: Joins all elements of an array into a string and returns this string. You can specify a separator.
  - **Example**:
    ```javascript
    let arr = [1, 2, 3];
    let str = arr.join('-');
    console.log(str); // "1-2-3"
    ```

### 7. **Other Array Methods**

- **`toString()`**
  - **Description**: Returns a string representing the specified array and its elements.
  - **Example**:
    ```javascript
    let arr = [1, 2, 3];
    console.log(arr.toString()); // "1,2,3"
    ```

- **`toLocaleString(locales, options)`**
  - **Description**: Returns a string representing the elements of the array. The elements are converted to strings using their `toLocaleString()` methods.
  - **Example**:
    ```javascript
    let dateArr = [new Date(), new Date()];
    console.log(dateArr.toLocaleString('en-US')); // "8/19/2024, 1:00:00 PM, 8/19/2024, 1:00:00 PM"
    ```

- **`length`**
  - **Description**: The length property sets or returns the number of elements in an array.
  - **Example**:
    ```javascript
    let arr = [1, 2, 3];
    console.log(arr.length); // 3
    ```

### 8. **Typed Arrays**
(These are specialized array objects for handling raw binary data.)

- **`Int8Array`, `Uint8Array`, `Uint8ClampedArray`, `Int16Array`, `Uint16Array`, `Int32Array`, `Uint32Array`, `Float32Array`, `Float64Array`**
  - **Description**: Each of these represents a typed array of elements. For instance, `Int8Array` represents a signed 8-bit integer array.
  - **Example**:
    ```javascript
    let buffer = new ArrayBuffer(16);
    let int32View = new Int32Array(buffer);
    int32View[0] = 42;
    console.log(int32View[0]); // 42
    ```

### 9. **Array Methods with Prototypes**

- **`Array.prototype`**
  - **Description**: The `prototype` property allows you to add new methods or properties to the `Array` object.
  - **Example**:
    ```javascript
    Array.prototype.double = function() {
      return this.map(x => x * 2);
    };

    let arr = [1, 2, 3];
    console.log(arr.double()); // [2, 4, 6]
    ```

### 10. **Static Methods**

- **`Array.isArray(obj)`**
  - **Description**: Determines whether the passed value is an array.
  - **Example**:
    ```javascript
    console.log(Array.isArray([1, 2, 3])); // true
    console.log(Array.isArray('Hello'));   // false
    ```

### Summary

These methods allow you to manipulate and interact with arrays in JavaScript in a variety of ways. They cover the creation of arrays, adding and removing elements, accessing and iterating over arrays, transforming and reordering arrays, combining and slicing arrays, and using typed arrays for performance-critical applications.

If you need more specific examples or explanations for any of these methods, feel free to ask!