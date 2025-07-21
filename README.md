# 🤖 TroubleBot - Offline IT Helpdesk Chatbot

**TroubleBot** is an offline AI chatbot designed to help users troubleshoot common system and IT problems without internet access. It runs locally using a small language model (LLM), making it secure and fast for organizations like BEL or internal IT teams.

---

## 📦 How to Set It Up (Google Drive Package)

### ✅ Prerequisites

- Windows 10/11 (64-bit)
- Python 3.10 or higher
- 8 GB RAM recommended
- No internet required after setup

---

## 🔧 Steps to Run TroubleBot

### 1. 🔽 Download and Extract

- Download the zip folder from Google Drive
- Right-click the ZIP → **Extract All...**
- Go into the extracted `TroubleBot` folder

---

### 2. 🛠 Create Virtual Environment

Open Command Prompt in the `TroubleBot` folder and run:

```bash
python -m venv venv
venv\Scripts\activate
```

If activation fails, run this once:

```powershell
Set-ExecutionPolicy RemoteSigned
```

Choose `Y`, then run the activation again.

---

### 3. 📥 Install Required Libraries

Once the environment is activated, install packages:

```bash
pip install -r requirements.txt
```

---

### 4. 🧠 Place the Model File

If not already included:
- Download a `.gguf` model (e.g., `gpt4all-falcon-q4_0.gguf`)
- Place it inside the `models/` folder

Final structure:
```
TroubleBot/
└── models/
    └── gpt4all-falcon-q4_0.gguf
```

---

### 5. 🧱 Build the Vector Index

Run this once:

```bash
python retriever.py
```

This creates the internal document index for retrieval.

---

### 6. 🚀 Launch the Web Chatbot

Start the Flask web server:

```bash
python webapp.py
```

Open your browser and go to:

```
http://127.0.0.1:5000/
```

---

## ✨ Features

- 💬 ChatGPT-style interface
- 📚 Offline document-based answers
- 🌙 Dark/Light mode toggle
- 🧠 GPT4All (local model, no internet required)
- 🕒 Stores frequently asked questions (soon)

---

## 📁 Included Files

| File | Purpose |
|------|---------|
| `webapp.py` | Flask server |
| `retriever.py` | Embedding & search setup |
| `generator.py` | AI model answer logic |
| `templates/index.html` | Web chat UI |
| `models/` | Store your `.gguf` model here |
| `faiss_index/` | Stores the FAISS document index |
| `requirements.txt` | Python dependencies |

---

## ❓ Need Help?

- ❗ “Model not found” → Make sure the `.gguf` model is placed in `models/`
- ❗ “Cannot open Flask site” → Ensure `webapp.py` is running in terminal
- ❗ “CMake or Llama errors” → Ignore unless chatbot fails to respond

---

## 🙋‍♀️ Author

Designed by **Hemant Kumar** for Bharat Electronics Limited  
Secure. Simple. Local.
