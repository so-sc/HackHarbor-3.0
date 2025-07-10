---
day: 9
title: "SQL and Open Source"
description: "SQL and Open Source"
---

# Day 9 - SQL and Open Source

<!-- Course content goes here -->

## Open Source

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

