# 🏢 InsureLLM Expert – RAG-based Q&A Assistant

A Retrieval-Augmented Generation (RAG) powered intelligent assistant that answers questions about InsureLLM using a custom knowledge base.

This project combines:

- 🔎 Semantic Search (Vector DB)
- 🧠 LLM Reasoning (OpenAI GPT)
- 📚 Context Retrieval (LangChain + Chroma)
- 🌐 Interactive UI (Gradio)

## 🚀 Features

- Ask natural language questions about InsureLLM
- Retrieves relevant documents from a knowledge base
- Uses LLM to generate accurate, context-aware answers
- Displays retrieved context alongside answers (great for debugging RAG!)
- Clean chat interface using Gradio

## 📁 Project Structure

- vector_db/             -- Stored vector embeddings (Chroma DB)
- knowledge-base/        -- Source Company documents (Markdown files)
- implementation/
   - ingest.py           -- Data ingestion & embedding pipeline
   - answer.py           -- RAG pipeline (retrieval + generation)
- app.py                 -- Gradio UI Chatbot
- .env                   -- API keys
- requirements.txt
- pyproject.toml
- README.md

## ⚙️ How It Works (RAG Pipeline)

## 1️⃣ Data Ingestion

- Loads .md files from knowledge-base/
- Splits into chunks
- Converts text → embeddings
- Stores in Chroma vector database

👉 Implemented in: ingest.py

## 2️⃣ Retrieval + Generation

- Converts user query → embedding
- Retrieves top-K similar chunks
- Passes context to LLM for answer generation

👉 Implemented in: answer.py

## 3️⃣ UI Interaction

- Chat interface using Gradio
- Shows:
    - 💬 Answer
    - 📚 Retrieved context (source documents)
  
👉 Implemented in: app.py

## 🧠 Key Concepts Used

- Embeddings: text-embedding-3-large
- Vector DB: Chroma
- LLM: gpt-4.1-nano
- Chunking Strategy:
- Chunk size: 500
- Overlap: 200

## 🛠️ Setup Instructions
## 1️⃣ Clone Repository

  ```bash
  git clone https://github.com/Omkar-Gadade/RAG-Expert-Assistant-for-InsureLLM-Company.git
  cd insurellm-rag
   ```
## 2️⃣ Create Virtual Environment

 - Using uv package manager (recommended):
```bash
c\Users\insurellm-rag > uv sync
```

## 3️⃣ Add Environment Variables

 - Create a .env file:
```bash
OPENAI_API_KEY=your_api_key_here
```

## 4️⃣ Run Data Ingestion
```bash
uv run implementation/ingest.py
```

This will:
 - Create embeddings
 - Store vectors in vector_db/

## 5️⃣ Launch Application
```bash
uv run app.py
```
App will open in your browser 🚀

## 💬 Example Workflow

- User asks:

  - "What services does InsureLLM provide?"

- System:
  - Retrieves relevant docs
  - Sends context + query to LLM
- Output:
  - ✅ Final answer
  - 📚 Supporting context
 
## 📌 Important Notes
  - If you update documents → re-run ingestion
  - Vector DB is persistent in vector_db/
  - Retrieval uses k=10 documents

## 📄 License

  -  This project is licensed under the MIT License.
