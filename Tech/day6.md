---
day: 6
title: "Cloud and Hosting"
description: "Introduction to Cloud Computing and Hands-on Deployment"
---

# Day 6 - Cloud and Hosting

## What is Cloud?

Cloud computing is the delivery of computing services—like servers, storage, and applications—over the internet. Instead of managing physical hardware, you rent what you need from a cloud provider, paying only for usage.

![Cloud Computing Overview](https://cf-assets.www.cloudflare.com/slt3lc6tev37/3YT0gya2bkUeuMrnGxhjAZ/4146c20c214cf001c74c0868ddfb9503/what-is-the-cloud.png)

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

![Deployment Models](https://www.cloudflare.com/img/learning/serverless/glossary/platform-as-a-service-paas/saas-paas-iaas-diagram.svg)

### Service Models

- **IaaS**: Infrastructure as a Service (e.g., AWS EC2)
- **PaaS**: Platform as a Service (e.g., Firebase)
- **SaaS**: Software as a Service (e.g., Google Docs)

---

## Practical Cloud Usage

### ☁️ Cloud Storage

Store and retrieve data using:

- **Amazon S3** – [S3 Docs](https://aws.amazon.com/s3/)
- **Google Cloud Storage** – [GCS Docs](https://cloud.google.com/storage)

Use case: File uploads, backups, hosting static files

---

### 💻 Virtual Machines

Create servers in the cloud:

- **Amazon EC2** – [EC2 Docs](https://aws.amazon.com/ec2/)
- **Google Compute Engine** – [GCE Docs](https://cloud.google.com/compute)

Use case: Full control over OS and environment

---

### ⚙️ Serverless Computing

Run backend code without managing servers:

- **AWS Lambda** – [Lambda Docs](https://aws.amazon.com/lambda/)
- **Google Cloud Functions** – [GCF Docs](https://cloud.google.com/functions)

Use case: APIs, automation tasks


---

### 📦 Containers

Package apps and run them anywhere:

- **Docker** – [Docker Docs](https://docs.docker.com/)
- **AWS ECS**, **GCP Cloud Run**

Use case: Microservices, reproducible dev environments

---

### 🌐 Networking Basics

- **DNS**: Converts names to IPs
- **CDN**: Faster content delivery
- **Load Balancers**: Distribute traffic across servers

---

## Domains, DNS & HTTPS

### 🔤 Domain Names & DNS

- **Domain**: The name of your website (e.g., `example.com`)
- **DNS**: Maps domain names to IP addresses

Use services like:

- [Namecheap](https://namecheap.com)
- [GoDaddy](https://godaddy.com)
- [Google Domains](https://domains.google/)

---

### 🔐 SSL Certificates & HTTPS

- **HTTPS** encrypts data between the browser and server
- **SSL Certificates** prove your site’s identity

Free options:

- [Let’s Encrypt](https://letsencrypt.org/)
- [Vercel](https://vercel.com), [Netlify](https://netlify.com)

---

## Free Cloud Providers for Learning

| Platform        | Free Tier                                                                           |
| --------------- | ----------------------------------------------------------------------------------- |
| Google Cloud    | $300 in credits + free tier – [GCP Free Tier](https://cloud.google.com/free)        |
| AWS             | 12-month free tier – [AWS Free Tier](https://aws.amazon.com/free/)                  |
| Microsoft Azure | $200 credit + free services – [Azure Free](https://azure.microsoft.com/en-us/free/) |
| Render          | Free static & backend hosting – [Render](https://render.com)                        |
| Vercel          | Great for frontend – [Vercel](https://vercel.com)                                   |
| Netlify         | Static hosting + serverless – [Netlify](https://netlify.com)                        |

---

## Mini Project: Deploy a Static Website on Vercel

Let’s deploy your HTML/CSS project using **Vercel**—a beginner-friendly platform.

### Step-by-Step Guide

1. **Prepare your project**

   Create a folder with:

   - `index.html`
   - `styles.css` or assets

2. **Push to GitHub**

   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git remote add origin https://github.com/yourusername/project-name.git
   git push -u origin main
   ```
