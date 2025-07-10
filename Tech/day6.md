---
day: 6
title: "Cloud and Hosting"
description: "Introduction to Cloud Computing and Hands-on Deployment"
---

# Day 6 - Cloud and Hosting

## What is Cloud?

Cloud computing is the delivery of computing services—like servers, storage, and applications—over the internet. Instead of managing physical hardware, you rent what you need from a cloud provider, paying only for usage.

### Why Cloud?

- **Scalable**: Grows with your needs
- **Cost-efficient**: No upfront hardware costs
- **Reliable**: High availability and redundancy
- **Accessible**: Use services from anywhere

### Evolution of the Cloud

From personal data centers to shared infrastructure offered by tech giants like Amazon, Google, and Microsoft, the cloud evolved to solve problems of scale, cost, and speed.

---

## Cloud Deployment & Service Models

### Deployment Models

- **Public Cloud**: Shared infrastructure (e.g., AWS, GCP)
- **Private Cloud**: Dedicated for a single organization
- **Hybrid Cloud**: Combines public and private
- **Community Cloud**: Shared among similar organizations

### Service Models

- **IaaS**: Infrastructure as a Service (e.g., AWS EC2)
- **PaaS**: Platform as a Service (e.g., Firebase)
- **SaaS**: Software as a Service (e.g., Google Docs)

---

## Practical Cloud Usage

### ☁️ Cloud Storage

Store and retrieve data using:
- **Amazon S3**
- **Google Cloud Storage**
- Use case: File uploads, backups, hosting static files

### 💻 Virtual Machines

Create servers in the cloud:
- **Amazon EC2**, **Google Compute Engine**
- Use case: Full control over OS and environment

### ⚙️ Serverless Computing

Run backend code without managing servers:
- **AWS Lambda**, **Google Cloud Functions**
- Use case: APIs, automation tasks

### 📦 Containers

Package apps and run them anywhere:
- **Docker** on cloud platforms (AWS ECS, GCP Cloud Run)
- Use case: Microservices, reproducible dev environments

### 🌐 Networking Basics

- **DNS (Domain Name System)**: Converts names to IPs
- **CDN (Content Delivery Network)**: Faster content delivery
- **Load Balancers**: Distribute traffic across servers

---

## Domains, DNS & HTTPS

### 🔤 Domain Names & DNS

- **Domain**: The name of your website (e.g., `example.com`)
- **DNS**: Maps domain names to IP addresses
- Services like **Namecheap**, **GoDaddy**, or **Google Domains** let you buy domains and configure DNS.

### 🔐 SSL Certificates & HTTPS

- **HTTPS** encrypts data between the browser and server.
- **SSL Certificates** enable HTTPS and prove your site's identity.
- Services like **Let's Encrypt** or **Vercel/Netlify** offer free automatic SSL setup.

---

## Free Cloud Providers for Learning

- **Google Cloud Platform (GCP)** – $300 in free credits
- **AWS Free Tier** – 12-month free usage on selected services
- **Microsoft Azure** – $200 credit + free tier
- **Render, Vercel, Netlify** – Free static site and serverless hosting

---

## Mini Project: Deploy a Static Website on Vercel

Let’s deploy your HTML/CSS project using **Vercel**—a beginner-friendly platform.

### Step-by-Step Guide

1. **Prepare your project**

   - Create a folder with `index.html` and your `styles.css` or assets.

2. **Push to GitHub**

   - Initialize Git:
     ```bash
     git init
     git add .
     git commit -m "Initial commit"
     git remote add origin https://github.com/yourusername/project-name.git
     git push -u origin main
     ```

3. **Sign Up on [vercel.com](https://vercel.com)**

   - Use your GitHub account.

4. **Import Project**

   - Click **“Add New → Project”**.
   - Select your GitHub repo.

5. **Configure and Deploy**

   - No build steps needed for plain HTML/CSS.
   - Click **Deploy**.

6. **Done!**
   - Your site will be live at `https://your-project-name.vercel.app`.



