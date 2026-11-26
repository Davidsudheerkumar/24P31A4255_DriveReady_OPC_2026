# Day 4 – EduPredictAI Student Support Agent

## Overview

Day 4 focuses on building an AI agent using LangChain tools, structured output, Pydantic validation, and Google Sheets integration.

For this practical task, I adapted the Sweet Crumbs Home Bakery tutorial into my own project, **EduPredictAI**.

EduPredictAI is an AI-powered student academic support assistant that helps teachers understand student performance, calculate marks percentages, classify academic results, and store student records.

## Objectives

- Understand how AI agents use tools.
- Create custom tools using LangChain's `@tool` decorator.
- Define structured student records using Pydantic.
- Extract student information from unstructured messages.
- Connect Google Sheets using `gspread`.
- Save student academic records automatically.
- Build an AI agent using LangChain's `create_agent`.
- Understand tool selection and agent execution traces.

## Technologies Used

- Python
- Google Colab
- LangChain
- LangChain Groq
- Groq LLM – `openai/gpt-oss-20b`
- Pydantic
- Google Sheets
- gspread

## Project Structure

```text
Day-4/
│
├── EduPredictAI_Day4.ipynb
└── README.md
```

## Implementation

### 1. Environment Setup

Installed the required Python packages:

- langchain
- langchain-groq
- gspread
- pydantic

Configured the Groq API key using Google Colab Secrets and initialized the language model.

Connected Google Colab to Google Sheets for storing student records.

### 2. Student Data Model

Created a Pydantic model named `StudentRecord`.

It contains the following fields:

- Name
- Subject
- Marks
- Attendance
- Date
- Academic concern

Pydantic helps validate the extracted student information.

### 3. Custom LangChain Tools

Created three custom tools using the `@tool` decorator.

**Tool 1: calculate_percentage**

Calculates the percentage of marks obtained by a student.

**Tool 2: classify_performance**

Classifies student performance using the following rules:

| Score | Classification |
|---|---|
| 0 | Dropout |
| 1–9 | Fail |
| 10–20 | Pass |

**Tool 3: log_student_record**

Validates and saves student academic records into Google Sheets.

### 4. Structured Output

Used `with_structured_output(StudentRecord)` to extract student details from unstructured text messages.

Tested the structured output using five different student messages.

### 5. Google Sheets Integration

Connected the application to Google Sheets using `gspread`.

Created a spreadsheet named:

`EduPredictAI Student Records`

The spreadsheet stores:

- Student name
- Subject
- Marks
- Attendance
- Date
- Academic concern
- Performance classification

### 6. AI Agent Creation

Created an AI agent using LangChain's `create_agent`.

The agent uses the three custom tools to calculate percentages, classify performance, and save confirmed student records.

Added a system prompt with instructions to provide simple responses and avoid inventing student information.

### 7. Tool Description Experiment

Created a temporary tool named `tool1` with the description `"does stuff"`.

Tested how an unclear tool name and description affect the agent's tool selection.

Compared it with descriptive tool names and docstrings.

### 8. Agent Execution Trace

Used `pretty_print()` to inspect the agent's execution messages.

Counted:

- Total model calls
- Total tool calls

This helped understand how the agent processes user requests and executes tools.

## Sample Test Cases

1. Calculate the percentage for 450 marks out of 500.
2. Classify a student who scored 15 out of 20.
3. Calculate the percentage for a student who scored 7 out of 20 and classify the result.
4. Extract student information from a natural-language message.
5. Save a confirmed student record into Google Sheets.

## Learning Outcomes

After completing Day 4, I learned:

- How to create custom LangChain tools.
- How an AI agent selects and executes tools.
- How to use Pydantic for structured data validation.
- How to extract structured information from natural-language messages.
- How to connect Google Sheets with Python.
- How to save records using an AI agent.
- How to inspect and count model and tool calls.

## Conclusion

In Day 4, I developed an EduPredictAI Student Support Agent by applying LangChain tools, structured output, Pydantic validation, and Google Sheets integration.

This practical helped me understand how AI agents can perform useful tasks by combining language models with external tools and structured data.
