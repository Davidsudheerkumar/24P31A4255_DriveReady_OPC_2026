# Day 1 LLM Practical Assignments

## Project Overview

**EduPredictAI** is an AI-based student performance prediction project. It uses historical student academic data and marks to predict student outcomes and help educators identify students who may need additional support.

This practical explores how Large Language Models (LLMs) work and how to connect them using an API.

## Technologies Used

- Python
- Google Colab
- Groq API
- OpenAI Python Library
- Large Language Models (LLMs)

## Setup Instructions

### 1. Open Google Colab

Visit [Google Colab](https://colab.research.google.com/) and create a new notebook.

### 2. Install the required library

```python
!pip install -q openai
```

### 3. Create a Groq API Key

1. Visit [Groq Console](https://console.groq.com/keys).
2. Sign in to your account.
3. Create a new API key.
4. Copy the generated key.

### 4. Add the API Key to Google Colab

1. Open the Secrets section using the key icon in Colab.
2. Click Add new secret.
3. Set the name as `GROQ_API_KEY`.
4. Paste your Groq API key into the value field.
5. Enable notebook access.

**Security:** Never expose your API key in source code or upload it to GitHub.

### 5. Connect to the Groq API

```python
from google.colab import userdata
from openai import OpenAI

client = OpenAI(
    api_key=userdata.get("GROQ_API_KEY"),
    base_url="https://api.groq.com/openai/v1"
)

MODEL = "openai/gpt-oss-20b"

print("EduPredictAI API connected successfully!")
```

## Day 1 – Practical Tasks

### Task 1: Temperature Experiment

**Objective:** Understand how temperature affects AI-generated responses.

- Generate three EduPredictAI taglines using temperature 0.2.
- Generate another three taglines using temperature 1.2.
- Compare the responses.

**Learning:** Low temperature generally produces more predictable responses, while high temperature allows more variation and creativity.

### Task 2: Hallucination Experiment

**Objective:** Understand AI hallucinations.

Ask the chatbot:

> Does EduPredictAI guarantee that every student will pass?

Observe whether the AI generates unsupported claims.

**Learning:** AI can produce incorrect or unsupported information when it does not have sufficient facts.

### Task 3: No Memory Experiment

**Objective:** Understand how API conversation memory works.

Experiment A:
- First API call: My name is Ravi.
- Second API call: What is my name?

Experiment B:
- Send both messages together in a single messages list.
- Check whether the AI identifies the name.

**Learning:** Separate API calls do not automatically remember previous conversations. Conversation history must be provided again.

### Task 4: Token Experiment

**Objective:** Compare token usage in English and Telugu.

- Ask the same EduPredictAI-related question in English.
- Ask the same question in Telugu.
- Compare `response.usage.prompt_tokens`.

**Learning:** Different languages may consume different numbers of tokens for the same meaning.

### Task 5: Build an EduPredictAI Chatbot

**Objective:** Create a project-specific chatbot using facts and rules.

#### Five Project Facts

1. EduPredictAI is an AI-based student performance prediction project.
2. It uses historical student academic data and marks.
3. It predicts three outcomes: Pass, Fail, and Dropout.
4. It provides an interactive dashboard for educators.
5. It helps educators identify at-risk students and provide support.

#### Three Chatbot Rules

1. Answer questions in simple and understandable English.
2. Do not invent project features or unsupported information.
3. Never guarantee student results. Predictions are only guidance.

Test the chatbot using three questions:

1. What is EduPredictAI?
2. How does EduPredictAI identify at-risk students?
3. Can EduPredictAI guarantee that every student will pass?

## Learning Outcomes

After completing these experiments, I learned:

- How Large Language Models generate responses.
- How temperature affects AI creativity.
- What hallucinations are and why they occur.
- Why separate API calls do not automatically remember previous messages.
- How token usage changes between languages.
- How to build a simple AI chatbot using project-specific facts and rules.

## Conclusion

This practical helped me understand the basic concepts of Large Language Models and API integration. I also created a simple EduPredictAI chatbot using Python and the Groq API.

The experiments provided practical knowledge about AI response generation, memory, token usage, hallucinations, and chatbot development.

---

**Project:** EduPredictAI  
**Practical:** Day 1 – How LLMs Work and Your First API Call  
**Language:** Python  
**Platform:** Google Colab
