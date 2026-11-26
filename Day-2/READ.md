# EduPredictAI – Day 2: Prompts, Memory and Python Agents

## 📌 Project Overview

This repository contains my Day 2 practical assignments from the AI Agents workshop. I completed five hands-on experiments using Python, Google Colab, Groq API, and the OpenAI Python library.

All five experiments are adapted to my project, **EduPredictAI – AI-Based Student Performance Prediction System**.

The purpose of these practicals is to understand how Large Language Models (LLMs) work with prompts, examples, structured data, conversation history, and Python functions.

## 🎯 Objectives

- Understand how system prompts and rules control AI responses.
- Learn few-shot prompting for message classification.
- Extract student information in JSON format.
- Understand chatbot memory using conversation history.
- Build a project-specific EduPredictAI chatbot using Python.

## 🛠️ Technologies Used

- **Python** – Programming language
- **Google Colab** – Cloud-based coding environment
- **Groq API** – Access to a language model
- **OpenAI Python Library** – API communication
- **JSON** – Structured data handling

## 🧪 Practical Tasks

### Task 1: Prompt Parts – Testing Chatbot Rules

**Objective:** Understand how system prompt rules influence AI responses.

**Work performed:**
- Created a system prompt for EduPredictAI.
- Tested the chatbot without specific rules.
- Added rules to prevent unsupported promises and guaranteed results.
- Compared both responses.

**Learning Outcome:** System prompt rules help control chatbot behaviour and reduce unsupported claims.

### Task 2: Few-Shot Classification

**Objective:** Build a message classifier using three examples and test it on five new messages.

**Categories used:**
1. Academic
2. Performance
3. Scholarship
4. Technical

**Work performed:**
- Provided three example messages with their categories.
- Used these examples to guide the AI classifier.
- Tested five new student-related messages.
- Observed the classification results.

**Learning Outcome:** Few-shot prompting helps an AI model understand a task through examples without additional model training.

### Task 3: JSON Data Extraction

**Objective:** Extract student information from normal text and convert it into structured JSON data.

**Fields extracted:**
- Student Name
- Subject
- Marks
- Attendance
- Exam Date
- Student Concern

**Work performed:**
- Created a prompt to extract student details.
- Asked the AI to return valid JSON.
- Used Python's `json.loads()` to convert the response into a Python dictionary.
- Used `try-except` to handle invalid JSON.

**Learning Outcome:** JSON makes it easier for Python applications to process information in a structured format.

### Task 4: Memory Experiment

**Objective:** Understand how conversation history helps a chatbot remember previous information.

**Work performed:**
- Set `MAX_TURNS = 2`.
- Entered a student's name and other details.
- Continued the conversation for three turns.
- Asked the chatbot to remember the student's name.
- Observed how older messages can be removed from the conversation history.

**Learning Outcome:** LLM API calls do not automatically remember previous conversations. The application must send relevant conversation history with each request.

### Task 5: Building an EduPredictAI Chatbot

**Objective:** Build a simple project-specific chatbot using Python.

**Work performed:**
- Created a Python dictionary containing Pass, Fail, and Dropout information.
- Created a Python function with a docstring.
- Designed a system prompt specifically for EduPredictAI.
- Added chatbot rules and project information.
- Tested the chatbot using three student-related questions.

**Learning Outcome:** Python dictionaries, functions, docstrings, and system prompts can be combined to build a basic project-specific AI chatbot.

## ▶️ How to Run

1. Open [Google Colab](https://colab.research.google.com/).
2. Open `EduPredictAI_Day2_LLM_Practicals.ipynb`.
3. Install the required package:

   ```python
   !pip install -q openai
   ```

4. Create a Groq API key from [Groq Console](https://console.groq.com/keys).
5. Add the API key to Google Colab Secrets using the name `GROQ_API_KEY`.
6. Run the API connection cell.
7. Execute all five practical tasks one by one.
8. Observe the outputs and save screenshots.

**Note:** Never share your API key or upload it to GitHub.

## 📚 Key Learnings

Through these practical assignments, I learned:

- Prompt engineering and system instructions.
- Few-shot learning using examples.
- Structured information extraction using JSON.
- Conversation memory and history management.
- Python dictionaries and functions.
- Connecting Python applications to an LLM API.
- Building a basic project-specific AI chatbot.

## 🔗 Project Context

**EduPredictAI** is an AI-based student performance prediction project that uses historical academic data to predict student outcomes such as Pass, Fail, and Dropout. It aims to help educators identify students who may need additional academic support.

The chatbot developed in these practicals is a learning prototype. It is not yet integrated with the actual EduPredictAI machine-learning model or student database.

## 👨‍💻 Author

**David Sudheer Kumar**

B.Tech – Computer Science and Engineering (AI & ML)

## 📝 Conclusion

I successfully worked on five practical experiments as part of Day 2 of the AI Agents workshop. These experiments helped me understand prompt engineering, few-shot classification, JSON extraction, chatbot memory, and Python-based AI chatbot development using the Groq API.

This practical work improved my understanding of how LLMs can be used in real-world applications like EduPredictAI.
