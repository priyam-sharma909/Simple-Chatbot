# Simple Chatbot

A simple conversational AI chatbot built with **Python, LangChain, and Google's Gemini 2.5 Flash model**.

The chatbot maintains conversation history during the session, allowing the AI to use previous messages as context while responding to the user.

## Features

* 🤖 Powered by **Google Gemini 2.5 Flash**
* 🔗 Built using **LangChain**
* 💬 Maintains conversation history
* 🧠 Uses system, human, and AI messages
* 🌡️ Configurable model temperature
* 🚪 Supports an `Exit` command to end the conversation
* 🔐 API credentials loaded securely using environment variables

## Tech Stack

* **Python**
* **LangChain**
* **Google Gemini**
* **python-dotenv**

## Project Structure

```text
Simple-Chatbot/
│
├── chatbot.py
└── README.md
```

## Installation

### 1. Clone the repository

```bash
git clone https://github.com/priyam-sharma909/Simple-Chatbot.git
cd Simple-Chatbot
```

### 2. Create a virtual environment

```bash
python -m venv venv
```

Activate it on Windows:

```bash
venv\Scripts\activate
```

### 3. Install dependencies

```bash
pip install langchain-google-genai langchain-core python-dotenv
```

### 4. Set up your API key

Create a `.env` file in the project directory:

```env
GOOGLE_API_KEY=your_api_key_here
```

**Never commit your `.env` file or expose your API key publicly.**

## Usage

Run the chatbot with:

```bash
python chatbot.py
```

You can then enter messages in the terminal:

```text
YOU: Hello
AI: Hello! How can I help you today?

YOU: What can you do?
AI: I can help answer questions, explain concepts, and have a conversation with you.

YOU: Exit
```

Type `Exit`, `exit`, or `EXIT` to terminate the chatbot.

## How It Works

The chatbot uses LangChain message objects to maintain the conversation:

* `SystemMessage` — Defines the chatbot's behavior.
* `HumanMessage` — Stores the user's messages.
* `AIMessage` — Stores the chatbot's responses.

Each new user message and AI response is appended to `chat_history`. The complete history is then passed to the Gemini model on every invocation, allowing the chatbot to maintain context throughout the conversation.

## Model Configuration

The current model configuration is:

```python
model = ChatGoogleGenerativeAI(
    model="gemini-2.5-flash",
    temperature=0.5
)
```

A temperature of `0.5` provides a balance between consistent and creative responses.

## Future Improvements

Some possible improvements include:

* Add a web-based interface using Streamlit or Flask
* Add persistent conversation history
* Add streaming responses
* Add conversation reset functionality
* Add error handling
* Add support for different Gemini models
* Add chat history storage using a database

## License

This project is open source and available for learning and experimentation.
