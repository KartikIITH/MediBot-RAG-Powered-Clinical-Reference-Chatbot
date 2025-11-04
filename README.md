# MediBot-RAG-Powered-Clinical-Reference-Chatbot

<div align="center">

# 🩺 Medical Chatbot (RAG-based Clinical Reference Assistant)

**Context-aware Q&A over a local medical knowledge base using FAISS vector search + HuggingFace or Groq-hosted LLMs.**

</div>

## 🧠 Overview
This project implements a Retrieval-Augmented Generation (RAG) pipeline that lets you ask medical questions grounded in a curated PDF knowledge base (e.g., an encyclopedia of medicine). Instead of hallucinating, the LLM is constrained by retrieved passages from a FAISS vector store built from your documents.

Two primary entry points:
* `connect_memory_with_llm.py` – CLI prototype using a HuggingFace Inference endpoint (e.g., Mistral 7B Instruct).
* `medibot.py` – Streamlit chat UI using a Groq-hosted model (Llama 3) with retrieval.

## ✨ Key Features
* **Vector Store:** Uses FAISS for fast, local semantic retrieval.
* **Embeddings:** Powered by `SentenceTransformer` (`all-MiniLM-L6-v2`), with an optional mode to use the HuggingFace API.
* **LLM Backends:** Modular support for Groq (fast) and HuggingFace (flexible).
* **Grounded Answers:** Includes source document traceability to show which chunks supported the answer.
* **Web UI:** A clean Streamlit chat interface for easy interaction.
* **Caching:** Caches the vector store and embeddings via Streamlit's resource cache for faster startups.

## 🏗️ Architecture
