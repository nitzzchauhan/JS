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

## JavaScript HTML BOM (Browser Object Model)

### HTML Browser Object Model (BOM)
The Browser Object Model (BOM) allows JavaScript to interact with the browser. It is a hierarchy of objects that represent the browser's window and all its elements.

### JS Window
The `window` object represents an open window in a browser. It is the top-level object in the BOM hierarchy.

#### Common Properties and Methods
- `window.innerWidth` and `window.innerHeight`: Returns the interior width and height of the window.
- `window.open()`: Opens a new browser window.
- `window.close()`: Closes the current window.
- `window.alert()`: Displays an alert box with a specified message.
- `window.confirm()`: Displays a dialog box with a specified message, along with OK and Cancel buttons.
- `window.prompt()`: Displays a dialog box that prompts the visitor for input.

```js
// Example of window properties and methods
console.log('Window Width:', window.innerWidth);
console.log('Window Height:', window.innerHeight);

function openNewWindow() {
    window.open('https://www.example.com', '_blank');
}

function showAlert() {
    window.alert('This is an alert!');
}

function askConfirmation() {
    const result = window.confirm('Do you confirm this action?');
    console.log('Confirmation result:', result);
}

function askForInput() {
    const userInput = window.prompt('Please enter your name:');
    console.log('User Input:', userInput);
}
```

### JS Screen
The `screen` object contains information about the visitor's screen.

#### Common Properties
- `screen.width` and `screen.height`: Returns the width and height of the screen.
- `screen.availWidth` and `screen.availHeight`: Returns the available width and height of the screen (excluding interface features like taskbars).

```js
// Example of screen properties
console.log('Screen Width:', screen.width);
console.log('Screen Height:', screen.height);
console.log('Available Screen Width:', screen.availWidth);
console.log('Available Screen Height:', screen.availHeight);
```

### JS Location
The `location` object contains information about the current URL.

#### Common Properties and Methods
- `location.href`: Returns the entire URL of the current page.
- `location.hostname`: Returns the domain name of the web host.
- `location.pathname`: Returns the path and filename of the current page.
- `location.search`: Returns the query string part of the URL.
- `location.hash`: Returns the anchor part of the URL.
- `location.assign()`: Loads a new document.

```js
// Example of location properties and methods
console.log('Current URL:', location.href);
console.log('Hostname:', location.hostname);
console.log('Pathname:', location.pathname);
console.log('Query String:', location.search);
console.log('Hash:', location.hash);

function redirectToGoogle() {
    location.assign('https://www.google.com');
}
```

### JS History
The `history` object contains the browser's history.

#### Common Methods
- `history.back()`: Loads the previous URL in the history list.
- `history.forward()`: Loads the next URL in the history list.
- `history.go()`: Loads a specific URL from the history list.

```js
// Example of history methods
function goBack() {
    history.back();
}

function goForward() {
    history.forward();
}

function goToSpecificPage(index) {
    history.go(index);
}
```

### JS Navigation
The `navigator` object contains information about the browser.

#### Common Properties
- `navigator.appName`: Returns the name of the browser.
- `navigator.appVersion`: Returns the version information of the browser.
- `navigator.userAgent`: Returns the user-agent header sent by the browser to the server.
- `navigator.platform`: Returns the platform for which the browser is compiled.

```js
// Example of navigator properties
console.log('Browser Name:', navigator.appName);
console.log('Browser Version:', navigator.appVersion);
console.log('User Agent:', navigator.userAgent);
console.log('Platform:', navigator.platform);
```

### Popup Alerts
JavaScript provides several methods to display popup alerts, such as `alert()`, `confirm()`, and `prompt()`.

```js
// Example of popup alerts
function showAlert() {
    alert('This is an alert!');
}

function showConfirmation() {
    const result = confirm('Do you agree?');
    console.log('User agreed:', result);
}

function showPrompt() {
    const userResponse = prompt('What is your name?');
    console.log('User name:', userResponse);
}
```

### JS Timing
The `setTimeout()` and `setInterval()` methods allow you to execute code after a delay or repeatedly at specified intervals.

#### `setTimeout()`
Executes a function, once, after waiting a specified number of milliseconds.

```js
// Example of setTimeout
function delayedMessage() {
    setTimeout(() => {
        console.log('This message is delayed by 2 seconds.');
    }, 2000);
}
```

#### `setInterval()`
Calls a function or evaluates an expression at specified intervals (in milliseconds).

```js
// Example of setInterval
function repeatMessage() {
    setInterval(() => {
        console.log('This message repeats every 3 seconds.');
    }, 3000);
}
```

### Cookies
Cookies are used to store data in a user's browser. JavaScript can create, read, and delete cookies.

#### Create and Read a Cookie
```js
// Example of creating and reading a cookie
function setCookie(name, value, days) {
    const d = new Date();
    d.setTime(d.getTime() + (days*24*60*60*1000));
    const expires = "expires=" + d.toUTCString();
    document.cookie = name + "=" + value + ";" + expires + ";path=/";
}

function getCookie(name) {
    const nameEQ = name + "=";
    const ca = document.cookie.split(';');
    for(let i = 0; i < ca.length; i++) {
        let c = ca[i];
        while (c.charAt(0) == ' ') {
            c = c.substring(1, c.length);
        }
        if (c.indexOf(nameEQ) == 0) {
            return c.substring(nameEQ.length, c.length);
        }
    }
    return null;
}

// Set a cookie
setCookie('username', 'JohnDoe', 7);

// Get a cookie
console.log('Cookie Value:', getCookie('username'));
```

#### Delete a Cookie
```js
// Example of deleting a cookie
function deleteCookie(name) {
    setCookie(name, '', -1);
}

// Delete the 'username' cookie
deleteCookie('username');
```

## Interview Questions and Answers

1. **What is the Browser Object Model (BOM)?**
   - **Answer:** The BOM allows JavaScript to interact with the browser. It represents the browser window and includes objects like `window`, `navigator`, `screen`, `history`, `location`, and `document`.

2. **How do you open a new browser window using JavaScript?**
   - **Answer:** You can use the `window.open()` method to open a new browser window.
   - **Code Example:**
     ```js
     window.open('https://www.example.com', '_blank');
     ```

3. **What is the difference between `window.alert()`, `window.confirm()`, and `window.prompt()`?**
   - **Answer:**
     - `window.alert()`: Displays a message and an OK button.
     - `window.confirm()`: Displays a message and returns `true` if OK is clicked and `false` if Cancel is clicked.
     - `window.prompt()`: Displays a message, a text input field, and returns the user's input.

4. **How can you get the current URL of the page?**
   - **Answer:** You can use the `location.href` property to get the current URL.
   - **Code Example:**
     ```js
     console.log('Current URL:', location.href);
     ```

5. **How do you redirect the browser to a new URL?**
   - **Answer:** You can use the `location.assign()` method to load a new document.
   - **Code Example:**
     ```js
     location.assign('https://www.google.com');
     ```

6. **What methods are available in the `history` object?**
   - **Answer:** The `history` object methods include `history.back()`, `history.forward()`, and `history.go()`.

7. **How do you set and get a cookie using JavaScript?**
   - **Answer:** You can use `document.cookie` to set and get cookies.
   - **Code Example:**
     ```js
     // Set a cookie
     document.cookie = "username=JohnDoe";

     // Get a cookie
     const cookies = document.cookie;
     console.log(cookies);
     ```

---

These notes, interview questions, and code examples provide a comprehensive overview of the JavaScript HTML BOM and its related concepts.