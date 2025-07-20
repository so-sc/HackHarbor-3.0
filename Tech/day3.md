---
day: 3
title: "Webdev basics - Intro to HTML CSS, How the web works, Dynamic and static pages"
description: "Webdev basics - Intro to HTML CSS, How the web works, Dynamic and static pages"
---

## 1. How the Web Works

---

#### **Internet vs. World Wide Web**
- **Internet:**  
  The Internet is a massive global network of computers that can send data to each other. It’s the infrastructure—like the roads and highways connecting cities.
- **World Wide Web (WWW):**  
  The Web is a service that runs on top of the Internet. It’s made up of web pages and websites you can visit using a browser. Think of it as the cars and buses (websites and apps) using the roads (Internet).
- **Example:**  
  You can use the Internet to send emails, make video calls, or play games online—not just browse web pages.

---

#### **Web Browsers & Servers**
- **Web Browser:**  
  A program (like Chrome, Firefox, or Edge) that lets you view and interact with websites. It translates code (HTML, CSS, JavaScript) into the visual pages you see.
- **Web Server:**  
  A computer that “serves” (sends) web pages/files when asked. When you visit a site, your browser asks the server for content, and the server responds with the files needed to display it.
- **Analogy:**  
  The browser is like a waiter taking your order (website address) and bringing you food (web page) from the kitchen (server).

---

#### **Client-Server Model**
- **Client:**  
  The device or software (your browser) making the request.
- **Server:**  
  The computer responding with data (the website).
- **How it works:**  
  1. You type a URL into your browser (client).
  2. The browser sends a request to the web server.
  3. The server processes the request and sends back the required files (HTML, images, etc.).
  4. The browser displays the web page.
- **Request/Response Cycle:**  
  Every time you click a link or submit a form, the process repeats: request sent → response received.

---

#### **HTTP/HTTPS Basics**
- **HTTP (Hypertext Transfer Protocol):**  
  The protocol (set of rules) for transferring web pages and data over the Internet. It defines how messages are formatted and transmitted.
- **HTTPS (HTTP Secure):**  
  The secure version of HTTP. Data is encrypted, making it safe from hackers during transmission. Used on sites where privacy matters (banking, shopping, logins).
- **Why It Matters:**  
  Always look for the lock icon (🔒) in your browser; it means your connection is secure (HTTPS).

---

#### **Domain Names & Hosting**
- **Domain Name:**  
  The easy-to-remember address of a website (e.g., google.com). Behind the scenes, it points to a server’s IP address.
- **DNS (Domain Name System):**  
  Like the Internet’s phonebook—translates domain names into IP addresses so browsers can locate servers.
- **Web Hosting:**  
  The service of storing website files on a server, so they are accessible over the Internet. Hosting companies rent out space and resources for your site to “live” online.

---

### **Why Teach This?**
Understanding these basics:
- Helps students grasp what happens “behind the scenes” when they use the Internet.
- Makes learning web development less mysterious and more logical.
- Builds a solid foundation for more advanced topics (like web security, APIs, or full-stack development).

---

### **Sample Code: (Client Request via HTML Form)**

```html
<!-- This HTML form represents a client request to a server -->
<form action="https://example.com/submit" method="POST">
  <label for="name">Your Name:</label>
  <input id="name" name="name" type="text" required>
  <button type="submit">Send</button>
</form>
```

**Explanation:**  
- When the user fills in the form and clicks “Send,” the browser (client) sends the name to `https://example.com/submit` using the POST method.
- The server at that address receives the data, processes it (e.g., saves the name to a database), and sends back a response (such as a “Thank you” page).
- This simple form illustrates the **request/response cycle**: the client (browser) sends a request; the server receives and responds.

---

### **Visual Diagram (Suggested for Teaching)**
```
[Browser (Client)]  <--request--  [Internet]  --request-->  [Web Server]
      |                                                      |
      |                                                      |
      <---------------------response-------------------------/
```
- The client (browser) initiates the request; the server processes and responds.

---

### **Classroom Activity Suggestion**
- **Demonstrate a live form submission** using browser Developer Tools (Network tab) so students can see the request/response in action.
- **Ask students to explain the difference** between static and dynamic web pages using real-world examples (e.g., Wikipedia home page vs. your Facebook feed).

---

## 2. Introduction to HTML (HyperText Markup Language)

---

#### **HTML Structure**
- **`<!DOCTYPE html>`:**  
  Declares the document type and HTML version. Always placed at the very top, it tells the browser to render the page using the latest HTML standard.
- **`<html>`:**  
  The root element that wraps all your content. Everything on your web page sits inside this tag.
