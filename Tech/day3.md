---
day: 3
title: "Webdev basics - Intro to HTML CSS, How the web works, Dynamic and static pages"
description: "Webdev basics - Intro to HTML CSS, How the web works, Dynamic and static pages"
---

## 1. How the Web Works

**What to Teach:**
- **Internet vs. World Wide Web:**  
  Clarify the difference between the Internet (network of networks) and the WWW (a service running on the Internet).
- **Web Browsers & Servers:**  
  Explain what browsers do (render web pages) and what servers do (host web content).
- **Client-Server Model:**  
  Visualize the process: client sends request, server responds. Discuss request/response cycles.
- **HTTP/HTTPS Basics:**  
  Introduce these protocols as the language of the web. Touch on security (what HTTPS adds).
- **Domain Names & Hosting:**  
  How domain names work, what DNS is, and basics of web hosting (where websites live).
- **Static vs. Dynamic Websites:**  
  Define static pages (same content for all) vs. dynamic pages (content can change/user-specific).

**Why:**  
This foundation demystifies the web, helping students understand the “why” before the “how.” It sets context for everything that follows.

**Sample Code: (Client Request via HTML Form)**
```html
<!-- This HTML form represents a client request to a server -->
<form action="https://example.com/submit" method="POST">
  <label for="name">Your Name:</label>
  <input id="name" name="name" type="text" required>
  <button type="submit">Send</button>
</form>
```
This form demonstrates how a browser (client) sends data to a server, exemplifying the request/response cycle.

---

## 2. Introduction to HTML (HyperText Markup Language)

**What to Teach:**
- **HTML Structure:**  
  Teach the skeleton: `<!DOCTYPE html>`, `<html>`, `<head>`, `<body>`.
- **Basic Tags:**  
  Headings (`<h1>`-`<h6>`), paragraphs (`<p>`), links (`<a>`), images (`<img>`), lists (`<ul>`, `<ol>`, `<li>`).
- **Attributes:**  
  How to use and why: `href`, `src`, `alt`, etc.
- **Tables and Forms (Basics):**  
  Building simple tables and basic forms (input fields, labels, buttons).
- **Semantic HTML (Intro):**  
  Introduce elements like `<header>`, `<footer>`, `<nav>`, `<article>`, and why they matter (better structure, accessibility, SEO).
- **Best Practices:**  
  Proper indentation, commenting, and code readability.

**Why:**  
HTML is the backbone of web pages. Understanding structure and common tags is essential for all future web work.

**Sample Code: (Basic HTML Page)**
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>My First Web Page</title>
</head>
<body>
  <header>
    <h1>Welcome to Web Development Basics!</h1>
  </header>
  <nav>
    <a href="#about">About</a> | <a href="#contact">Contact</a>
  </nav>
  <section id="about">
    <h2>About Me</h2>
    <p>Hello! I am learning web development.</p>
    <img src="profile.jpg" alt="Profile picture" width="150">
  </section>
  <section>
    <h2>My Skills</h2>
    <ul>
      <li>HTML</li>
      <li>CSS</li>
      <li>Problem Solving</li>
    </ul>
  </section>
  <footer>
    <p>Contact: student@example.com</p>
  </footer>
</body>
</html>
```

---

## 3. Introduction to CSS (Cascading Style Sheets)

**What to Teach:**
- **What is CSS?**  
  Purpose (styling HTML), syntax (selectors, properties, values).
- **Ways to Add CSS:**  
  Inline, internal (`<style>`), and external CSS files.
- **Selectors & Properties:**  
  Using element, class, and id selectors. Common properties: `color`, `background`, `font-size`, `margin`, `padding`.
- **Box Model:**  
  Explain content, padding, border, margin, and how they interact.
- **Layout Basics:**  
  `display` property (block, inline), intro to `position` (static, relative, absolute, fixed).
- **Text & Link Styling:**  
  Fonts, text alignment, removing underline from links, hover effects.
- **Responsive Design (Intro):**  
  Why websites must work on all devices. Briefly show media queries.

**Why:**  
CSS makes web pages visually appealing and usable. Early exposure to best practices prevents “bad habits” later.

**Sample Code: (Basic CSS Styling)**
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Styled Web Page</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #f6f8fa;
      margin: 40px;
    }
    header {
      background: #2d72d9;
      color: white;
      padding: 20px;
      text-align: center;
    }
    img {
      border-radius: 50%;
    }
    nav a {
      color: #2d72d9;
      text-decoration: none;
      padding: 0 10px;
    }
    nav a:hover {
      text-decoration: underline;
    }
    section {
      background: #fff;
      padding: 15px;
      margin-bottom: 20px;
      border-radius: 8px;
      box-shadow: 0 2px 8px rgba(0,0,0,0.05);
    }
    @media (max-width: 600px) {
      body {
        margin: 10px;
      }
      section {
        padding: 5px;
      }
    }
  </style>
</head>
<body>
  <header>
    <h1>Welcome to Styled Web Page!</h1>
  </header>
  <nav>
    <a href="#about">About</a> | <a href="#contact">Contact</a>
  </nav>
  <section id="about">
    <h2>About Me</h2>
    <p>This page demonstrates basic CSS styling.</p>
    <img src="profile.jpg" alt="Profile picture" width="100">
  </section>
  <footer>
    <p>Contact: student@example.com</p>
  </footer>
</body>
</html>
```

---

## 4. Static vs. Dynamic Web Pages

**What to Teach:**
- **Static Pages:**  
  Content is fixed (e.g., info page, resume site). Show with plain HTML/CSS.
- **Dynamic Pages:**  
  Content can change (based on user, time, etc.).  
  *For this intro, you can explain conceptually, and if possible, show a simple form that saves/shows user input or mention server-side scripting (without deep coding).*
- **Comparison:**  
  Use cases, advantages, and disadvantages.

**Why:**  
Understanding the difference shapes how students think about web applications and prepares them for JavaScript/backend concepts later.

**Sample Code: (Static vs Dynamic Example)**

_Static HTML Page:_
```html
<!DOCTYPE html>
<html>
<head>
  <title>Static Page Example</title>
</head>
<body>
  <h1>Welcome, Guest!</h1>
  <p>This content is always the same for every visitor.</p>
</body>
</html>
```

_"Dynamic" Page Simulation with HTML (No actual backend, just for illustration):_
```html
<!DOCTYPE html>
<html>
<head>
  <title>Dynamic Page Example (Frontend Only)</title>
  <script>
    function showMessage() {
      var name = document.getElementById('username').value;
      document.getElementById('message').innerText = 'Welcome, ' + name + '!';
    }
  </script>
</head>
<body>
  <input type="text" id="username" placeholder="Enter your name">
  <button onclick="showMessage()">Submit</button>
  <h1 id="message"></h1>
</body>
</html>
```
*Note: True dynamic pages are created using backend languages (PHP, Node.js, Python etc.) or frameworks, but this example demonstrates the concept using JavaScript.*

---
