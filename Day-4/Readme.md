# Day 4 – EduPredictAI Agent with Tools

## Project Overview

Day 4 focuses on building an AI-powered university admission assistant using LangChain, Groq, Pydantic and Google Sheets.

The EduPredictAI agent helps universities manage student admission enquiries, calculate academic percentages, classify student performance and store admission records.

## Technologies Used

- Python
- LangChain
- LangChain Groq
- Pydantic
- Google Colab
- Google Sheets
- gspread

## Tasks Completed

### 1. Creating Custom Tools with @tool

Converted two existing Python homework functions into LangChain tools.

- `calculate_percentage()` – Calculates student academic percentage.
- `classify_performance()` – Classifies student performance into Pass, Fail or Dropout.

Added clear function names, type hints and docstrings to help the AI agent select the correct tools.

### 2. Creating a Pydantic Model

Created an `AdmissionEnquiry` Pydantic class to represent university admission enquiries.

The model contains:

- Student Name
- Program / Branch
- Previous Academic Percentage
- Entrance Examination Score
- Enquiry Date
- Admission Question

### 3. Structured Output Testing

Used `llm.with_structured_output(AdmissionEnquiry)` to convert normal student messages into structured Python objects.

Tested the model with five different student messages containing admission information.

### 4. Google Sheets Integration

Connected Google Sheets using `gspread` and Google authentication.

Created a spreadsheet named **EduPredictAI Admission Enquiries** to store student admission information.

### 5. Creating the Logging Tool

Created `log_admission_enquiry()` using LangChain's `@tool`.

This tool:

- Validates admission information using Pydantic.
- Checks the required student details.
- Saves complete admission enquiries to Google Sheets.
- Returns a confirmation message after saving.

### 6. Tool Description Experiment

Renamed one tool to `tool1` and changed its docstring to `"does stuff"`.

Compared the vague tool description with the original descriptive tool name and docstring.

Observed how clear tool descriptions help improve tool selection.

Restored the original descriptive tool.

### 7. Reading the Agent Trace

Used `pretty_print()` to inspect the complete agent execution process.

Counted:
- Model calls
- Tool calls
- Tool execution results
- Final AI response

## Learning Outcomes

- Creating custom LangChain tools using `@tool`.
- Writing clear tool names and docstrings.
- Creating Pydantic data models.
- Generating structured LLM output.
- Connecting Python applications with Google Sheets.
- Creating AI agents using `create_agent()`.
- Understanding tool selection and agent execution traces.
- Handling tool errors and validating student information.

## Business Application

EduPredictAI provides an AI-powered admission enquiry management system for universities.

It helps organize student information, process academic details and maintain admission records using AI and Python.

## Conclusion

Successfully prepared the Day 4 practical implementation of an EduPredictAI admission assistant using LangChain tools, Pydantic structured output and Google Sheets integration.

This project demonstrates how AI agents can automate university admission enquiry management and academic information processing.
