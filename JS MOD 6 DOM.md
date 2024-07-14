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

# Module 6: JavaScript HTML DOM

## 1. HTML Document Object Model (DOM)
The Document Object Model (DOM) is a programming interface for HTML and XML documents. It represents the page so that programs can change the document structure, style, and content. The DOM represents the document as nodes and objects; that way, programming languages can interact with the page.

## 2. DOM Methods
DOM methods are actions that can be performed on HTML elements. They are used to get or manipulate elements in the DOM.

- `getElementById()`: Selects an element by its ID.
- `getElementsByClassName()`: Selects all elements with a specified class name.
- `getElementsByTagName()`: Selects all elements with a specified tag name.
- `querySelector()`: Returns the first element that matches a specified CSS selector.
- `querySelectorAll()`: Returns all elements that match a specified CSS selector.
- `createElement()`: Creates an HTML element.
- `appendChild()`: Adds a new child node to an element.
- `removeChild()`: Removes a child node from an element.

## 3. DOM Documents
The `document` object represents the whole HTML document. It is the root node of the HTML document tree and provides properties and methods to access and manipulate the document content.

- `document.title`: Gets or sets the title of the document.
- `document.body`: Represents the `<body>` element of the document.
- `document.head`: Represents the `<head>` element of the document.
- `document.createElement()`: Creates an HTML element.
- `document.getElementById()`: Returns an element with the specified ID.

## 4. DOM Elements
DOM elements are the individual parts of the document, represented as objects in JavaScript. Elements can be accessed and manipulated using various methods.

- `element.innerHTML`: Gets or sets the HTML content of an element.
- `element.textContent`: Gets or sets the text content of an element.
- `element.style`: Accesses or sets the inline style of an element.
- `element.attributes`: Returns a live collection of all attributes of an element.

## 5. DOM HTML
DOM HTML refers to the manipulation of HTML elements within the DOM. It allows dynamic changes to the HTML structure, attributes, and content.

- `element.innerHTML`: Allows you to get or set the HTML content inside an element.
- `element.setAttribute()`: Adds a new attribute or changes the value of an existing attribute on an element.
- `element.getAttribute()`: Returns the value of a specified attribute on the element.

## 6. DOM Forms
Forms are used to collect user input. The DOM provides properties and methods to manipulate form elements.

- `form.elements`: Returns a collection of all form elements.
- `input.value`: Gets or sets the value of a form field.
- `input.checked`: Gets or sets the checked state of a checkbox or radio button.
- `form.submit()`: Submits the form.

## 7. DOM CSS
DOM CSS involves the manipulation of CSS styles through the DOM.

- `element.style.property`: Allows you to get or set a specific CSS property.
- `element.classList`: Provides methods to add, remove, and toggle CSS classes.

## 8. DOM Events
Events are actions that can be detected by JavaScript. These can be user actions or browser actions.

- `onclick`: Event triggered when an element is clicked.
- `onchange`: Event triggered when the value of an element changes.
- `onmouseover`: Event triggered when the mouse is moved over an element.
- `onload`: Event triggered when the page or an image is fully loaded.

## 9. DOM Event Listener
Event listeners are methods that wait for specified events to occur.

- `addEventListener()`: Attaches an event handler to the specified element.
- `removeEventListener()`: Removes an event handler from the specified element.

## 10. DOM Navigation
DOM navigation refers to the ability to traverse through the elements of the DOM.

- `parentNode`: Returns the parent node of an element.
- `childNodes`: Returns a live NodeList of child nodes of an element.
- `firstChild`: Returns the first child node of an element.
- `lastChild`: Returns the last child node of an element.
- `nextSibling`: Returns the next sibling node of an element.
- `previousSibling`: Returns the previous sibling node of an element.

## Interview Questions and Answers

### Q1: What is the DOM?
**A1:** The DOM, or Document Object Model, is a programming interface for HTML and XML documents. It represents the document as a tree of nodes, where each node is an object representing a part of the document, allowing programs to change the document structure, style, and content.

### Q2: How can you select an element by its ID using JavaScript?
**A2:** You can select an element by its ID using the `getElementById()` method. For example:
```javascript
let element = document.getElementById('elementId');








```markdown
## Q3: What is the difference between `innerHTML` and `textContent`?

`innerHTML` gets or sets the HTML content of an element, including HTML tags. `textContent` gets or sets the text content of an element, excluding HTML tags.

## Q4: How do you add an event listener to an element?

You can add an event listener to an element using the `addEventListener()` method. For example:

```javascript
element.addEventListener('click', function() {
  // event handler code
});
```

## Q5: How can you create a new HTML element using JavaScript?

You can create a new HTML element using the `createElement()` method. For example:

```javascript
let newElement = document.createElement('div');
```

## Q6: What is the purpose of the `querySelectorAll()` method?

The `querySelectorAll()` method returns a static NodeList of all elements in the document that match a specified CSS selector.

## Q7: How can you change the style of an element using JavaScript?

You can change the style of an element using the `style` property. For example:

```javascript
element.style.color = 'red';
```

## Q8: How do you submit a form using JavaScript?

You can submit a form using the `submit()` method. For example:

```javascript
document.forms['formName'].submit();
```

## Q9: What is the `classList` property and how is it used?

The `classList` property returns a live DOMTokenList of the class attributes of an element. It provides methods to add, remove, and toggle classes. For example:

```javascript
element.classList.add('newClass');
element.classList.remove('existingClass');
element.classList.toggle('activeClass');
```

## Q10: What is the difference between `childNodes` and `children`?

`childNodes` returns a live NodeList of all child nodes of an element, including text nodes and comment nodes. `children` returns a live HTMLCollection of only the child elements of an element.
```
