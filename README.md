# Academic Writing Assistant Hub

> **A lightweight web interface connecting students to three specialized Flowise-powered writing assistants.**

Designed to support students with structure, argumentation, and writer’s block in academic writing—without replacing critical thinking or producing full essays.

## Overview

The **Academic Writing Assistant Hub** provides targeted pedagogical support for university-level writing. Rather than generating text for the user, each assistant focuses on a specific cognitive difficulty associated with academic writing, such as "blank page paralysis" or structural incoherence.

### Core Philosophy
* **Specific Support:** Each bot has a distinct persona and toolset.
* **Pedagogical Alignment:** Based on real writing center methodologies (e.g., Reverse Outlining, Interview Method).
* **Academic Integrity:** Explicitly designed to avoid essay writing or source fabrication.

---

## The Assistants

The hub includes three distinct assistants, selectable via the sidebar:

### 1. Structure Architect
*Focus: Organizing thoughts and refining document flow.*
* **Reverse Outlining:** Analyzes existing drafts to extract the core logic.
* **Question-to-Claims:** Helps build a coherent structure from scratch.
* **Red Thread Analysis:** Ensures paragraph-thesis alignment and logical flow.

### 2. Kickstart Helper
*Focus: Overcoming writer's block and initiating the writing process.*
* **Interview Method:** Extracts ideas through conversation rather than staring at a blank page.
* **Cognitive Load Reduction:** Uses guided questioning to break down complex tasks.
* **Micro-step Suggestions:** Provides actionable, small next steps to get moving.

### 3. Argumentation Coach
*Focus: Strengthening logic and critical reasoning.*
* **Probing Chain-of-Thought (ProCoT):** Challenges user assumptions to deepen analysis.
* **Fallacy Detection:** Identifies logical gaps or weak arguments.
* **Transition Analysis:** Checks how well paragraphs connect and transition.

---

## Tech Stack

### Frontend
* **Core:** Static HTML, CSS, JavaScript (No complex build tools required).
* **Interface:** Sidebar module selection with a dynamic chat frame.
* **Integration:** Embedded `Flowise FullChatbot`.

### Backend (Flowise)
* **Engine:** [FlowiseAI](https://flowiseai.com) (Hosted on Render).
* **Model:** `gpt-4o-mini`.
* **Memory:** Buffer Window (Last 20 messages).
* **Moderation:** Enabled (OpenAI Moderation API).

#### Configuration
The frontend connects to specific Chatflows via the following IDs:

| Assistant | Chatflow ID |
| :--- | :--- |
| **Structure Architect** | `057b9b96-b93f-42ac-b91d-6b562b908d8b` |
| **Kickstart Helper** | `786e47a5-d8e1-4b3b-acbf-39e51222dfd8` |
| **Argumentation Coach** | `a5b9373b-7ab1-4f3d-8b48-770afa0f745b` |

---

## How It Works

1.  **User Selection:** The user clicks an assistant name in the sidebar.
2.  **Dynamic Loading:** The client-side JavaScript injects the `Flowise FullChatbot` component into the main chat frame.
3.  **Connection:** The chatbot initializes using the specific **Chatflow ID** associated with that assistant.
4.  **Processing:** All logic, prompting strategies, and memory management are handled remotely by the Flowise instance.

---

## Getting Started

Since this is a static site, you do not need to install `node_modules` or run a build server for the frontend.

### Prerequisites
* A web browser.
* Internet connection (to reach the Flowise backend).

### Installation
1.  Clone the repository:
    ```bash
    git clone [https://github.com/](https://github.com/)<yourname>/writing-assistant-ui.git
    ```
2.  Navigate to the folder:
    ```bash
    cd writing-assistant-ui
    ```
3.  Open `index.html` in your browser.

*(Note: Ensure the Flowise backend at `https://flowiseweb-kf7q.onrender.com` is active and reachable.)*

---

## Project Goals

* **Reduce Paralysis:** Help students get words on the page without doing the work for them.
* **Improve Structure:** Move beyond spell-checking to deep structural analysis.
* **Teach, Don't Cheats:** Foster long-term writing skills through scaffolding and questioning.

---

**License**
[MIT](LICENSE)

```
