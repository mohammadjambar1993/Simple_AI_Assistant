# 🧠 Simple AI Assistant Docker App that Remembers

This project is a **production-ready AI chat app** built with Docker Model Runner, Streamlit, and LangChain. It lets you talk to a local LLM running via Docker, or switch seamlessly to a large cloud-based model (like those on OpenRouter), all **while remembering your entire conversation history**. Each model will get the full chat context, even in moments when it wasn't participating in the conversation.



## ⭐ Features

1. Run local open-source LLMs with Docker Model Runner 🤖
2. Clean Streamlit chat interface with message history 💻
3. Seamless switch between local and cloud models 🕹️
4. Context-passing for memory-aware responses 💡
5. Fully containerized with Docker Compose  🐋



## ⚡️ Quick Start

### 1️⃣ Prerequisites

- [Docker Desktop](https://www.docker.com) installed and updated to current version.
- Docker Model Runner **enabled** in Docker Desktop (see [official docs](https://dockr.ly/4nT2saM))

### 2️⃣ Clone This Repo

<pre>
git clone 
simple_AI_assistant
</pre>

### 3️⃣ Create a `.env` File

Create a file named `.env` in the project root:

<pre>
LOCAL_BASE_URL=http://model-runner.docker.internal/engines/llama.cpp/v1
REMOTE_BASE_URL=https://openrouter.ai/api/v1
LOCAL_MODEL_NAME=ai/gemma3
REMOTE_MODEL_NAME=qwen/qwen3-30b-a3b
OPENROUTER_API_KEY=YOUR_OPENROUTER_API_KEY
</pre>

- Replace `YOUR_OPENROUTER_API_KEY` with your actual OpenRouter key.  
- Choose any local or remote model from:
  - 👉 [Docker Model Catalog](https://dockr.ly/4eTeLQl)
  - 👉 [OpenRouter](https://openrouter.ai)

### 4️⃣ Run the App

<pre>
docker compose up
</pre>

Then open your browser to:

http://localhost:8501  

✅ Your AI chat app is ready to use!

## 🗂️ Project Structure

```
.
├── app.py                # Streamlit chat app with LangChain
├── Dockerfile            # Container for running the app
├── docker-compose.yaml   # Defines app + model services
├── requirements.txt      # Python dependencies
└── .env                  # Environment variables (you create this)
```


## 🧩 How It Works

- The **llm** service in `docker-compose.yaml` uses Docker Model Runner to serve a local LLM (e.g. Gemma).
- The **ai-app** service is a Streamlit web app that:
  - Stores message history in session state
  - Passes the entire chat context to the LLM for memory-aware responses
  - Lets you switch between local and remote models with a simple checkbox


## 🚀 Customization

- **Change Local Model**  
  Edit `LOCAL_MODEL_NAME` and `LOCAL_BASE_URL` in your `.env`.

- **Change Remote Model**  
  Edit `REMOTE_MODEL_NAME`, `REMOTE_BASE_URL`, and your `OPENROUTER_API_KEY`.

- **Dependencies**  
  Add any extra Python packages to `requirements.txt`.


## 📚 Helpful Links

- 🐳 [Docker Model Runner Documentation](https://dockr.ly/4nT2saM)  
- 🔎 [Find Models in Docker Catalog](https://dockr.ly/4eTeLQl)  
- 🌐 [OpenRouter](https://openrouter.ai)  
- 🐍 [Streamlit](https://streamlit.io)  
- 🦜 [LangChain for Python](https://python.langchain.com)


## 🤝 Contributing

If you'd like to contribute, please create an issue and describe what you have in mind.
<br>
I'm trying to keep this repository as close as possible to the video workflow, but if you'd like to take it to the next level, I can split it in two.
