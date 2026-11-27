# EduPredictAI – Day 5: Knowledge Base and AI Agent

## Project Overview

Day 5 focuses on improving the EduPredictAI assistant by adding a knowledge base, a retrieval search tool, and conversation memory.

The assistant uses project-specific information to answer questions about EduPredictAI and avoids making up information that is not available in its knowledge base.

## Objectives

1. Store 15–20 EduPredictAI facts in a ChromaDB collection.
2. Create a search tool to retrieve relevant project information.
3. Integrate the search tool into the Day 4 LangGraph agent.
4. Add a checkpointer to maintain conversation history.
5. Test the agent using two different thread IDs.
6. Test questions outside the knowledge base.
7. Run automated tests and calculate the pass rate.

## Technologies Used

- Python
- Google Colab
- ChromaDB
- LangChain
- LangGraph
- Groq LLM
- InMemorySaver

## Tasks Completed

### 1. Created the EduPredictAI Knowledge Base

Created a ChromaDB collection named `edupredictai_knowledge`.

Added 18 individual facts about the EduPredictAI application.

Each fact is stored as a separate document (one fact per chunk).

**Topics covered:**

- Project introduction and purpose
- Student academic information
- Academic performance prediction
- Pass, Fail, and Dropout classification
- Branch and class placement recommendations
- Merit-based scholarship screening
- Financial-need-based scholarship screening
- Student academic support
- University user roles
- Technology stack
- Dashboards, analytics, and reports

### 2. Created the Search Tool

Created a LangChain tool named:

`search_edupredictai_knowledge`

The tool uses ChromaDB similarity search to retrieve relevant information from the knowledge base.

It includes a docstring describing the topics covered by the knowledge base.

### 3. Integrated the Search Tool into the Agent

Integrated the knowledge retrieval tool into the EduPredictAI LangGraph agent.

The agent uses the Groq language model and the following tools:

- `search_edupredictai_knowledge`
- `calculate_percentage` (if loaded from Day 4)
- `classify_performance` (if loaded from Day 4)
- `log_student_record` (if loaded from Day 4)

### 4. Added Conversation Memory

Implemented `InMemorySaver` as the agent checkpointer.

Used different thread IDs to test conversation memory:

- `student_thread_1`
- `student_thread_2`

The agent should remember information within the same thread and keep separate conversations isolated.

### 5. Tested Unknown Questions

Tested questions about information not included in the knowledge base, such as:

- Exact scholarship amounts
- Minimum family income requirements
- Unspecified scholarship eligibility cutoffs

Added system rules to prevent unsupported answers.

When information is unavailable, the assistant should explain that it needs to be checked with the university admissions team.

### 6. Automated Testing

Created an automated test section with eight checks:

1. Knowledge base contains 18 facts.
2. Search tool retrieves classification information.
3. Agent explains the project purpose.
4. Agent explains G3 classification rules.
5. Agent explains scholarship screening.
6. Agent remembers information in the same thread.
7. Agent keeps different threads separate.
8. Agent handles unknown information safely.

The notebook calculates the number of passed tests, failed tests, and overall pass percentage.

## Performance Evaluation

**Target pass rate:** 80% or above.

The actual pass rate is calculated when the automated test cell is executed.

Formula:

`Pass Rate = (Passed Tests / Total Tests) × 100`

## Conclusion

Successfully developed an EduPredictAI knowledge-based AI assistant using ChromaDB, LangChain, LangGraph, and Groq.

The implementation adds project-specific information retrieval, conversation memory, separate thread handling, and safeguards against unsupported answers.

This completes the Day 5 knowledge base and agent development tasks, with automated testing included for evaluation.