- **`<head>`:**  
  Contains meta-information about the page (not visible to users): character encoding, page title, links to CSS stylesheets, etc.
- **`<body>`:**  
  Holds all the visible content—text, images, buttons, etc.—that users see and interact with.

---

#### **Basic Tags**
- **Headings (`<h1>`–`<h6>`):**  
  Used for titles and section headings. `<h1>` is the biggest and most important; `<h6>` is the smallest.
- **Paragraphs (`<p>`):**  
  For blocks of text or descriptions.
- **Links (`<a>`):**  
  Create hyperlinks to other pages or sites. The `href` attribute specifies the destination URL.
- **Images (`<img>`):**  
  Embeds images. The `src` attribute points to the image file, and `alt` describes the image for accessibility.
- **Lists (`<ul>`, `<ol>`, `<li>`):**  
  `<ul>` = unordered (bulleted) list.  
  `<ol>` = ordered (numbered) list.  
  `<li>` = list item (used inside `<ul>` or `<ol>`).

---

#### **Attributes**
- **What are attributes?**  
  Extra information added to HTML tags to control their behavior or appearance.
- **Common attributes:**
  - `href`: For links—where should the link go?
  - `src`: For images—where is the image file?
  - `alt`: For images—a short description for screen readers or if the image fails to load.
  - `width`, `height`: Set the size of images or elements.
  - `id`, `class`: Used for identifying or styling elements (useful when you start CSS/JavaScript).

---

#### **Tables and Forms (Basics)**
- **Tables:**  
  Use `<table>`, `<tr>` (table row), `<th>` (header cell), and `<td>` (data cell) to organize tabular data.
  ```html
  <table>
    <tr>
      <th>Name</th><th>Age</th>
    </tr>
    <tr>
      <td>Alice</td><td>20</td>
    </tr>
  </table>
  ```
- **Forms:**  
  Allow users to input and send data.  
  Elements include `<form>`, `<input>`, `<label>`, `<button>`, etc.
  ```html
  <form>
    <label for="email">Email:</label>
    <input id="email" name="email" type="email">
    <button type="submit">Subscribe</button>
  </form>
  ```

---

#### **Semantic HTML (Intro)**
- **Why use semantic tags?**  
  Semantic elements like `<header>`, `<footer>`, `<nav>`, `<section>`, `<article>` describe the meaning of the content, not just its appearance.
  - **Benefits:**
    - Easier to read and maintain code
    - Improved accessibility for screen readers
    - Better SEO (search engines understand your page structure)
- **Examples:**
  - `<header>`: Top section, usually with navigation or page title
  - `<nav>`: Contains site navigation links
  - `<section>`: Major content sections
  - `<article>`: Independent content (e.g., a blog post)
  - `<footer>`: Bottom section, usually with contact info or copyright

---

#### **Best Practices**
- **Indentation:**  
  Use consistent indentation (2 or 4 spaces) to make code easy to read.
- **Commenting:**  
  Use `<!-- Comments -->` to annotate or explain parts of your code.
- **Readability:**  
  Use descriptive names for `id` or `class` attributes, structure your HTML logically, and avoid deeply nesting elements unnecessarily.

---

### **Why Learn HTML First?**
- **Foundation:**  
  Every web page is built with HTML. Understanding its basics is essential before adding design (CSS) or interactivity (JavaScript).
- **Visual Feedback:**  
  You see changes instantly—great for beginners!
- **Universal Skill:**  
  Used in every web and many mobile projects, regardless of the framework or language.

---

### **Sample Code: (Basic HTML Page)**

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

**Explanation:**  
- The structure uses semantic tags for clarity and accessibility.
- Navigation allows easy jumping to page sections.
- The image uses `alt` for accessibility and `width` for sizing.
- Lists and headings are used to organize content and improve readability.

---

### **Activity Suggestions**
- **Hands-on:**  
  Have students recreate the sample page, then modify it (e.g., add a new skill, change the image, or update the footer).
- **Challenge:**  
  Ask students to build a simple table (like a schedule) or form (like a signup form).
- **Discussion:**  
  Review different semantic tags and ask why they might be better than just using `<div>` everywhere.

---

**Summary:**  
Learning HTML gives you the power to create and structure web content. With these basics, you can build your own web pages and are ready to learn CSS, JavaScript, and beyond!

---

## 3. Introduction to CSS (Cascading Style Sheets)

---

#### **What is CSS?**

- **Purpose:**  
  CSS is used to style and visually enhance HTML elements, separating content (HTML) from presentation (CSS).
