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

### Functions in JavaScript

#### 1. Function Declarations

**Definition**: Function declarations define a function with the specified parameters. They are hoisted to the top of their scope, meaning they can be called before they are defined in the code.

**Syntax**:
```javascript
function functionName(parameters) {
  // function body
  return value;
}
```

**Example**:
```javascript
function greet(name) {
  return `Hello, ${name}!`;
}

console.log(greet('Alice')); // Output: Hello, Alice!
```

#### 2. Hoisting

**Definition**: Hoisting is JavaScript's default behavior of moving declarations to the top of the current scope (to the top of the current script or the current function).

**Example**:
```javascript
console.log(sayHello()); // Output: Hello!

function sayHello() {
  return 'Hello!';
}
```

In the above example, the function `sayHello` is hoisted to the top, so it can be called before its declaration.

#### 3. Arguments

**Definition**: The `arguments` object is an array-like object accessible inside functions that contains the values of the arguments passed to that function.

**Example**:
```javascript
function sum() {
  let total = 0;
  for (let i = 0; i < arguments.length; i++) {
    total += arguments[i];
  }
  return total;
}

console.log(sum(1, 2, 3, 4)); // Output: 10
```

#### 4. The Rest Operator

**Definition**: The rest operator (`...`) allows a function to accept an indefinite number of arguments as an array.

**Example**:
```javascript
function sum(...numbers) {
  return numbers.reduce((total, num) => total + num, 0);
}

console.log(sum(1, 2, 3, 4)); // Output: 10
```

#### 5. Default Parameters

**Definition**: Default parameters allow named parameters to be initialized with default values if no value or `undefined` is passed.

**Example**:
```javascript
function greet(name = 'Guest') {
  return `Hello, ${name}!`;
}

console.log(greet()); // Output: Hello, Guest!
console.log(greet('Alice')); // Output: Hello, Alice!
```

#### 6. Getter and Setters

**Definition**: Getters and setters are methods that get and set the value of an object property.

**Example**:
```javascript
class Person {
  constructor(name) {
    this._name = name;
  }

  get name() {
    return this._name;
  }

  set name(value) {
    this._name = value;
  }
}

let person = new Person('Alice');
console.log(person.name); // Output: Alice
person.name = 'Bob';
console.log(person.name); // Output: Bob
```

#### 7. Try and Catch

**Definition**: The `try...catch` statement allows you to test a block of code for errors (try), and handle the error (catch).

**Example**:
```javascript
try {
  let result = riskyOperation();
  console.log(result);
} catch (error) {
  console.log('An error occurred:', error.message);
}

function riskyOperation() {
  throw new Error('Something went wrong!');
}
```

#### 8. Local vs. Global Scope

**Definition**: Variables declared within a function are in the local scope, while variables declared outside any function are in the global scope.

**Example**:
```javascript
let globalVar = 'Global';

function testScope() {
  let localVar = 'Local';
  console.log(globalVar); // Output: Global
  console.log(localVar); // Output: Local
}

testScope();
console.log(globalVar); // Output: Global
console.log(localVar); // Error: localVar is not defined
```

#### 9. `this` Keyword

**Definition**: The `this` keyword refers to the object it belongs to.

**Example**:
```javascript
let person = {
  name: 'Alice',
  greet: function() {
    console.log(`Hello, my name is ${this.name}`);
  }
};

person.greet(); // Output: Hello, my name is Alice

let anotherPerson = {
  name: 'Bob'
};

anotherPerson.greet = person.greet;
anotherPerson.greet(); // Output: Hello, my name is Bob
```

### Interview Questions and Solutions

**Question 1**: What is function hoisting in JavaScript?

**Solution**:
Function hoisting is the process where function declarations are moved to the top of their containing scope during the compilation phase. This means you can call functions before they appear in the code.

**Example**:
```javascript
console.log(sayHello()); // Output: Hello!

function sayHello() {
  return 'Hello!';
}
```

**Question 2**: How can you handle errors in JavaScript?

**Solution**:
Errors can be handled using the `try...catch` statement. The code that might throw an error is wrapped in a `try` block, and the error handling code is placed in a `catch` block.

**Example**:
```javascript
try {
  let result = riskyOperation();
  console.log(result);
} catch (error) {
  console.log('An error occurred:', error.message);
}

function riskyOperation() {
  throw new Error('Something went wrong!');
}
```

**Question 3**: Explain the difference between `let`, `var`, and `const`.

**Solution**:
- `var`: Function-scoped, can be re-declared and updated.
- `let`: Block-scoped, cannot be re-declared but can be updated.
- `const`: Block-scoped, cannot be