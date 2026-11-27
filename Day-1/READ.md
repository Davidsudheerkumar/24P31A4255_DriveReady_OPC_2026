# Day 1 – First API Integration with EduPredict AI 🤖

## Project: EduPredict AI
**AI-Powered University Admission Web Application**

### 📌 Objective

The objective of Day 1 was to understand how to connect a Python application with an AI model using the Groq API and build a basic AI assistant for the EduPredict AI project.

We learned how to send questions to an AI model, receive responses, control its behavior using system prompts, and measure token usage.

---

## 1. Technologies Used

- **Python** – Programming language
- **Google Colab** – Development environment
- **Groq API** – AI model API provider
- **OpenAI Python Library** – API client
- **GPT-OSS-20B** – AI model (`openai/gpt-oss-20b`)

## 2. API Setup and Authentication

Installed the OpenAI-compatible Python library:

```python
!pip install -q openai
```

Retrieved the Groq API key securely from Google Colab Secrets.

```python
from google.colab import userdata
from openai import OpenAI

client = OpenAI(
    api_key=userdata.get("GROQ_API_KEY"),
    base_url="https://api.groq.com/openai/v1"
)

print("API client connected successfully!")
```

**What we learned:**
- How to install and import the required library.
- How to securely access API keys.
- How to initialize an API client.
- How to connect Python with Groq.

## 3. First API Call

Created the first API request using the chat completions endpoint.

```python
response = client.chat.completions.create(
    model="openai/gpt-oss-20b",
    messages=[
        {
            "role": "system",
            "content": "You are EduPredict AI, an intelligent academic assistant."
        },
        {
            "role": "user",
            "content": "What is EduPredict AI and how does it help universities?"
        }
    ]
)

print(response.choices[0].message.content)
```

**What we learned:**
- System messages define the AI's behavior.
- User messages contain questions.
- API requests send messages to the model.
- The response object contains the generated answer.

## 4. EduPredict AI System Prompt

Created a custom system prompt to give the AI assistant information about our project.

The assistant was configured to understand these four core modules:

1. **GPA & Academic Performance Prediction** – Forecast student academic performance.
2. **Academic Branch Recommendation** – Recommend suitable academic branches.
3. **Scholarship Eligibility** – Evaluate merit-based and need-based scholarship eligibility.
4. **Analytics Dashboard** – Visualize student performance and institutional insights.

### Technology Stack Included

- Frontend: React.js, Vite, JavaScript, Tailwind CSS and Recharts.
- Backend: Python and FastAPI.
- Database: MongoDB.
- Machine Learning: Scikit-learn.
- Data Processing: Pandas and NumPy.

The system prompt also included rules to avoid unsupported information and explain concepts in simple English.

## 5. Temperature Testing

Tested different temperature values to understand how they affect AI responses.

```python
for temp in [0.2, 1.2]:

    response = client.chat.completions.create(
        model="openai/gpt-oss-20b",
        temperature=temp,
        messages=[
            {"role": "system", "content": SYSTEM},
            {
                "role": "user",
                "content": "Explain why EduPredict AI is useful for universities."
            }
        ]
    )

    print("Temperature:", temp)
    print(response.choices[0].message.content)
```

**Learning:**
- 0.2 produces more focused and consistent responses.
- 1.2 allows more variation and creativity.

## 6. Hallucination Testing

Tested whether the assistant generates unsupported information.

Example question:

"Does EduPredict AI currently support face recognition attendance?"

Expected behavior:

The assistant should explain that this information is not available in the project details instead of inventing an answer.

## 7. Conversation Memory Testing

Tested the difference between separate API calls and conversation history.

- Separate API calls do not automatically remember previous messages.
- Including previous messages in the `messages` list allows the model to use conversation history.

This helped us understand how conversational context works in AI applications.

## 8. Token Usage

Learned how to check the number of tokens consumed by an API request.

```python
print("Prompt Tokens:", response.usage.prompt_tokens)
print("Completion Tokens:", response.usage.completion_tokens)
print("Total Tokens:", response.usage.total_tokens)
```

**Learning:**
- Prompt tokens represent input processed by the model.
- Completion tokens represent generated output.
- Total tokens represent the combined usage.

## 9. Important Concepts Learned

| Concept | Description |
|---|---|
| API | Allows applications to communicate with external services. |
| API Key | Used for authentication. |
| OpenAI Client | Python library for making compatible API requests. |
| System Prompt | Defines AI behavior and instructions. |
| User Prompt | Contains the user's question. |
| Temperature | Controls response randomness. |
| Hallucination | Generating unsupported or incorrect information. |
| Conversation Memory | Providing previous messages as context. |
| Token Usage | Measures input and output tokens. |

## 10. Project Application

The knowledge gained on Day 1 will be used to develop an AI-powered assistant for EduPredict AI.

The assistant will eventually support:
- Explaining student academic performance predictions.
- Answering questions about branch recommendations.
- Explaining scholarship eligibility criteria.
- Providing information about the project.
- Supporting students, administrators and academic counselors.

**Note:** This Day 1 implementation is an API-based assistant prototype. It is not yet connected to the actual student database or trained prediction models.

---

## 🎯 Day 1 Learning Outcomes

Successfully explored the fundamentals of AI API integration using Python and Groq.

- Connected Python with Groq API.
- Created the first AI API request.
- Built a custom EduPredict AI system prompt.
- Explored temperature settings.
- Tested hallucination prevention.
- Understood conversation history.
- Checked API token usage.

### Conclusion

Day 1 provided a foundation for integrating Large Language Models (LLMs) into EduPredict AI. These concepts will help us gradually develop a more intelligent academic assistance system.

**Project:** EduPredict AI  
**Focus:** Python, AI API Integration and Prompt Engineering  
**Repository:** Davidsudheerkumar/EduPredictAI
