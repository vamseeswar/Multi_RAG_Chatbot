
# 🤖 MultiRAG Chatbot

A **Multi-Document Retrieval-Augmented Generation (RAG) Chatbot** built with **LangChain v0.2+, Groq LLM, and Chroma Vector DB**.  
This chatbot allows users to upload and query multiple files (PDFs, DOCX, CSV, PPT, Excel, TXT, RTF, ODT, etc.) and get **precise, context-aware answers** in real time.

---

## ✨ Features
- 📂 **Multi-format Document Uploads** — PDF, DOC/DOCX, PPT, Excel, TXT, CSV, RTF, ODT.
- ⚡ **Groq-Powered LLM** — Uses **Groq’s LLaMA-3.1** for fast, context-rich responses.
- 🗄️ **Vector Database** — Stores embeddings with **Chroma** for efficient retrieval.
- 📑 **Chunking & Indexing** — Smart text splitting for better answer quality.
- 🚀 **Large File Support** — Handles files up to **200MB** with background processing.
- 🧹 **Data Management** — `/clear` API wipes all processed data in one click.
- 🌐 **REST API + Web UI** — Flask backend, optional frontend in `templates/`.

---

## 🛠️ Tech Stack
- **Backend:** Python (Flask)
- **LLM:** Groq LLaMA (via `langchain_groq`)
- **Vector DB:** Chroma
- **Embeddings:** HuggingFace (`all-MiniLM-L6-v2`)
- **File Parsing:** pdfplumber, PyMuPDF, python-docx, openpyxl, python-pptx
- **Other Tools:** dotenv, threading for background tasks

---

## 📂 Project Structure
```

📦 Multi\_RAG\_Chatbot
┣ 📂 uploads/          # Uploaded raw files
┣ 📂 processed/        # Processed chunks & vector store
┣ 📂 templates/        # Optional frontend (index.html)
┣ 📜 app.py            # Main Flask backend
┣ 📜 requirements.txt  # Python dependencies
┣ 📜 .env.example      # Sample environment variables
┗ 📜 README.md         # Project documentation

````

---

## ⚙️ Installation

### 1. Clone Repository
```bash
git clone https://github.com/vamseeswar/Multi_RAG_Chatbot.git
cd Multi_RAG_Chatbot
````

### 2. Create Virtual Environment

```bash
python -m venv venv
source venv/bin/activate   # Linux/Mac
venv\Scripts\activate      # Windows
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Setup Environment Variables

Create a `.env` file:

```ini
UPLOAD_FOLDER=uploads
PROCESSED_FOLDER=processed
CHROMA_DIR=processed/chroma_db

# Groq API
GROQ_API_KEY=your_groq_api_key_here
GROQ_MODEL=llama-3.1-8b-instant
GROQ_TEMPERATURE=0.1

# RAG Settings
CHUNK_SIZE=1000
CHUNK_OVERLAP=200
SIMILARITY_K=10
SIMILARITY_THRESHOLD=0.5
```

---

## ▶️ Running the App

```bash
python app.py
```

Server runs at **[http://localhost:5000](http://localhost:5000)**

---

## 🔗 API Endpoints

| Method | Endpoint              | Description              |
| ------ | --------------------- | ------------------------ |
| POST   | `/upload`             | Upload a document        |
| GET    | `/upload_status/<id>` | Check processing status  |
| POST   | `/ask`                | Query uploaded documents |
| POST   | `/clear`              | Clear all data           |
| GET    | `/health`             | Health check             |

---

## 📊 Example Workflow

1. Upload `research_paper.pdf`
2. Ask: **“What is the conclusion of the paper?”**
3. Chatbot retrieves relevant text & responds using **Groq LLM**.

---

## 🚧 Future Improvements

* ⬆️ Handle **500MB+ uploads** with streaming
* 👥 Add **multi-user session support**
* 🔄 Real-time **WebSocket streaming answers**
* 🎨 Enhanced UI with themes & animations

---

## 👨‍💻 Author

Developed by **[Vamseeswar](https://github.com/vamseeswar)**
📌 Repository: [Multi\_RAG\_Chatbot](https://github.com/vamseeswar/Multi_RAG_Chatbot)

---

## 📜 License

This project is licensed under the **MIT License** – free to use, modify, and distribute.

```


