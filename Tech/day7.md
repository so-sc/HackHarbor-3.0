# 🌟 Generative AI, LLM APIs, Prompt Engineering & AI Tools  
_For 2nd Year Engineering Students_

---

## 👩‍🏫 Mentor's Guide

### 🧠 Target Audience  
2nd-year engineering students with basic programming knowledge (C, Python, HTML/CSS). No prior AI/ML experience required.

### 🧭 Teaching Format  
- Each section can be covered in 30–45 minutes.  
- Focus on **visual explanations**, **hands-on prompts**, and **real-world case studies**.  
- Use tools like Google Colab, Replit, or Postman for coding and API demos.  
- Encourage peer learning and collaborative mini-projects.

### 📦 Tools Required  
- Internet browser  
- Code environment: VSCode, Colab, or Replit  
- Optional: Python/JavaScript setup  
- OpenAI/HuggingFace API keys (free tier works)  
- (Optional) Ollama for self-hosting LLMs

---

## 1️⃣ Introduction to Generative AI
### What You’ll Learn
- **Definition:**  
  Generative AI refers to models that *generate* new content such as text, images, music, or code. Instead of classifying or recommending, these models can *create* from learned patterns.
- **Examples in Action:**  
  - ChatGPT for text generation  
  - DALL·E or Midjourney for art creation  
  - GitHub Copilot for writing code  
- **Traditional AI vs. LLMs:**  
  - Traditional AI: specific, rule-based (e.g., detecting spam)  
  - LLMs: trained on large datasets to understand and generate natural language
- **Applications in Industry:**  
  - Education (essay generation, tutoring)  
  - Design (mockups, illustrations)  
  - Development (code generation, debugging)

🛠️ **Activity:**  
Group discussion: Name at least 3 AI tools or features you’ve interacted with (e.g., YouTube recommendations, Siri, Grammarly).

---

## 2️⃣ LLM APIs and Usage
### What You’ll Learn
- **What is an API?**  
  APIs (Application Programming Interfaces) act like messengers, allowing your application to communicate with LLMs hosted in the cloud.
- **Why APIs are Useful:**  
  - No need to train models from scratch  
  - Access powerful models like GPT-4, Claude  
  - Easily integrate into web or mobile apps
- **Popular LLM APIs:**  
  - **OpenAI API (ChatGPT)**  
  - **HuggingFace Inference API**  
  - **Cohere (language tasks)**  
  - **Ollama (run models locally)**
- **Basics of API Requests:**  
  - HTTP methods (GET, POST)  
  - API key authentication  
  - Sending JSON payloads and handling responses

🛠️ **Activity:**  
Send a basic prompt to OpenAI’s API using Python or Postman. Example: "Give me a fun fact about space."

---

## 3️⃣ Self-Hosting and Local LLMs
### What You’ll Learn
- **Why Run LLMs Locally?**  
  - Privacy (no cloud logging)  
  - No internet required  
  - Great for offline experimentation
- **Popular Tools for Local Hosting:**  
  - **Ollama:** Easy CLI-based setup for LLaMA2, Mistral  
  - **LM Studio:** UI-based model loading  
  - **KoboldAI:** Text adventure/roleplay generator
- **Hardware Requirements:**  
  - Min. 8 GB RAM (better with GPU)  
  - Models range from 3B to 13B parameters
- **Comparison Table:**  

  | Feature         | Self-Hosted       | Cloud/API         |
  |-----------------|-------------------|--------------------|
  | Privacy         | ✅ Yes             | ❌ Depends         |
  | Setup Effort    | 🛠️ High            | 🔌 Plug-and-play   |
  | Cost            | 💸 Once (power)    | 💸 Pay-per-use     |
  | Speed           | ⚡ Fast (local)     | 🌐 Depends on API  |

🛠️ **Activity:**  
Live demo: Run Llama2 using `ollama run llama2` and prompt it for a motivational quote.

---

## 4️⃣ Prompt Engineering Basics
### What You’ll Learn
- **What is a Prompt?**  
  A prompt is a carefully phrased input or instruction that guides the LLM to produce the desired output.
- **Prompting is Programming:**  
  Unlike traditional programming, prompting is about communicating with language. Good prompts = better outputs.
- **Writing Effective Prompts:**  
  - Be clear and specific  
  - Set context: “You are a Java teacher...”  
  - Ask for format: “Answer in bullet points.”

🛠️ **Activity:**  
Rephrase a poorly written prompt (“Tell me about AI”) into 3 better ones, targeting specific outputs.

