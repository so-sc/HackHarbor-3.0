---
day: 5
title: "API basics - intro to Postman"
description: "API basics - intro to Postman
And web requests"
---

# Day 5 - API basics - intro to Postman

# 📘 Topic 1: What Are APIs?

## 🤔 What is an API?

An **API** stands for **Application Programming Interface**.

It acts as a **messenger** between two software components, allowing them to communicate and exchange data.

> **Real-world analogy**: Think of a restaurant.
>
> * You (the user) sit at a table and order food.
> * The waiter (API) takes your request to the kitchen.
> * The kitchen (server) prepares the food and sends it back through the waiter (API).

![Waiter example for an API](https://github.com/so-sc/HackHarbor-3.0/blob/main/Tech/assets/api-waiter-visual.webp)

---

## 🧠 Why Are APIs Useful?

* 🔄 **Modularity** – Frontend & backend can be built separately
* 🧰 **Reusability** – One API can serve multiple apps (mobile, web)
* 🔒 **Security** – Control access to internal data/functions

---

## 🌐 Common API Use Cases

| Example App         | API Being Used       |
| ------------------- | -------------------- |
| Weather app         | OpenWeather API      |
| "Login with Google" | Google OAuth API     |
| Google Maps on app  | Google Maps API      |
| ChatGPT chatbot     | OpenAI API           |
| Translate feature   | Google Translate API |

---

## 🔌 Real API Example (Weather)

🌀 URL called by a weather app to get current temperature for a city:

```
GET https://api.openweathermap.org/data/2.5/weather?q=Delhi&appid=API_KEY
```

📦 The server responds with structured weather data in JSON format.

![Weather API Request-Response Flow](https://github.com/so-sc/HackHarbor-3.0/blob/main/Tech/assets/Weather%20API%20Response.png)

---

## 📬 Real API Example (Social Media Post)

To create a new post on a platform, the frontend might call:

```
POST https://api.myapp.com/posts
Body:
{
  "title": "Hello!",
  "body": "My first post",
  "userId": 7
}
```

![POST Request with JSON Body](https://github.com/so-sc/HackHarbor-3.0/blob/main/Tech/assets/POST%20Request%20with%20JSON%20Body.png)

---

# 📘 Topic 2: REST, HTTP Methods & Status Codes

## 🌍 What is REST?

**REST** stands for **Representational State Transfer**. It is an architecture style used for designing networked applications and APIs.

A RESTful API uses **resources**, identified by **URLs**, and standard **HTTP methods** to perform actions on them.

![RESTful API Resource Model](https://github.com/so-sc/HackHarbor-3.0/blob/main/Tech/assets/RESTful%20API%20Resource%20Model.png)

---

## 🔁 HTTP Methods (Verbs)

| Method   | Purpose              | Example Use Case  |
| -------- | -------------------- | ----------------- |
| `GET`    | Retrieve data        | View user profile |
| `POST`   | Create new data      | Submit a form     |
| `PUT`    | Update existing data | Edit a blog post  |
| `DELETE` | Remove data          | Delete a comment  |

---

## 🧪 Example: Post Resource

| Action          | Method   | URL        |
| --------------- | -------- | ---------- |
| Get all posts   | `GET`    | `/posts`   |
| Get single post | `GET`    | `/posts/1` |
| Create new post | `POST`   | `/posts`   |
| Update a post   | `PUT`    | `/posts/1` |
| Delete a post   | `DELETE` | `/posts/1` |

---

## 📟 HTTP Status Codes

| Code | Meaning               | Description                          |
| ---- | --------------------- | ------------------------------------ |
| 200  | OK                    | Request succeeded                    |
| 201  | Created               | Resource created successfully        |
| 400  | Bad Request           | Invalid or missing input from client |
| 401  | Unauthorized          | Authentication required              |
| 404  | Not Found             | Resource not found                   |
| 500  | Internal Server Error | Generic server failure               |

![HTTP Status Code Chart](https://github.com/so-sc/HackHarbor-3.0/blob/main/Tech/assets/HTTP%20Status%20Code%20Chart.png)

---

# 📘 Topic 3: Using Postman to Explore APIs Visually

## 🧰 What is Postman?

**Postman** is a popular API client that allows developers to test, debug, and interact with APIs without writing code.

You can send requests like `GET`, `POST`, `PUT`, and `DELETE` and view responses easily — great for learning and testing.

![Postman Interface Overview](https://github.com/so-sc/HackHarbor-3.0/blob/main/Tech/assets/Postman%20Interface%20Overview.png)

---

## 🧪 Try a Simple GET Request in Postman

1. Open Postman
2. Select `GET` from dropdown
3. Paste the URL:

   ```
   https://jsonplaceholder.typicode.com/posts/1
   ```
4. Click **Send**

Postman will show a JSON response like:

```json
{
  "userId": 1,
  "id": 1,
  "title": "...",
  "body": "..."
}
```

![GET Request in Postman](https://github.com/so-sc/HackHarbor-3.0/blob/main/Tech/assets/GET%20Request%20in%20Postman.png)

---

## ✍️ Try a POST Request with JSON Body

1. Select `POST` from method dropdown
2. URL: `https://jsonplaceholder.typicode.com/posts`
3. Go to **Body** tab → choose **raw** → select **JSON** from dropdown
4. Enter this JSON:

```json
{
  "title": "API Demo",
  "body": "Learning APIs with Postman",
  "userId": 1
}
```

5. Click **Send**

You’ll see a response with your submitted data and a new `id`.

![POST Request with Body in Postman](https://github.com/so-sc/HackHarbor-3.0/blob/main/Tech/assets/POST%20Request%20with%20Body%20in%20Postman.png)
---

## 📋 Headers to Know

* Most APIs expect a `Content-Type: application/json` header for POST/PUT
* Postman auto-adds this when you choose JSON in the body section

---

## 🔍 Bonus: Explore Other Test APIs

* `https://jsonplaceholder.typicode.com/` – Free fake REST API
* `https://reqres.in/` – Another great test API for practicing POST/PUT/DELETE

---

# 📘 Topic 4: Understanding JSON Body in API Requests

## 📦 What is JSON?

**JSON** stands for **JavaScript Object Notation**.
It is a lightweight data format used to exchange data between a client and a server in a structured and human-readable way.

JSON is commonly used in `POST`, `PUT`, and `PATCH` requests to send data to the server.

```json
{
  "name": "Alice",
  "email": "alice@example.com",
  "age": 21
}
```

![JSON Breakdown](https://github.com/so-sc/HackHarbor-3.0/blob/main/Tech/assets/JSON%20Breakdown.png)

---

## 🧠 JSON vs JavaScript Object

Though they look similar:

* JSON is a **string format**, not code
* All **keys and string values must be in double quotes**
* Cannot contain functions or comments

JavaScript:

```js
{ name: "Alice" } ✅
```

JSON:

```json
{ "name": "Alice" } ✅
```

---

## ✍️ Using JSON in a POST Request (Postman)

1. Set method to `POST`
2. URL: `https://jsonplaceholder.typicode.com/posts`
3. Body tab → raw → JSON
4. Example body:

```json
{
  "title": "Learning JSON",
  "body": "This is a test post",
  "userId": 99
}
```

5. Send the request

You’ll receive a response echoing your data, with a new `id`.

![POST Request with JSON Body in Postman](https://github.com/so-sc/HackHarbor-3.0/blob/main/Tech/assets/POST%20Request%20with%20JSON%20Body%20in%20Postman.mp4)

---

## 📌 Content-Type Header

Whenever you send JSON data, you should include this header:

```
Content-Type: application/json
```

Postman usually adds this automatically when JSON is selected.

---

# 📘 Topic 5: Using APIs with JavaScript (Fetch API)

## 🧠 Why Use JavaScript for APIs?

In real-world apps, JavaScript allows your web page to make API requests dynamically — without needing to refresh the page.

Most frontend projects use the **Fetch API** to send HTTP requests from JavaScript.

---

## 📦 Fetching Data from an API (GET Request)

Here’s how to fetch data from a public API:

```js
fetch('https://jsonplaceholder.typicode.com/posts/1')
  .then(response => response.json())
  .then(data => {
    console.log('Data received:', data);
  })
  .catch(error => {
    console.error('Error:', error);
  });
```

![Flow of Fetch GET Request](https://github.com/so-sc/HackHarbor-3.0/blob/main/Tech/assets/Flow%20of%20Fetch%20GET%20Request.png)

---

## ✍️ Sending Data to an API (POST Request)

```js
fetch('https://jsonplaceholder.typicode.com/posts', {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    title: 'New Post',
    body: 'This post was made using fetch',
    userId: 1
  })
})
  .then(response => response.json())
  .then(data => console.log('Created:', data))
  .catch(error => console.error('Error:', error));
```

![Fetch POST Flow](https://github.com/so-sc/HackHarbor-3.0/blob/main/Tech/assets/Fetch%20POST%20Flow.png)

---

## 🖼️ Showing API Data on a Webpage (Bonus)

You can update your HTML content using data from an API:

```html
<div id="output"></div>
<script>
fetch('https://jsonplaceholder.typicode.com/users/1')
  .then(res => res.json())
  .then(user => {
    document.getElementById('output').innerText = `Name: ${user.name}`;
  });
</script>
```

![Live Data Binding](https://github.com/so-sc/HackHarbor-3.0/blob/main/Tech/assets/Live%20Data%20Binding.png)

---

## 🧪 Tools for Debugging

* Use **browser console** to log request and response
* Check **Network tab** in DevTools to inspect the actual HTTP traffic

![Browser DevTools Network Tab](https://github.com/so-sc/HackHarbor-3.0/blob/main/Tech/assets/Browser%20DevTools%20Network%20Tab.png)

---

# 📘 Topic 6: Working with API Keys – Google AI Studio & OpenWeather

## 🔑 What is an API Key?

An **API Key** is a unique code used to identify and authorize your access to an API. It's like a password — don’t share it publicly.

Many public APIs (like OpenWeather or Google AI Studio) require you to sign up and get an API key to use their services.

![API Key Concept](https://github.com/so-sc/HackHarbor-3.0/blob/main/Tech/assets/API%20Key%20Concept.png)

---

## 🌦️ OpenWeather API – Get Weather by City

### 🔧 Get Your API Key:

1. Go to: [https://home.openweathermap.org/users/sign\_up](https://home.openweathermap.org/users/sign_up)
2. Sign up & log in
3. Copy your API key from the API Keys section

### 🌐 Try It in Postman:

```
GET https://api.openweathermap.org/data/2.5/weather?q=Delhi&appid=YOUR_API_KEY
```

### 💡 Tip:

* `q` → city name
* `appid` → your unique key

![OpenWeather in Postman](https://github.com/so-sc/HackHarbor-3.0/blob/main/Tech/assets/OpenWeather%20in%20Postman.png)

---

## 🤖 Google AI Studio API – Gemini Prompt API (Optional Demo)

### 🔧 Get Your API Key:

1. Go to: [https://makersuite.google.com/app/apikey](https://makersuite.google.com/app/apikey)
2. Log in with Google and generate an API key
3. Copy the key for use in headers

### 📬 Use in Postman:

* Method: `POST`
* URL: `https://generativelanguage.googleapis.com/v1beta/models/gemini-2.0-flash:generateContent`
* Headers:

```
Content-Type: application/json
X-goog-api-key: GEMINI_API_KEY
```

* Body (raw JSON):

```json
{
  "contents": [{ "parts": [{ "text": "Give me a joke about programmers." }] }]
}
```

![Postman Google AI Prompt Headers](https://github.com/so-sc/HackHarbor-3.0/blob/main/Tech/assets/Postman%20Google%20AI%20Prompt%20Headers.png)
![Postman Google AI Prompt Body](https://github.com/so-sc/HackHarbor-3.0/blob/main/Tech/assets/Postman%20Google%20AI%20Prompt%20Body.png)

---

## ⚠️ Important Notes

* Never expose keys in frontend JS or public GitHub repos
* Use `.env` files or server-side variables in real apps
* Regenerate keys if you suspect they’re leaked

---

# 📘 Topic 7: Simple API Integration in HTML + CSS + JavaScript

## 🎯 Goal

Create a basic webpage that fetches data from an API (like OpenWeather) and displays it using HTML, styled with CSS.

---

## 🧱 HTML + CSS Setup

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Weather App</title>
  <style>
    body { font-family: sans-serif; padding: 2rem; text-align: center; }
    #weather { margin-top: 2rem; font-size: 1.5rem; }
  </style>
</head>
<body>
  <h1>Weather App</h1>
  <input id="city" placeholder="Enter city name" />
  <button onclick="getWeather()">Get Weather</button>
  <div id="weather"></div>

  <script src="script.js"></script>
</body>
</html>
```

---

## ⚙️ JavaScript – Fetching Weather API

```js
function getWeather() {
  const city = document.getElementById("city").value;
  const key = 'YOUR_API_KEY';
  const url = `https://api.openweathermap.org/data/2.5/weather?q=${city}&appid=${key}&units=metric`;

  fetch(url)
    .then(res => res.json())
    .then(data => {
      const output = `🌡️ Temp in ${data.name}: ${data.main.temp}°C`;
      document.getElementById("weather").innerText = output;
    })
    .catch(err => {
      document.getElementById("weather").innerText = "City not found!";
    });
}
```

---

## 🧪 Try It Out

1. Save the HTML as `index.html`
2. Save the JS code in `script.js`
3. Replace `YOUR_API_KEY` with your OpenWeather key
4. Open `index.html` in browser
5. Type a city name and click **Get Weather**

---

## ⚠️ Note on API Limits

* Free API keys often have rate limits (60 calls/minute for OpenWeather)
* Always handle errors (e.g. wrong city name, no internet, key expired)

---

# 🧠 Express.js Basics with Examples

This guide introduces Express.js fundamentals and demonstrates core features like route handling, middleware, query parameters, and JSON communication.

---

## 📦 What is Express.js?

**Express.js** is a minimal and flexible Node.js web application framework that provides features for building web and API servers.

Install via npm:

```bash
npm install express
```

---

## 🚀 Setting Up an Express Server

```js
const express = require('express');
const cors = require('cors');
const app = express();

// Middleware
app.use(cors({ origin: '*' }));
app.use(express.json());

app.listen(8080, () => {
  console.log('Server is listening');
});
```

---

## 🌐 Defining Routes

### `GET /`

Responds with a simple string:

```js
app.get('/', (req, res) => {
  res.send('hello');
});
```

---

## 🔍 Using Query Parameters

### Example: `GET /test?name=PGS&age=30`

```js
// Middleware to check age
const isOld = (req, res, next) => {
  if (req.query.age >= 18) return next();
  return res.status(401).json({ msg: "nah too young" });
};

// Middleware to check name
const isPGS = (req, res, next) => {
  if (req.query.name == "PGS") return next();
  return res.status(401).json({ msg: "you aint pgs" });
};

// Route using both middlewares
app.get("/test", isOld, isPGS, (req, res) => {
  const name = req.query.name || "User";
  res.json({ msg: `Hello ${name}` });
});
```

---

## 📥 POST Requests with JSON Body

### `POST /testpgs`

Sends back a message with data from the body.

```js
app.post("/testpgs", (req, res) => {
  const { name, age } = req.body;
  res.json({ msg: `hello, ${name}, you are ${age} years old` });
});
```

Make sure to use `express.json()` middleware to parse JSON bodies.

---

## 🧪 Testing API Calls

### `test.js` (Node.js Script)

```js
const test = async () => {
  const res = await fetch("http://localhost:8080/testpgs", {
    method: "POST",
    headers: {
      'Content-type': "Application/json"
    },
    body: JSON.stringify({ name: "pgs", age: "30" })
  });

  const data = await res.json();
  console.log(data);
};

test();
```

### `test.html` (HTML + JS Client)

```html
<input type="text" id="test">
<button onclick="test()">click me</button>
<script>
const test = async () => {
  const val = document.querySelector("#test").value;
  const res = await fetch("http://localhost:8080/testpgs", {
    method: "POST",
    headers: {
      'Content-type': "Application/json"
    },
    body: JSON.stringify({ name: val, age: "30" })
  });

  const data = await res.json();
  alert(data.msg);
};
</script>
```

---

## ✅ Summary

| Feature          | Description                            |
| ---------------- | -------------------------------------- |
| `app.get()`      | Handles GET requests                   |
| `app.post()`     | Handles POST requests                  |
| `express.json()` | Parses incoming JSON                   |
| `req.query`      | Access URL query parameters (GET only) |
| `req.body`       | Access JSON payload (POST/PUT)         |
| `res.json()`     | Sends JSON response                    |
| Middleware       | Logic before final route handler       |

---

## 🔐 API Key Reminder

* Never expose your **API Keys** in public files.
* Secure server-side code.

---

## ⚠️ CORS and Errors

If accessing APIs from the browser, you might encounter:

**"CORS Policy: No 'Access-Control-Allow-Origin'..."**

* Use `cors()` middleware in Express to fix this.

---

## 📉 Rate Limiting

Servers often restrict how many requests a client can make:

* Error: `429 Too Many Requests`
* Use backoff and retries.

---

## 🛠️ Error Handling Flow

Use conditional branches and return JSON errors properly:

```js
if (!req.query.age) {
  return res.status(400).json({ error: "Age required" });
}
```

---

# 📘 Topic 10: Limitations of APIs & Practical Tips

## 🚧 Common API Limitations

### 1. **Rate Limits**

* Most APIs have a limit on the number of requests per minute/hour.
* Exceeding limits may lead to blocked requests.

---

### 2. **Authentication Requirements**

* Some APIs require OAuth, API Keys, tokens, etc.
* Insecure key usage (like in frontend code) can expose your API.

---

### 3. **CORS Restrictions**

* Some APIs block frontend requests from different origins (browser security).
* Error: `Access-Control-Allow-Origin` missing

---

### 4. **Unreliable or Inconsistent APIs**

* Free/test APIs may change response format or go down.
* Always check API documentation.

---

## 💡 Best Practices for Working with APIs

* ✅ Always read official documentation
* ✅ Use Postman to test before coding
* ✅ Handle errors (`.catch()`, 404s, invalid inputs)
* ✅ Respect rate limits and retry if necessary
* ✅ Store keys securely (use `.env`, don’t push to GitHub)
* ✅ Test with known working inputs before dynamic data

---

## 🧰 Tools to Help

* **Postman** – for testing requests
* **Hoppscotch** – lightweight online API tester
* **JSON Formatter** – makes JSON easier to read
* **Browser DevTools** – inspect requests and network calls

---
