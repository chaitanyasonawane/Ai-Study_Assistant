# 🚀 AI Study Assistant Pro (RAG Chatbot)

An AI-powered chatbot that allows users to upload PDF documents and ask questions based on their content using Retrieval-Augmented Generation (RAG).

This project demonstrates the practical implementation of Large Language Models (LLMs), vector databases, and conversational memory.

---

## 📌 Features

- 📄 Upload PDF and extract content
- 🔍 Semantic search using FAISS
- 🧠 Retrieval-Augmented Generation (RAG)
- 💬 Conversational memory (context-aware chat)
- 🛡️ Basic guardrails for safe interaction
- ⚡ Fully local (no API required)
- 🎯 Simple and clean Streamlit UI

---

## 🧠 How It Works

1. User uploads a PDF
2. Text is extracted and split into chunks
3. Chunks are converted into embeddings
4. Stored in FAISS vector database
5. User asks a question
6. Relevant chunks are retrieved
7. Local LLM generates response using context

---

## 🏗️ Tech Stack

- **Frontend:** Streamlit  
- **Backend:** Python  
- **Framework:** LangChain  
- **Vector Database:** FAISS  
- **Embeddings:** Sentence Transformers  
- **LLM:** HuggingFace (FLAN-T5 - Local Model)

---

## 📁 Project Structure
