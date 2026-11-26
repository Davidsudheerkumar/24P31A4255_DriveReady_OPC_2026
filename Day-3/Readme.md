# EduPredictAI – Day 3: Your First AI Agent

## Project Overview

This project is part of the **AI Agents Workshop – Day 3** practical.

In this task, I created an AI assistant called **EduPredictAI** using LangChain and the Groq API. The assistant helps teachers and college administrators understand student academic performance in simple English.

The practical focuses on understanding LLMs, system prompts, prompt chains, testing, and temperature experiments.

## Objectives

- Understand what an AI agent is.
- Create a system prompt for EduPredictAI.
- Connect a Large Language Model (LLM) using Groq.
- Build a prompt chain using LangChain.
- Create 10 test questions in a CSV file.
- Evaluate the AI assistant using automated tests.
- Improve the system prompt and compare results.
- Experiment with different temperature settings.
- Understand the difference between Python code, an LLM call, and an AI agent.

## Technologies Used

| Technology | Purpose |
|---|---|
| Python | Programming language |
| Google Colab | Cloud coding environment |
| LangChain | Prompt and chain creation |
| Groq API | Access to the AI model |
| GPT-OSS-20B | Language model |
| CSV | Store test questions and expected keywords |

## Project Structure

```text
EduPredictAI-Day3/
│
├── EduPredictAI_Day3.ipynb
├── tests.csv
└── README.md
```

## Implementation Steps

### 1. Install Required Packages

Installed LangChain Groq integration.

```python
%pip install -q langchain-groq
```

### 2. Import Libraries

Imported the required libraries for model connection, prompt creation, output parsing, and CSV testing.

```python
import os
import csv
import getpass

from langchain_groq import ChatGroq
from langchain_core.prompts import ChatPromptTemplate, MessagesPlaceholder
from langchain_core.output_parsers import StrOutputParser
```

### 3. Configure Groq API Key

Configured the Groq API key securely in Google Colab.

### 4. Create the AI Model

Created the language model using Groq.

```python
llm = ChatGroq(
    model="openai/gpt-oss-20b",
    temperature=0.3
)
```

### 5. Create the SYSTEM Prompt

Defined the system prompt to explain the responsibilities and rules of EduPredictAI.

The assistant is designed to:

- Explain student academic performance.
- Explain Pass, Fail, and Dropout predictions.
- Help identify students who may need academic support.
- Provide clear explanations in simple English.
- Avoid inventing student marks or results.
- Remind teachers that predictions are estimates.

### 6. Create the Prompt Chain

Used LangChain to connect the system prompt, user question, language model, and output parser.

```python
prompt = ChatPromptTemplate.from_messages([
    ("system", SYSTEM),
    MessagesPlaceholder("history"),
    ("human", "{question}")
])

chain = prompt | llm | StrOutputParser()
```

### 7. Test the AI Assistant

Asked EduPredictAI:

**Question:** What is EduPredictAI and how does it help teachers?

The assistant generates an answer based on the system prompt.

### 8. Create the Test Dataset

Created a `tests.csv` file containing 10 questions and their expected keywords.

Example:

| Question | Expected keyword |
|---|---|
| What is EduPredictAI? | student |
| What is its main purpose? | performance |
| Which categories can it predict? | Pass |
| How does it help teachers? | students |
| What type of data does it use? | historical |
| Can it identify students needing support? | support |
| Does it guarantee 100% accuracy? | estimate |
| Who can use EduPredictAI? | teachers |
| What does Dropout mean? | Dropout |
| What should teachers do after predictions? | review |

### 9. Run Automated Tests

Created a `run_tests()` function to:

- Read questions from `tests.csv`.
- Send each question to the AI assistant.
- Compare the generated answer with the expected keyword.
- Display PASS or FAIL.
- Calculate the overall pass rate.

**Pass Rate Formula:**

```text
Pass Rate = (Passed Tests / Total Tests) × 100
```

### 10. Improve the System Prompt

Added additional instructions to explain Pass, Fail, and Dropout clearly and remind teachers to verify predictions.

Rebuilt the prompt chain and ran the tests again to compare the original and improved pass rates.

### 11. Temperature Experiment

Changed the model temperature from `0.3` to `1.0`.

```python
llm_temp1 = ChatGroq(
    model="openai/gpt-oss-20b",
    temperature=1.0
)
```

Ran the same tests twice to observe whether the generated answers and test results changed.

**Observation:** Higher temperature can produce more varied responses. The actual pass rate may differ between runs.

## Business Job Classification

| Business Job | Type |
|---|---|
| Calculate student marks percentage | Plain Python Code |
| Explain student performance reports | One LLM Call |
| Analyze records, identify missing information, retrieve records, and prepare support recommendations | AI Agent |

## Learning Outcomes

After completing this practical, I learned:

1. How to create a system prompt for a specific application.
2. How to connect an LLM using the Groq API.
3. How to create a prompt chain using LangChain.
4. How to evaluate AI responses using test cases.
5. How to improve prompts based on test results.
6. How temperature affects AI-generated responses.
7. The difference between normal Python code, LLM calls, and AI agents.

## How to Run the Project

1. Open the `EduPredictAI_Day3.ipynb` notebook in Google Colab.
2. Install the required package.
3. Restart the runtime after installation.
4. Execute the notebook cells in order.
5. Enter your Groq API key when prompted.
6. Create the model and system prompt.
7. Run the AI assistant.
8. Generate `tests.csv` and execute the automated tests.
9. Compare the original and improved prompt results.
10. Run the temperature experiment.

## Conclusion

Through this Day 3 practical, I developed a basic AI-powered assistant for EduPredictAI using Python, LangChain, and Groq.

I learned how prompts guide an LLM, how chains connect different components, and how automated testing helps evaluate AI responses. I also explored how temperature changes response generation and understood where an AI agent can be useful in a student performance analysis application.

---

**Project:** EduPredictAI – Day 3  
**Workshop:** AI Agents Workshop  
**Environment:** Google Colab  
**Language:** Python
