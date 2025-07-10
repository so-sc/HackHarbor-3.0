---
day: 8
title: "Docker and LLMs"
description: "Docker and LLMs"
---

# Day 8 - Docker and LLMs

<!-- Course content goes here -->

## Docker

**Before Class:**

 * Ensure Docker Desktop is installed and working on all systems

 * Verify that each student has internet access

 * Optional: Help students create a Docker Hub account

## 1. What is Containerization?

* **Problem Before Containers:**
  
  Before containers, developers often faced the frustrating **“it works on my machine”** issue. This happened because code that ran perfectly on one system would  often fail on another due to differences in operating systems, software versions, dependencies, or system configurations. These inconsistencies made debugging and deploying applications difficult and time-consuming. Teams would spend hours trying to replicate bugs caused not by faulty code, but by environment mismatches. Containers solve this problem by packaging the application along with all its dependencies into a single, portable unit that behaves the same on any system, ensuring consistency across development, testing, and production environments.

* **What are Containers?**
  
  Lightweight, standalone units that package code + dependencies + tools into one portable system.

* **Why Containers Matter:**

  * Consistency across devices
  * Isolation from host machine
  * Lightweight and fast
  * Easier to test, scale, and deploy

**Analogy:**

 Container = Application + Environment
 
 Docker = Shipping tool
 
 Host = The machine that runs containers

---

## 2. Introduction to Docker

* **What is Docker?**
  
  A containerization platform that automates the deployment of applications in containers.

* **Docker Ecosystem Overview:**

  * **Docker Engine** (runs containers)
  * **Docker Hub** (public repo for images)
  * **Dockerfile** (build instructions)

* **Basic Terminologies:**

| Term           | Description                               |
| -------------- | ----------------------------------------- |
| **Image**      | A read-only template to create containers |
| **Container**  | A running instance of an image            |
| **Dockerfile** | Instructions to build a custom image      |
| **Docker Hub** | Online registry for images (like GitHub)  |

---

## 3. Hands-On: Getting Started with Docker

* **Check Docker Installation:**

```bash
docker --version
docker info
```

* **Run Your First Container (hello-world):**

```bash
docker run hello-world
```

* **What It Does:**

  * Downloads image from Docker Hub
  * Creates and runs container
  * Prints confirmation message

* **Run a Web Server (NGINX):**

```bash
docker run -d -p 8080:80 nginx
```

➡ Visit `http://localhost:8080` in browser

---

## 4. Exploring Docker Commands


| Command                      | Description                             |
| ---------------------------- | --------------------------------------- |
| `docker ps`                  | List running containers                 |
| `docker ps -a`               | List all containers (including stopped) |
| `docker stop <container_id>` | Stop a running container                |
| `docker rm <container_id>`   | Remove a container                      |
| `docker images`              | Show downloaded images                  |
| `docker rmi <image_id>`      | Remove an image                         |
| `docker pull <image>`        | Download an image from Docker Hub       |
| `docker run <image>`         | Run a container from an image           |

**Sample Demo Task:**

```bash
docker run -d -p 3000:80 httpd
```

➡ Visit `http://localhost:3000` to see Apache HTTP server running

---

## Summary

Today You Learned:

* What containerization is and why it matters
* How Docker simplifies packaging and running applications
* Key Docker concepts: image, container, Dockerfile, Hub
* Ran real containers: `hello-world`, `nginx`, `httpd`

---

## Optional Practice Tasks

* Explore images on Docker Hub: [https://hub.docker.com](https://hub.docker.com)
* Run more containers:

```bash
docker run -d -p 5050:80 httpd  
docker run -it ubuntu bash
docker run alpine
```

* Try [Play with Docker](https://labs.play-with-docker.com) (browser-based Docker playground)
* Create a basic static site folder and serve it using NGINX

---


