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
- 1️⃣ Clone Repository

  ```bash
  git clone https://github.com/Omkar-Gadade/RAG-Expert-Assistant-for-InsureLLM-Company.git
  cd insurellm-rag
   ```
