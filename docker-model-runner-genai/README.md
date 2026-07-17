# 🚀 Docker Model Runner + Python GenAI (WSL2)

A hands-on project demonstrating how to build and run a local AI chatbot using **Docker Model Runner**, **Python**, **Flask**, and **WSL2** without using any cloud-based LLM services.

Everything runs locally on your machine.

---

# 📖 Project Overview

This project demonstrates how to integrate Docker Model Runner with a Flask web application using Docker's OpenAI-compatible API.

It also documents the complete troubleshooting journey—from networking issues to application deployment—making it easy for anyone to reproduce the setup.

---

# 🏗️ Architecture

```

Browser
│
▼
Flask Application (Port 7001)
│
▼
Docker Model Runner
(OpenAI Compatible API)
│
▼
SmolLM2 (135M-Q4_K_M)

```

---

# 🛠 Tech Stack

- Docker Desktop
- Docker Model Runner
- Python 3.10+
- Flask
- WSL2 (Ubuntu 22.04)
- Local LLM
- OpenAI Compatible API

---

# 📋 Prerequisites

- Windows 11
- Docker Desktop (Latest)
- WSL2 Ubuntu
- Python 3.10+
- Git

---

# 📂 Project Structure

```

docker-model-runner-genai/
│
├── app.py
├── Dockerfile
├── docker-compose.yml
├── requirements.txt
├── requirements.lock.txt
├── README.md
├── .env.example
├── .gitignore
├── static/
├── templates/
└── screenshots/

```

---

# 🚀 Step 1 – Verify Docker

```bash
docker version
```

Expected Output

```text
Client:
 Version: 29.x.x

Server:
 Docker Desktop
```

---

# 🚀 Step 2 – Verify Docker Model Runner

```bash
docker model status
```

Expected Output

```text
Docker Model Runner is running

BACKEND
llama.cpp
```

---

# 🚀 Step 3 – Pull the Model

```bash
docker model pull ai/smollm2:135M-Q4_K_M
```

Verify

```bash
docker model list
```

Expected Output

```text
docker.io/ai/smollm2:135M-Q4_K_M
```

---

# 🚀 Step 4 – Test the Model

```bash
docker model run smollm2:135M-Q4_K_M
```

Example

```text
> What is Docker?

Docker is a platform for building, shipping and running applications inside containers.
```

---

# 🚀 Step 5 – Clone Repository

```bash
git clone https://github.com/sandeepmohapatra177/AIOPs.git

cd AIOPs/docker-model-runner-genai
```

---

# 🚀 Step 6 – Create Virtual Environment

```bash
python3 -m venv .venv

source .venv/bin/activate
```

---

# 🚀 Step 7 – Install Dependencies

```bash
pip install -r requirements.txt
```

---

# 🚀 Step 8 – Configure Environment Variables

```bash
export PORT=7001

export LLAMA_URL=http://localhost:12434/engines/v1

export LLAMA_MODEL=smollm2:135M-Q4_K_M
```

Verify

```bash
echo $PORT
echo $LLAMA_URL
echo $LLAMA_MODEL
```

---

# 🚀 Step 9 – Run the Application

```bash
python3 app.py
```

Expected Output

```text
Server starting on http://localhost:7001

Using LLM endpoint:
http://localhost:12434/engines/v1/chat/completions

Using model:
smollm2:135M-Q4_K_M

Running on http://127.0.0.1:7001
```

---

# 🚀 Step 10 – Open the Application

```
http://localhost:7001
```

---

# 🔍 Verify Docker Model Runner API

```bash
curl http://localhost:12434/engines/v1/models
```

Expected Output

```json
{
  "object": "list",
  "data": [
    {
      "id": "docker.io/ai/smollm2:135M-Q4_K_M"
    }
  ]
}
```

---

# 🛠 Troubleshooting

## Docker Model Runner

```bash
docker model status
```

---

## Verify Model

```bash
docker model list
```

---

## Verify API

```bash
curl http://localhost:12434/engines/v1/models
```

---

## Port Already in Use

Linux

```bash
ss -ltnp | grep 7001
```

Windows

```powershell
netstat -ano | findstr :7001
```

---

# 💡 Challenges Faced

During implementation, several real-world issues had to be resolved:

- Docker Model Runner API connectivity
- WSL2 networking configuration
- Windows ↔ WSL localhost communication
- Docker Desktop configuration
- VS Code port conflict
- Flask application port configuration
- Environment variable setup
- Local LLM endpoint validation

---

# 📸 Demo

Add screenshots for:

- Docker Model Runner Status
- Terminal Running the Model
- Flask Application
- Chat Interface
- Successful AI Response

---

# 🚀 Future Improvements

- Streaming responses
- Conversation history
- Multi-model support
- Retrieval-Augmented Generation (RAG)
- PDF document chat
- Voice assistant integration

---

# 👨‍💻 Author

**Sandeep Mohapatra**

GitHub: https://github.com/sandeepmohapatra177/AIOPs

If you found this project useful, consider giving it a ⭐.
