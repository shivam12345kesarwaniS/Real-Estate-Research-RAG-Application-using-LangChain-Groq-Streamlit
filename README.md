# 🏡 WebRAG-RealEstate-Assistant

An AI-powered **Real Estate Research Tool** that scrapes live web articles, stores them in a vector database, and answers natural language questions using a Retrieval-Augmented Generation (RAG) pipeline — with source citations.

---

## 🚀 Features

✅ Enter 1–3 real estate article URLs  
✅ Web scraping using `UnstructuredURLLoader`  
✅ Text chunking & embedding using HuggingFace MiniLM model  
✅ Vector storage using **ChromaDB (persistent)**  
✅ Question answering using **LLaMA 3.3 - 70B via Groq API**  
✅ Custom prompt: falls back to general knowledge if answer not found in data  
✅ Returns **answer + source URLs**  
✅ Fully interactive Streamlit UI  

---

## 🏗️ Architecture Workflow

1. User enters URLs  
2. Content is scraped & converted into text  
3. Text is split into chunks (2000 tokens, 500 overlap)  
4. Embeddings generated via `sentence-transformers/all-MiniLM-L6-v2`  
5. Vectors stored in Chroma database  
6. Query passed to LLM via LangChain RetrievalQAWithSourcesChain  
7. Answer + source references returned to UI  

---

## 📚 Tech Stack

| Layer | Tool |
|-------|------|
| LLM | LLaMA 3.3 70B via Groq API |
| Framework | LangChain |
| Vector DB | ChromaDB (local persisted store) |
| Embeddings | HuggingFace MiniLM |
| UI | Streamlit |
| Loader | Unstructured URL Loader |
| Environment | Python + Dotenv |

