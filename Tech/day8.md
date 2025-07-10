---
day: 8
title: "Docker and Open Source"
description: "Docker and Open Source"
---

# Day 8 - Docker and LLMs

<!-- Course content goes here -->

# Docker

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

-> Visit `http://localhost:8080` in browser

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

-> Visit `http://localhost:3000` to see Apache HTTP server running

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


# Open Source

**Before Class:**

 * Ensure students have Git and GitHub installed and set up

 * Make sure all students have GitHub accounts

 * Prepare a list of beginner-friendly open source repositories (e.g., from goodfirstissue.dev)

 * Test Wi-Fi access for cloning and pushing to repositories

## 1. What is Open Source?

* **Definition:**
  
  Open source is software that anyone can view, use, modify, and distribute. Its source code is publicly available.

* **Real-World Examples:**
  
  Linux, VS Code, Mozilla Firefox, React, Python, Blender.

* **Benefits of Open Source:**

  * Learn by reading real code
  * Build your portfolio
  * Collaborate with global developers
  * Help others and get help
  * Build credibility and network
    
**Analogy:**
Think of open source like Wikipedia: anyone can read it, contribute to it, and make it better for everyone.

---

## 2. How Open Source Works

* **The GitHub Ecosystem:**

  * **Repositories** = Project folders
  * **Commits** = Snapshots of changes
  * **Branches** = Safe spaces to work on features
  * **Issues** = To-do list or bug tracker
  * **Pull Requests (PRs)** = Proposals for merging code
  * **Forks** = Your own copy of a public project

* **Typical Contribution Flow:**

```
1. Fork a repository
2. Clone it to your computer
3. Create a new branch
4. Make changes
5. Commit & push changes
6. Create a Pull Request
```
---

## 3. First Contribution: Hands-On Demo

Guide students through their first contribution using this beginner repo:
🔗 [https://github.com/firstcontributions/first-contributions](https://github.com/firstcontributions/first-contributions)

### Step-by-Step:

1. **Fork the Repo:**

   * Go to the GitHub link
   * Click “Fork” (top-right)

2. **Clone Your Fork:**

```bash
git clone https://github.com/YOUR-USERNAME/first-contributions.git
cd first-contributions
```

3. **Create a Branch:**

```bash
git checkout -b add-your-name
```

4. **Make a Change:**

   * Open the `Contributors.md` file
   * Add your name to the list

5. **Commit & Push:**

```bash
git add Contributors.md
git commit -m "Add <Your Name> to Contributors list"
git push origin add-your-name
```

6. **Create a Pull Request:**

   * Go to your GitHub repo
   * Click “Compare & pull request”
   * Add a title and message, then submit

 Done! You’ve made your first open source contribution.

---

## 4. How to Find Beginner-Friendly Projects

* **Tags to Look For on GitHub:**

  * `good first issue`
  * `beginner friendly`
  * `help wanted`

* **Websites for Beginners:**

| Platform                                               | Description                 |
| ------------------------------------------------------ | --------------------------- |
| [goodfirstissue.dev](https://goodfirstissue.dev)       | Curated beginner issues     |
| [up-for-grabs.net](https://up-for-grabs.net)           | Projects with open issues   |
| [firsttimersonly.com](https://www.firsttimersonly.com) | For first-time contributors |
| [codetriage.com](https://www.codetriage.com)           | Daily issues to work on     |


---

## 5. Contribution Ideas Beyond Code

Open source isn’t only for developers. Beginners can also:

|Contribution Type| Examples                                |
| --------------- | ----------------------------------------- |
|  Documentation  | Improve READMEs, tutorials, wikis         |
|  Bug Reports    | Report bugs and help reproduce them       |
|  Translations   | Translate UI or docs into other languages |
|  Design         | Logo, branding, UI suggestions            |
|  Community      | Answer issues, welcome contributors       |

---

## 6. Best Practices for Open Source

* **Be respectful**: Open source is collaborative and global
* **Read the README**: It often includes contribution guidelines
* **Start small**: Fix a typo, add a comment, or suggest a minor improvement
* **Ask questions**: Most maintainers are open to helping
* **Use meaningful commit messages**
---

## Summary

 Today You Learned:

* What open source is and why it matters
* How GitHub repositories, branches, and PRs work
* How to contribute through a hands-on example
* Where to find beginner-friendly projects
* That everyone — not just coders — can contribute

---

## Optional Practice Tasks

* Customize and update your GitHub profile (add a bio, pinned repos)
* Star and follow 3 open source projects you’re interested in
* Try contributing to another beginner issue from [goodfirstissue.dev](https://goodfirstissue.dev)
* Join a community like [EddieHub](https://github.com/EddieHubCommunity) or [MLH](https://mlh.io)

---