- **Syntax:**  
  CSS is made up of rulesets:  
  - **Selector** `{` **property**: **value**; `}`

**Example:**
```css
p {
  color: blue;
  font-size: 18px;
}
```
This makes all `<p>` text blue and slightly larger.

---

#### **Ways to Add CSS**

1. **Inline CSS:**  
   CSS added directly to an HTML element using the `style` attribute.  
   ```html
   <p style="color: green;">This uses inline CSS.</p>
   ```

2. **Internal CSS:**  
   CSS written inside a `<style>` tag within the HTML `<head>`.  
   ```html
   <head>
     <style>
       h1 { color: purple; }
     </style>
   </head>
   ```

3. **External CSS:**  
   CSS code in a separate `.css` file, linked to the HTML.  
   - **styles.css**
     ```css
     body { background: #f0f0f0; }
     ```
   - **index.html**
     ```html
     <head>
       <link rel="stylesheet" href="styles.css">
     </head>
     ```

**Best Practice:** Use external CSS for most real projects—it's reusable and keeps code cleaner.

---

#### **Selectors & Properties**

- **Element Selector:** Targets all elements of a type.
  ```css
  h2 { color: #2d72d9; }
  ```

- **Class Selector:** Targets elements with a specific class. Use `.` before the class name.
  ```css
  .highlight {
    background: yellow;
    font-weight: bold;
  }
  ```
  ```html
  <p class="highlight">Important!</p>
  ```

- **ID Selector:** Targets one unique element by its `id`. Use `#` before the id.
  ```css
  #main-title {
    font-size: 32px;
    color: darkred;
  }
  ```
  ```html
  <h1 id="main-title">My Site</h1>
  ```

- **Common Properties:**
  - `color`, `background-color`
  - `font-size`, `font-family`
  - `margin`, `padding`
  - `border`

**Example:**
```css
ul {
  padding: 20px;
  background: #e0eaff;
}
```

---

#### **Box Model**

The box model explains how every HTML element is a box, with:
- **Content** (the actual text or image)
- **Padding** (space inside the box, around the content)
- **Border** (outline around the padding)
- **Margin** (space outside the border, between boxes)

**Example:**
```css
section {
  margin: 30px;
  padding: 15px;
  border: 2px solid #2d72d9;
  background: #f9f9f9;
}
```

**Visual:**
```
| Margin | → | Border | → | Padding | → | Content |
```

---

#### **Layout Basics**

- **`display` Property:**
  - `block`: Element takes the full width (e.g., `<div>`, `<p>`).
  - `inline`: Element only as wide as its content (e.g., `<span>`, `<a>`).

  ```css
  nav a {
    display: inline;
    margin-right: 10px;
  }
  section {
    display: block;
  }
  ```

- **`position` Property:**
  - `static` (default): Normal flow.
  - `relative`: Positioned relative to itself (can be nudged using top/left/right/bottom).
  - `absolute`: Positioned relative to its nearest positioned ancestor.
  - `fixed`: Stays in the same place even when scrolling.

  ```css
  .badge {
    position: absolute;
    top: 10px;
    right: 10px;
    background: red;
    color: white;
    padding: 4px 8px;
    border-radius: 8px;
  }
  ```

---

#### **Text & Link Styling**

- **Fonts and Alignment:**
  ```css
  body {
    font-family: 'Segoe UI', Arial, sans-serif;
    text-align: left;
  }
  h1 {
    text-align: center;
  }
  ```

- **Links:**
  ```css
  a {
    color: #2d72d9;
    text-decoration: none;
  }
  a:hover {
    text-decoration: underline;
    color: #1a4e8a;
  }
  ```

- **Remove Underline / Add Hover Effects:**
  ```css
  nav a {
    text-decoration: none;
    transition: color 0.2s;
  }
  nav a:hover {
    color: #d94f2d;
  }
  ```

---

#### **Responsive Design (Intro)**

- **Why:**  
  Sites must look good on phones, tablets, and desktops.
- **How:**  
  Use **media queries** to change styling based on device size.

  ```css
  @media (max-width: 600px) {
    body {
      margin: 5px;
      font-size: 15px;
    }
    header, section {
      padding: 8px;
    }
    img {
      width: 50px;
    }
  }
  ```

This makes the page easier to read on small screens.

---

### **Summary**

CSS lets you control the look and feel of your website, from colors and fonts to layouts and responsiveness. Learning best practices early—like using external stylesheets, understanding the box model, and writing clear selectors—will help you avoid messy code and build beautiful, maintainable websites.

---

### **Activity Suggestions**

