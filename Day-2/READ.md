# Day 2 – Prompt Engineering and Python Fundamentals

## Project: EduPredictAI

**Program:** DriveReady OPC 2026  
**Day:** 2  
**Project:** EduPredictAI – AI-Powered University Admission and Academic Decision-Support Assistant  
**Language:** Python  
**Environment:** Google Colab

---

## 1. Overview

Day 2 focused on understanding prompt engineering and important Python concepts used in building AI agents.

I applied these concepts to my project, **EduPredictAI**, an AI-powered university admission and academic decision-support application.

EduPredictAI aims to help universities with:

- Student academic performance and GPA prediction.
- Academic branch recommendations.
- Merit-based scholarship screening.
- Need-based scholarship screening.
- Student performance analytics and reports.

## 2. Objectives

The main objectives of Day 2 were:

1. Understand system prompts and prompt components.
2. Learn few-shot classification using examples.
3. Generate and process JSON data using Python.
4. Understand conversation history and memory management.
5. Build a business-specific chatbot structure using Python functions and system prompts.

---

## 3. Tasks Completed

### Exercise 1 – Prompt Parts

**Objective:** Understand how system prompt rules affect chatbot responses.

I created three important prompt components:

- **ROLE:** Defines the chatbot's identity.
- **FACTS:** Contains information about EduPredictAI.
- **RULES:** Defines the chatbot's behavior and limitations.

I tested the question:

`Can you deliver in 1 hour?`

I compared the responses using two prompts:

1. System prompt without RULES.
2. System prompt with RULES.

**Observation:**

Without rules, the chatbot demonstration produced a less restricted response. With rules, it avoided guaranteeing one-hour completion.

**Learning:** System prompt rules help control chatbot behavior and responses.

### Exercise 2 – Few-Shot Classifier

**Objective:** Understand message classification using examples.

I created three example messages and their categories.

| Example message | Category |
|---|---|
| I want to know my exam marks | Performance Prediction |
| Which branch should I choose? | Branch Recommendation |
| Am I eligible for a scholarship? | Scholarship Support |

I tested the classifier with five new student messages.

The categories included:

- Performance Prediction
- Branch Recommendation
- Scholarship Support
- General Enquiry

**Observation:** The classifier assigned categories to all five test messages using keyword-based Python conditions.

**Learning:** Examples help define the categories and expected classification behavior. This exercise used a simple keyword-based demonstration rather than an actual LLM few-shot classifier.

### Exercise 3 – JSON Output and Parsing

**Objective:** Understand how structured JSON data can be processed using Python.

I created a student service request containing the following fields:

- `name`
- `item`
- `qty`
- `date`
- `eggless`

Example JSON:

```json
{
    "name": "David",
    "item": "Performance Prediction",
    "qty": 1,
    "date": "2026-11-27",
    "eggless": false
}
```

I used:

- `json.loads()` to convert JSON text into a Python dictionary.
- `try/except` to handle invalid JSON.
- `json.JSONDecodeError` to identify parsing errors.

**Observation:** Valid JSON was successfully converted into a Python dictionary. Invalid JSON produced an error message that was handled using exception handling.

**Learning:** JSON is useful for exchanging structured information between applications and AI systems.

### Exercise 4 – Chat Memory

**Objective:** Understand how conversation history works and how memory limits affect a chatbot.

I implemented a simple conversation memory system using a Python list.

Configuration:

```python
MAX_TURNS = 2
```

I performed three conversation turns:

1. My name is David.
2. What is EduPredictAI?
3. Can it recommend branches?

The memory system retained only the latest two turns.

**Observation:** The first conversation was removed when the third turn was added. Therefore, the chatbot could not retrieve my name from the remaining conversation history.

**Learning:** Limited conversation memory can cause an AI assistant to lose older information.

### Exercise 5 – Build for My Own Business

**Objective:** Apply the concepts to my own project, EduPredictAI.

I created a service catalogue using a Python dictionary.

#### Service Catalogue

| Service | Description |
|---|---|
| Performance Prediction | Predict student academic performance and GPA |
| Branch Recommendation | Recommend suitable academic branches |
| Merit Scholarship | Screen students for merit-based scholarships |
| Need Scholarship | Screen students for need-based scholarships |
| Analytics | Generate student performance analytics and reports |

#### Python Function

I implemented the `get_service()` function with a docstring.

```python
def get_service(service_name):
    """
    Return information about an EduPredictAI service.

    Args:
        service_name (str): Name of the requested service.

    Returns:
        str: Description of the service or an error message.
    """

    return SERVICES.get(
        service_name,
        "Sorry, this service is not available."
    )
```

#### System Prompt

I created a dedicated system prompt defining:

- Chatbot identity.
- Project responsibilities.
- Academic assistance capabilities.
- Response rules.
- Limitations on guaranteeing academic results.

**Observation:** The service catalogue and function worked successfully. The function returned the description of the requested EduPredictAI service.

**Learning:** Python dictionaries, functions, docstrings, and system prompts help organize a business-specific AI assistant.

---

## 4. Technologies and Concepts Used

| Technology / Concept | Purpose |
|---|---|
| Python | Main programming language |
| Google Colab | Coding and execution environment |
| Dictionaries | Store service information |
| Functions | Organize reusable operations |
| Docstrings | Document Python functions |
| System Prompts | Define chatbot behavior |
| Few-Shot Examples | Demonstrate example-based classification |
| JSON | Represent structured data |
| `json.loads()` | Parse JSON data |
| `try/except` | Handle errors |
| Lists | Store conversation history |
| Memory Management | Limit stored conversation turns |

---

## 5. Final Verification

All five local practice exercises were checked using Python assertions.

| Exercise | Result |
|---|---|
| Prompt Parts | Passed |
| Few-Shot Classifier | Passed |
| JSON and JSON Parsing | Passed |
| Chat Memory | Passed |
| EduPredictAI Business Setup | Passed |

**Final result:** All five local practice checks passed successfully.

---

## 6. Challenges Faced

During the chatbot integration, I encountered the following issues:

- `NameError: name 'client' is not defined`
- Groq API authentication error (401 – Invalid API Key).

I identified that the first error occurred because the Groq client had not been initialized.

The second error occurred because the API rejected the supplied credentials.

The five local Python exercises were completed independently of the Groq API connection. Successful live LLM integration remains a separate step.

---

## 7. What I Learned

After completing Day 2, I learned:

1. How system prompts are organized into roles, facts, and rules.
2. How example-based classification can be demonstrated.
3. How to create and parse JSON data in Python.
4. How to handle invalid data using exception handling.
5. How conversation memory works.
6. How to manage a limited chat history.
7. How to create business-specific Python functions with docstrings.
8. How to organize chatbot services using dictionaries.

---

## 8. Project Application – EduPredictAI

The concepts learned during Day 2 provide a foundation for developing the EduPredictAI assistant.

The chatbot is intended to help students and university staff understand academic performance prediction, branch recommendations, scholarship screening, and student analytics.

These exercises establish the basic Python and prompt-engineering structure needed for future AI agent development.

---

## 9. Conclusion

Day 2 helped me understand the fundamentals of prompt engineering, structured data, Python functions, error handling, and chatbot memory.

I successfully completed five local practice exercises and applied the concepts to my own project, **EduPredictAI**.

This work provides a foundation for the next stage of AI agent development and LLM integration.

**Status: Day 2 – Five local practice exercises completed.**
