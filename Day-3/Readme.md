# Day 4 – EduPredictAI: LangChain Assistant

## Project Overview

EduPredictAI is an AI-powered university admission and academic decision-support assistant. It helps universities analyze student academic information, predict academic performance, recommend suitable branches, identify students needing academic support, and support scholarship screening.

On Day 4, I used LangChain and the Groq LLM to build a basic EduPredictAI assistant and test its responses.

## Technologies Used

- Python
- Google Colab
- LangChain
- LangChain-Groq
- Groq API
- CSV for testing

## 1. Your Business – EduPredictAI SYSTEM Prompt

Created a custom SYSTEM prompt for EduPredictAI instead of using the Sweet Crumbs bakery example.

The assistant is designed to:
- Answer university admission-related questions.
- Explain student academic performance prediction.
- Recommend suitable academic branches.
- Identify students who may need academic support.
- Explain merit-based and financial-need-based scholarships.

Added rules to prevent the assistant from inventing student records or guaranteeing admission and scholarships.

## 2. Your Tests – tests.csv

Created a CSV file containing 10 customer questions and their expected keywords.

| No. | Customer Question | Must Include |
|---|---|---|
| 1 | What is EduPredictAI? | university |
| 2 | How does EduPredictAI help students? | academic |
| 3 | Can EduPredictAI predict student performance? | performance |
| 4 | Does EduPredictAI recommend branches? | branch |
| 5 | Does it support scholarships? | scholarship |
| 6 | What is academic performance prediction? | predict |
| 7 | Can it identify students needing support? | support |
| 8 | Does EduPredictAI provide reports? | reports |
| 9 | Can it guarantee admission? | guarantee |
| 10 | Does EduPredictAI make final admission decisions? | final |

Implemented a Python testing function to:
- Read questions from tests.csv.
- Send each question to the LangChain model.
- Check whether the expected keyword appears in the answer.
- Display PASS or FAIL.
- Calculate the overall pass rate.

## 3. Improve – Prompt Improvement

Created an improved SYSTEM prompt (Prompt V2).

Changes made:
- Added explanations for academic predictions.
- Added instructions to mention insufficient information.
- Improved accuracy and reliability rules.
- Added human review recommendations for important decisions.
- Improved the assistant's response instructions.

Ran the same 10 tests again and compared Prompt V1 and Prompt V2 using their pass rates.

**Observation:** The actual improvement is evaluated using the test results.

## 4. Switch – Temperature Experiment

Changed the model temperature from 0.3 to 1.0.

Tested the same question twice:

"Explain how EduPredictAI helps universities."

Compared both AI-generated responses.

**Observation:**
- Temperature 0.3 generally produces more consistent responses.
- Temperature 1.0 allows more variation and creativity.
- The two responses may differ in wording and explanation.

## 5. Agent or Not – Task Classification

Identified three jobs in EduPredictAI and classified them.

| Job | Category | Explanation |
|---|---|---|
| Calculate student percentage | Plain Code | Uses mathematical calculations. |
| Explain student performance prediction | One LLM Call | Uses an LLM to generate an explanation. |
| Analyze student records, identify support needs and prepare reports using tools | Agent | Uses multiple steps and tools to complete a task. |

## Project Workflow

1. Install LangChain and LangChain-Groq.
2. Connect the Groq API key using Google Colab Secrets.
3. Initialize the ChatGroq model.
4. Create the EduPredictAI SYSTEM prompt.
5. Build the prompt template and chain.
6. Create tests.csv with 10 questions.
7. Execute the automated tests.
8. Improve the SYSTEM prompt.
9. Compare the test pass rates.
10. Change temperature to 1.0 and test twice.
11. Classify business tasks as Plain Code, LLM Call, or Agent.

## Learning Outcomes

After completing Day 4, I learned:

- How to create a business-specific AI assistant using LangChain.
- How to use SYSTEM prompts to control AI responses.
- How to create and execute automated CSV-based tests.
- How to improve prompts and compare their performance.
- How temperature affects AI-generated responses.
- The difference between Plain Code, One LLM Call, and an AI Agent.

## Conclusion

Successfully prepared an AI-powered EduPredictAI assistant using LangChain and Groq. Created a custom business prompt, a 10-question testing dataset, an improved prompt, and a temperature experiment. Also identified different tasks that can be implemented using traditional Python code, LLM calls, and AI agents.

---

**Project:** EduPredictAI  
**Day:** 4  
**Focus:** LangChain, Prompt Engineering, Testing and AI Agents  
**Environment:** Google Colab