---

## 5️⃣ Prompting Tips & Tricks
### What You’ll Learn
- **Role Prompting:**  
  Make the AI act as a specific persona: “You are a chef. Give me a recipe for biryani.”
- **Chain-of-Thought Prompting:**  
  Ask it to explain step-by-step: “Explain how to sort a list using bubble sort, step by step.”
- **Prompt Templates:**  
  Use scaffolds like:
  - “Summarize this article in 3 lines.”  
  - “Convert this text into an email.”  
  - “Explain this code in simple terms.”
- **Few-Shot Prompting:**  
  Provide examples in the prompt so the model understands your desired style.  
- **Common Mistakes to Avoid:**  
  - Vague queries  
  - Conflicting instructions  
  - Asking for too much in one go

🛠️ **Activity:**  
Design a few-shot prompt that teaches the model to convert text into “tweet-sized facts.”

---

## 6️⃣ Useful AI Tools & Websites (By Task)
### What You’ll Learn

#### 🎨 Design & UI
- [Lovable.so](https://www.lovable.so) – UI mockups via text  
- [V0.dev](https://v0.dev) – Converts prompts into React code  
- [Firebase Studio](https://studio.firebase.google.com) – AI for backend

#### 🤖 Chatbots & Coding
- **ChatGPT**, **Claude**, **Gemini** – General AI assistants  
- **GitHub Copilot** – Code completion in IDE

#### ✍️ Writing & Summarization
- **Jasper** – Marketing copy  
- **GrammarlyGO** – Writing refinement  
- **QuillBot**, **SMMRY** – Article summarization

#### 💻 Code Generation
- **SourceAI** – Converts natural language into code  
- **Copilot** – Embedded code suggestions

#### 🧪 Tool Evaluation Skills
- Check for privacy policy, explainability, free tier, and credibility of the tool.

🛠️ **Activity:**  
Use V0.dev to design a portfolio landing page using a prompt like: “Create a modern landing page for a CS student.”

---

## 7️⃣ Good Models vs. Bad Models (Task-Specific)
### What You’ll Learn
- **Model Performance by Task:**

  | Task           | Best Model        | Why                      |
  |----------------|-------------------|---------------------------|
  | Coding         | GPT-4, Claude     | Strong syntax & logic     |
  | Long Summary   | Claude            | Handles long input better |
  | Privacy Tasks  | Llama via Ollama  | Runs fully offline        |

- **Why Some Models Fail:**  
  - Hallucinations  
  - Limited context window  
  - Overfitting or underfitting

🛠️ **Activity:**  
Give same task to ChatGPT, Claude, and Gemini. Compare the results for accuracy and clarity.

---

## 8️⃣ Responsible AI Use
### What You’ll Learn
- **AI is Not Always Right:**  
  LLMs can make factual errors or biased assumptions. Always fact-check outputs.
- **Bias in LLMs:**  
  A model trained on biased internet data may reflect stereotypes.
- **Legal Considerations:**  
  - Copyright of AI-generated art or code  
  - Using AI for assignments: Is it ethical?
- **Proper Attribution:**  
  _e.g., “This essay summary was generated using ChatGPT, OpenAI, July 2025.”_

🛠️ **Activity:**  
Debate: “Should AI tools be allowed in exams or take-home assignments?”

---

## 9️⃣ Mini Project / Hands-On
### What You’ll Learn
- **Build Something Practical:**  
  Projects consolidate all knowledge into action. Use any LLM API or local model.
- **Project Ideas:**  
  - Resume enhancer  
  - Code explain bot  
  - Travel destination recommender  
  - AI-based joke generator

🛠️ **Prompt Engineering Challenge:**  
Use few-shot prompting to generate social media captions for different product categories.

---

## 🔟 Q&A & Further Resources
### What You’ll Learn
- **AI/ML Career Options:**  
  - Prompt Engineer  
  - ML Ops Engineer  
  - AI Research Intern  
  - AI Product Manager
- **Free Learning Resources:**  
  - [Google AI](https://ai.google)  
  - [Fast.ai](https://fast.ai)  
  - [YouTube: Fireship, 3Blue1Brown, Two Minute Papers]  
  - [GitHub: awesome-llm, awesome-chatgpt-prompts]
- **Q&A Session:**  
  Resolve doubts and collect feedback

🛠️ **Activity:**  
Each student shares 1 favorite tool or model and how they plan to use it.

---
