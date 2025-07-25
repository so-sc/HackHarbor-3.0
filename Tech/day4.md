---
day: 4
title: "Javascript basics"
description: "Javascript basics"
---

# Day 4 - Javascript basics

---

# 🧠 1. Introduction to the Web & JavaScript

## 🌍 What is the Web?

The **Web** (World Wide Web) is a system of interlinked hypertext documents accessed via the Internet. These documents (webpages) are built using:

- **HTML** (Structure)
- **CSS** (Styling)
- **JavaScript** (Interactivity)

<br>

## 📄 Static vs Dynamic Web Pages

| Type    | Description                                     | Technologies Used                  |
|---------|-------------------------------------------------|------------------------------------|
| Static  | Content doesn’t change unless manually updated | HTML, CSS                          |
| Dynamic | Content changes based on interaction or data   | HTML, CSS, **JavaScript**, Backend |

![Side-by-side image of a static HTML page and a dynamic page showing real-time update or form submission](https://github.com/so-sc/HackHarbor-3.0/blob/main/Tech/assets/static-vs-dynamic-website.webp)

<br>

## 💬 What is JavaScript?

JavaScript is a **high-level**, **interpreted**, and **dynamically-typed** programming language used to make webpages interactive.

- It runs in the browser.
- It reacts to user actions.
- It updates the DOM (Document Object Model).
- It can also be used server-side (Node.js).

<br>

## 🧪 Why Use JavaScript?

- Create dynamic content
- Respond to user events (clicks, scroll, keys)
- Control multimedia
- Build games and interactive UIs
- Form validation

<br>

## 🧠 How JavaScript Works

JavaScript doesn’t need compilation like C/C++. It’s **interpreted and executed** by the browser’s **JavaScript engine**.

Popular JS Engines:

| Browser     | Engine Name |
|-------------|-------------|
| Chrome      | V8          |
| Firefox     | SpiderMonkey|
| Safari      | JavaScriptCore |
| Edge        | Chakra (Legacy), now also V8 |

<br>

## ⚙️ V8 JavaScript Engine

V8 is Google's open-source JavaScript engine written in C++.

- Used in Chrome and Node.js
- Converts JS code to **machine code** for speed
- Compiles JS at runtime using **JIT (Just-In-Time Compilation)**

![Diagram showing JS → Parser → AST → JIT → Machine Code](https://github.com/so-sc/HackHarbor-3.0/blob/main/Tech/assets/v8-engine.png)

<br>

## 💡 Quick Example

```html
<!-- HTML -->
<h2 id="greet">Hello!</h2>
<button onclick="changeText()">Click Me</button>

<!-- JavaScript -->
<script>
  function changeText() {
    document.getElementById("greet").innerText = "You clicked the button!";
  }
</script>
```
📝 This small code shows how JavaScript can interact with HTML by changing the text of an element when a button is clicked.

<br>

# 🔗 2. Connecting JavaScript with HTML & CSS

## 🧙‍♂️ The Role of HTML, CSS, and JS Together

To build modern web pages:

* **HTML** provides the **structure**
* **CSS** handles the **styling**
* **JavaScript** adds **interactivity and dynamic behavior**

These three work **together**, not separately.

<br>

## 📦 Ways to Include JavaScript in HTML

There are **three main methods** to use JavaScript in an HTML file:

### 1. Inline JavaScript

Using the `onclick` attribute directly in HTML:

```html
<button onclick="alert('Hello!')">Click Me</button>
```

✅ Simple, but not recommended for maintainability.

<br>

### 2. Internal JavaScript

Placed inside a `<script>` tag within the same HTML file:

```html
<!DOCTYPE html>
<html>
<head>
  <script>
    function sayHello() {
      alert("Hello from internal JS!");
    }
  </script>
</head>
<body>
  <button onclick="sayHello()">Greet</button>
</body>
</html>
```

✅ Better than inline. Good for small pages or demos.

<br>

### 3. External JavaScript

Saved as a `.js` file and linked using the `<script src="..."></script>` tag:

```html
<!-- index.html -->
<script src="script.js"></script>
```

```js
// script.js
function greetUser() {
  alert("Hello from external JS!");
}
```

✅ Best practice. Keeps code organized and reusable.

<br>

## 📍 Where to Place the `<script>` Tag?

You can place `<script>` either:

* In the `<head>` (but may block page rendering)
* **Or** at the end of `<body>` (✅ recommended)

### ✅ Best Practice:

```html
<!DOCTYPE html>
<html>
  <head>
    <title>My Webpage</title>
  </head>
  <body>
    <button onclick="sayHi()">Say Hi</button>

    <script src="main.js"></script>
  </body>
</html>
```

<br>

## 🎨 JavaScript Can Also Interact with CSS

JavaScript can:

* Add or remove **CSS classes**
* Directly change **inline styles**
* React to user actions (hover, click, input)

<br>

## 🧪 Demo: Changing Background Color

```html
<!-- index.html -->
<button onclick="changeColor()">Change Background</button>

<script>
  function changeColor() {
    document.body.style.backgroundColor = "lightblue";
  }
</script>
```

<br>

## 🧪 Demo: Dark Mode Toggle

```html
<button onclick="toggleDarkMode()">Toggle Dark Mode</button>

<script>
  function toggleDarkMode() {
    document.body.classList.toggle("dark-mode");
  }
</script>

<style>
  .dark-mode {
    background-color: #121212;
    color: white;
  }
</style>
```

📝 This example shows JavaScript adding/removing a CSS class on button click.

<br>

![A pyramid with HTML at base, CSS above, and JS on top adding dynamic behavior](https://github.com/so-sc/HackHarbor-3.0/blob/main/Tech/assets/pyramid-html-css-js.png)

---

# 🔢 3. JavaScript Syntax & Variables

## ✍️ Writing JavaScript: The Basics

JavaScript is case-sensitive and follows a syntax similar to C-style languages like C++ or Java.

### 🗒️ Statements and Semicolons

* Each instruction is called a **statement**.
* It's good practice to end each statement with a semicolon `;`, though it's not mandatory due to *automatic semicolon insertion*.

```js
let name = "John";
console.log(name);
```

<br>

## 🧾 Comments in JavaScript

Used to explain code or prevent execution:

```js
// This is a single-line comment

/*
  This is a
  multi-line comment
*/
```

<br>

## 📦 Declaring Variables

Three ways to declare variables:

### ✅ `let`

* Block-scoped
* Can be updated but not re-declared in same scope

### ✅ `const`

* Block-scoped
* Cannot be updated or re-declared
* Must be initialized during declaration

### ⚠️ `var`

* Function-scoped (not block-scoped)
* Can be updated and re-declared
* **Avoid using `var` in modern JS**

```js
let age = 20;
const PI = 3.14;
var username = "student";
```

<br>

## 🧠 Data Types in JavaScript

JavaScript is **dynamically typed** — you don't need to specify a data type explicitly.

### Primitive Data Types:

* `String`: Text (e.g., "hello")
* `Number`: Integer or float (e.g., 42, 3.14)
* `Boolean`: `true` or `false`
* `Null`: Explicitly nothing
* `Undefined`: Variable declared but not assigned
* `BigInt`: For very large numbers
* `Symbol`: Unique identifiers

```js
let name = "Alice";      // String
let age = 21;            // Number
let isStudent = true;    // Boolean
let score = null;        // Null
let city;                // Undefined
```

<br>

## 🧮 Operators in JavaScript

### Arithmetic Operators:

```js
+   // Addition
-   // Subtraction
*   // Multiplication
/   // Division
%   // Modulus
```

### Comparison Operators:

```js
==    // Equal to (type conversion)
===   // Strictly equal (no type conversion)
!=    // Not equal
!==   // Strictly not equal
>
<
>=
<=
```

### Logical Operators:

```js
&&    // Logical AND
||    // Logical OR
!     // Logical NOT
```

<br>

## 🧪 Demo: Simple Calculator with Variables & Operators

```html
<!-- index.html -->
<p id="result"></p>

<script>
  let num1 = 10;
  let num2 = 5;
  let sum = num1 + num2;

  document.getElementById("result").innerText = "Sum = " + sum;
</script>
```

<br>

![chart showing all primitive and non-primitive types](https://github.com/so-sc/HackHarbor-3.0/blob/main/Tech/assets/datatypes-js.png)

---

# 🧩 4. Functions & Events

## 🧠 What is a Function?

A **function** is a block of reusable code that performs a specific task.

```js
function greet() {
  console.log("Hello!");
}

greet(); // Calling the function
```

Functions help:

* Break code into reusable blocks
* Reduce repetition
* Improve readability and modularity

<br>

## ✍️ Function Parameters & Return Values

Functions can accept **parameters** and optionally return a value.

```js
function add(a, b) {
  return a + b;
}

let result = add(5, 3); // 8
console.log(result);
```

<br>

## ⚡ JavaScript Events

JavaScript can respond to **events** such as:

* `click`
* `mouseover`
* `keydown`
* `submit`

You can attach events using:

* `onclick` in HTML
* `.addEventListener()` in JS (recommended)

### Example: Using `onclick`

```html
<button onclick="sayHi()">Click Me</button>

<script>
  function sayHi() {
    alert("Hello there!");
  }
</script>
```

### Example: Using `addEventListener()`

```html
<button id="btn">Click Me</button>

<script>
  document.getElementById("btn").addEventListener("click", function() {
    alert("You clicked the button!");
  });
</script>
```

<br>

## 🧪 Demo: Toggle Light/Dark Mode

```html
<button onclick="toggleMode()">Toggle Mode</button>

<script>
  function toggleMode() {
    document.body.classList.toggle("dark");
  }
</script>

<style>
  .dark {
    background-color: #222;
    color: #fff;
  }
</style>
```

<br>

![Diagram showing function call stack or how events flow from browser to handler](https://github.com/so-sc/HackHarbor-3.0/blob/main/Tech/assets/function-call-stack-js.png)

---

# 🔀 5. Conditional Logic & Loops

## ❓ Conditional Statements

Conditional statements are used to make decisions in JavaScript based on conditions.

### ✅ if Statement

```js
let age = 18;
if (age >= 18) {
  console.log("You are an adult.");
}
```

### ✅ if-else Statement

```js
let score = 45;
if (score >= 50) {
  console.log("Pass");
} else {
  console.log("Fail");
}
```

### ✅ if-else-if Ladder

```js
let marks = 85;
if (marks >= 90) {
  console.log("Grade A+");
} else if (marks >= 75) {
  console.log("Grade A");
} else if (marks >= 60) {
  console.log("Grade B");
} else {
  console.log("Grade C");
}
```

### ✅ switch Statement

```js
let day = 2;
switch(day) {
  case 1:
    console.log("Monday");
    break;
  case 2:
    console.log("Tuesday");
    break;
  default:
    console.log("Another day");
}
```

<br>

## 🔁 Loops in JavaScript

Loops are used to run the same block of code multiple times.

### 🔂 for Loop

```js
for (let i = 0; i < 5; i++) {
  console.log("Iteration", i);
}
```

### 🔁 while Loop

```js
let i = 0;
while (i < 5) {
  console.log("While Loop", i);
  i++;
}
```

<br>

## 🔚 break and continue

* `break` exits the loop early
* `continue` skips the current iteration

```js
for (let i = 1; i <= 5; i++) {
  if (i === 3) continue;  // Skip 3
  if (i === 5) break;     // Stop at 5
  console.log(i);
}
```

<br>

## 🧪 Demo: Checking Even or Odd Numbers with a Loop

```html
<script>
  for (let i = 1; i <= 5; i++) {
    if (i % 2 === 0) {
      console.log(i + " is Even");
    } else {
      console.log(i + " is Odd");
    }
  }
</script>
```

<br>

![Flowchart showing branching and loop cycles](https://github.com/so-sc/HackHarbor-3.0/blob/main/Tech/assets/conditional-looping-js.jpg)

---

# 🧺 6. Arrays & Objects

## 🔢 Arrays in JavaScript

An **array** is a collection of values stored in a single variable.

```js
let fruits = ["apple", "banana", "cherry"];
console.log(fruits[0]); // apple
```

* Arrays are **zero-indexed**
* Can store mixed data types (though not recommended)

### 🔧 Common Array Operations

```js
let nums = [10, 20, 30];

nums.push(40);       // Add to end
nums.pop();          // Remove from end
nums.shift();        // Remove from start
nums.unshift(5);     // Add to start
console.log(nums);
```

<br>

## 🔁 Looping through Arrays

### Using `for` loop:

```js
let colors = ["red", "green", "blue"];
for (let i = 0; i < colors.length; i++) {
  console.log(colors[i]);
}
```

<br>

## 📦 Objects in JavaScript

An **object** is a collection of **key-value pairs**.

```js
let student = {
  name: "John",
  age: 21,
  isGraduate: true
};

console.log(student.name); // John
```

* Keys are strings (or symbols)
* Values can be any data type (even functions)

### 🔧 Modifying Objects

```js
student.age = 22;         // Update
student.city = "Mumbai";  // Add new
```

<br>

## 🔁 Looping through Objects

### Using `for...in`:

```js
for (let key in student) {
  console.log(key, student[key]);
}
```

<br>

## 🧪 Demo: Store and Display Book Info

```html
<script>
  let book = {
    title: "The Alchemist",
    author: "Paulo Coelho",
    year: 1988
  };

  for (let key in book) {
    console.log(key + ": " + book[key]);
  }
</script>
```

<br>

| Array                              | Object                                 |
|------------------------------------|----------------------------------------|
| `let fruits = [`                   | `let student = {`                      |
| `  "apple",`                       | `  name: "Alice",`                     |
| `  "banana",`                      | `  age: 20,`                           |
| `  "cherry"`                       | `  isGraduate: true`                   |
| `];`                               | `};`                                   |
|                                    |                                        |
| `console.log(fruits[0]);`          | `console.log(student.name);`           |
| `// "apple"`                       | `// "Alice"`                           |

---

# 🌐 7. DOM Manipulation

## 🧱 What is the DOM?

**DOM** (Document Object Model) is a tree-like structure created by the browser from the HTML.

* Every HTML element becomes a **node**.
* JavaScript can read, modify, and delete these nodes.

> Think of DOM as JavaScript's way to interact with a webpage.

<br>

## 🔍 Accessing Elements

You can use various methods to access elements:

### By ID:

```js
document.getElementById("demo")
```

### By Class:

```js
document.getElementsByClassName("info")
```

### By Tag Name:

```js
document.getElementsByTagName("p")
```

### Query Selector (Recommended):

```js
document.querySelector(".info")     // first match

document.querySelectorAll(".info")  // all matches
```

<br>

## ✍️ Changing Content

### Change Text:

```js
document.getElementById("demo").innerText = "Hello World!";
```

### Change HTML:

```js
document.getElementById("demo").innerHTML = "<strong>Bold Text</strong>";
```

<br>

## 🎨 Changing Styles

```js
document.getElementById("demo").style.color = "blue";
document.getElementById("demo").style.fontSize = "20px";
```

<br>

## ➕ Creating & Removing Elements

### Create Element:

```js
let para = document.createElement("p");
para.innerText = "New Paragraph";
document.body.appendChild(para);
```

### Remove Element:

```js
let el = document.getElementById("demo");
el.remove();
```

<br>

## 📌 Setting Attributes

```js
document.getElementById("myImg").setAttribute("src", "image.jpg");
document.getElementById("myImg").setAttribute("alt", "Sample Image");
```

<br>

## 🧪 Demo: Update Text on Button Click

```html
<p id="demo">Original Text</p>
<button onclick="updateText()">Click Me</button>

<script>
  function updateText() {
    document.getElementById("demo").innerText = "Text Updated!";
  }
</script>
```

<br>

![Diagram showing hierarchy of HTML tags as tree nodes](https://github.com/so-sc/HackHarbor-3.0/blob/main/Tech/assets/dom-tree-strucutre.png)

---

# 🧰 Bonus: What Are Node.js and npm?

Even though not needed for basic web JavaScript, these tools are essential if you want to move into **backend development**, **build tools**, or **large projects**:

## 🌍 Node.js

* A runtime environment that lets you run JavaScript **outside the browser**.
* Built on the **V8 engine** (same as Chrome).
* Used for building servers, tools, and full-stack apps.

```bash
node script.js
```

## 📦 npm (Node Package Manager)

* Comes with Node.js
* Lets you install and manage **packages/libraries** made by others.

```bash
npm install express
```

> You won’t need these for browser-based JS learning — but they are **must-know** tools once you get into advanced JS or backend development.

---

# 🔗 Links
## 📘 JavaScript Basics
- [Mozilla MDN JavaScript Guide](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide)
- [W3Schools JavaScript Tutorial](https://www.w3schools.com/js/)

## 🧱 DOM & Events
- [MDN – Document Object Model](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model)
- [JavaScript.info – Events](https://javascript.info/introduction-browser-events)

## 🧪 Practice Platforms
- Online Editor:- Your very own browser (OR) NodeJS (OR) [JSFiddle](https://jsfiddle.net/)
- Try JS Instantly:- [CodePen](https://codepen.io/)
- Build a small project:- [FreeCodeCamp JS Calorie Counter](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures-v8/#learn-form-validation-by-building-a-calorie-counter)

## 🧠 Deep Dives (for later exploration)
- [Google Developers Blog – V8](https://v8.dev/)
- [MDN – How JavaScript works](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Details_of_the_Object_Model)

---
