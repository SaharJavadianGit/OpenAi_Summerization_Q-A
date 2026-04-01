# OpenAi_Summerization_Q-A
# 🤖 LLM Text Summarization and Chatbot using OpenAI GPT Models

------------------------------------------------------------------------

# 📌 Project Overview

This project demonstrates how **Large Language Models (LLMs)** can be
used for two common Natural Language Processing tasks:

1️⃣ **Text Summarization**\
2️⃣ **Conversational Question & Answer Chatbot**

Both tasks are implemented using **OpenAI GPT models** through the
OpenAI API.

⚠️ The API key has intentionally been removed from the code for security
reasons.

Unlike many open-source NLP projects that rely on **Hugging Face
transformer models**, this project specifically uses **OpenAI hosted GPT
models**, which run in the cloud and are accessed via API calls.

------------------------------------------------------------------------

# 🧠 What are Large Language Models (LLMs)?

Large Language Models are deep learning models trained on massive
amounts of text data to understand and generate human-like language.

They can perform many tasks including:

-   Text summarization
-   Question answering
-   Chatbots
-   Translation
-   Code generation
-   Content creation

Examples of LLM providers include:

-   OpenAI (GPT models)
-   Hugging Face Transformers
-   Google Gemini
-   Anthropic Claude

This project specifically uses **OpenAI GPT models**, which are
**different from Hugging Face models** because:

  OpenAI Models            Hugging Face Models
  ------------------------ --------------------------
  Hosted via API           Usually run locally
  Managed infrastructure   User manages model
  Easy to integrate        Requires model downloads
  Paid API usage           Many free models

------------------------------------------------------------------------

# 🚀 Project Features

This project contains two main components:

### 1️⃣ LLM Text Summarization

A text document is provided to the GPT model and the model generates a
**short summary of the text**.

The summarization task:

-   Reads text from a file
-   Sends the text to the GPT model
-   Returns a concise summary
-   Generates a topic for the summarized text

Example:

Input: Long article text\
Output: 3 sentence summary + topic

------------------------------------------------------------------------

### 2️⃣ LLM Chatbot (Question & Answer System)

The second part of the project implements a **simple conversational
chatbot** using GPT.

Features:

-   Accepts user input
-   Sends conversation history to the LLM
-   Generates intelligent responses
-   Maintains conversation context

The chatbot continues running until the program is stopped.

------------------------------------------------------------------------

# ⚙️ Technologies Used

-   Python
-   OpenAI API
-   GPT Models (OpenAI)
-   Jupyter Notebook

Python libraries used:

-   openai
-   json (optional)
-   standard Python libraries

------------------------------------------------------------------------

# 📂 Project Structure

llm-openai-project/

│ ├── Project3.ipynb ├── README.md ├── History_of_Pizza.txt │ └──
requirements.txt

------------------------------------------------------------------------

# 🔐 API Key Security

The OpenAI API key is **not included in the repository** for security
reasons.

To run this project, create an environment variable:

``` bash
export OPENAI_API_KEY="your_api_key_here"
```

Or inside Python:

``` python
from openai import OpenAI
client = OpenAI()
```

Never upload API keys to GitHub.

------------------------------------------------------------------------

# ▶️ Running the Project

1️⃣ Install dependencies

``` bash
pip install openai
```

2️⃣ Open the notebook

``` bash
jupyter notebook Project3.ipynb
```

3️⃣ Run all cells to execute:

-   LLM text summarization
-   LLM chatbot interaction

------------------------------------------------------------------------

# 🧾 Code Explanation

## 1️⃣ Importing the OpenAI Client

``` python
from openai import OpenAI
client = OpenAI()
```

This initializes the OpenAI client which allows communication with GPT
models via API.

------------------------------------------------------------------------

## 2️⃣ Text Summarization with GPT

The program reads a text file:

``` python
with open("History_of_Pizza.txt", "r", encoding="utf-8") as f:
    text = f.read()
```

The text is then sent to the GPT model:

``` python
response = client.responses.create(
    model="gpt-4.1-mini",
    input=f"Summarize this text in 3 sentences and choose a topic for that:\n\n{text}"
)
```

The model:

-   Reads the text
-   Understands the context
-   Generates a short summary
-   Suggests a topic

The result is printed:

``` python
print(response.output_text)
```

------------------------------------------------------------------------

## 3️⃣ Chatbot Implementation

A conversation list stores the dialogue history:

``` python
messages = []
```

The program continuously receives user input:

``` python
user_input = input("You: ")
```

User messages are appended to the conversation history:

``` python
messages.append({"role": "user", "content": user_input})
```

The conversation is sent to the GPT model:

``` python
response = client.responses.create(
    model="gpt-4.1-mini",
    input=messages
)
```

The model generates a reply:

``` python
reply = response.output_text
print("Bot:", reply)
```

The response is added back to the conversation memory so the chatbot
maintains context.

------------------------------------------------------------------------

# 📊 Key Takeaways

This project demonstrates how LLMs can be used for:

-   Text summarization
-   Conversational AI
-   Natural language understanding

Using OpenAI models makes it easy to integrate powerful language models
without needing heavy local hardware.

------------------------------------------------------------------------

# 🔮 Future Improvements

Possible improvements include:

-   Adding a web interface
-   Memory-based chatbot
-   Retrieval Augmented Generation (RAG)
-   Using vector databases
-   Multi-document summarization

------------------------------------------------------------------------

# 👨‍💻 Author

LLM Project\
Text Summarization & Chatbot using OpenAI GPT Models

------------------------------------------------------------------------

⭐ If you found this project useful, consider giving it a star on
GitHub!