- **Try It Out:**  
  Give students a plain HTML page and ask them to style it using selectors, colors, and spacing.
- **Box Model Visual:**  
  Use browser DevTools (Inspect Element) to show how margin, border, and padding affect elements on a real page.
- **Responsive Challenge:**  
  Have students add a media query to make their site mobile-friendly (change background or font size on small screens).

---

## 4. Static vs. Dynamic Web Pages

---

#### **Static Pages**

- **Definition:**  
  Static web pages show the exact same content to every visitor, every time. They are built using only HTML and CSS (and possibly basic client-side JavaScript for UI effects, but no content changes based on user or time).
- **How They Work:**  
  When a browser requests a static page, the server simply sends back the file as-is—no changes, no customization.
- **Use Cases:**  
  - Simple information sites (e.g., portfolios, “About Us” pages)
  - Landing pages or marketing pages
  - Documentation sites

**Advantages:**
- Fast to load (no server processing)
- Easy to create and host (just upload files)
- Very secure (no backend to hack)

**Disadvantages:**
- Cannot personalize content for users
- Hard to update lots of pages (no automation)
- No interactivity beyond simple scripts

**Sample Static Page:**
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

---

#### **Dynamic Pages**

- **Definition:**  
  Dynamic web pages can change their content or appearance based on user input, date/time, data from a database, or other variables.
- **How They Work:**  
  Usually require a backend language (PHP, Node.js, Python, etc.) or frameworks (React, Django, etc.). The server generates a unique page for each request, or the browser updates content using JavaScript.

**Simple Frontend-Only Dynamic Simulation:**  
Even without a backend, you can simulate a "dynamic" effect using JavaScript on the client side:

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
**Explanation:**  
- The page changes its greeting based on user input, but the change only happens in the browser (no server/database involved).
- This is NOT a true dynamic site (no server-side logic or data fetching), but introduces the concept.

---

**True Dynamic Site Example (with Server-Side Scripting - Conceptual Only):**
- **How it works:**  
  User requests a page → server runs code to generate HTML (possibly using user data, database, etc.) → sends custom page to browser.

- **PHP Example (not runnable here, but for illustration):**
  ```php
  <?php
    $name = $_GET['name'] ?? 'Guest';
    echo "<h1>Welcome, $name!</h1>";
  ?>
  ```
  - If you visit `example.com/?name=Raj`, the page shows "Welcome, Raj!"
  - The content is generated on the server, not in the browser.

---

#### **Comparison Table**

| Feature        | Static Web Page           | Dynamic Web Page               |
| -------------- | ------------------------ | ------------------------------ |
| Content        | Fixed for all users      | Changes based on user/data     |
| Technologies   | HTML, CSS (maybe JS)     | HTML, CSS, JavaScript + backend (PHP, Node.js, etc.) |
| Interactivity  | Limited (UI only)        | Full (forms, user accounts, etc.) |
| Speed          | Very fast                | Slightly slower (processing time)|
| Security       | Very secure              | Needs extra care (can have vulnerabilities)|
| Use Cases      | Info pages, portfolios   | Social networks, e-commerce, dashboards |

---

#### **Why This Matters**

Understanding the difference between static and dynamic web pages helps you:
- Know when you just need HTML/CSS or when you’ll need to learn backend programming
- Prepare for JavaScript, APIs, and backend frameworks
- Architect web projects the right way from the start

---

#### **More Dynamic Interactivity (Frontend Only) Example: Display Current Time**

```html
<!DOCTYPE html>
<html>
<head>
  <title>Dynamic Time Example</title>
  <script>
    function showTime() {
      var now = new Date();
      document.getElementById('time').innerText = 'Current time: ' + now.toLocaleTimeString();
    }
    setInterval(showTime, 1000); // Update every second
  </script>
</head>
<body onload="showTime()">
  <h1>Welcome!</h1>
  <p id="time"></p>
</body>
</html>
```
- The content updates every second—demonstrating a simple dynamic effect with JavaScript.

---

#### **Activity Suggestions**

- **Hands-on:**  
  Have students modify the static page to change text/images, then try the dynamic example and personalize the greeting.
- **Discussion:**  
  Ask: What can you do with static HTML only? When would you need a dynamic page?
- **Extension:**  
  For advanced students, show a simple backend dynamic example using a free service like Replit or Glitch.

---

**Summary:**  
- **Static pages:** Great for simple sites, fast and secure, but limited.
- **Dynamic pages:** Needed for interactivity, personalized content, and modern web apps.
- **JavaScript bridges the gap** on the frontend, but true dynamic sites require backend programming.

---
