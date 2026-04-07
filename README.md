# 🩺 Medical RAG+Wiki QA System Demo

A lightweight **Medical Retrieval-Augmented Generation (RAG) system** that retrieves health-related information from Wikipedia and provides relevant answers based on semantic similarity.

🔗 **Live Demo (Hugging Face Space):**  
https://sncarenyang-medical-rag-demo.hf.space/

---
## 📌 Overview

This is a simple retrieval‑enhanced QA demo for medical and health‑related queries. It:

- Does **not** rely on any large language model API (LLM).  
- Uses only the wikipedia Python package and sklearn TF‑IDF + cosine similarity.  
- Is intended as an educational / demonstration project, **not** as a medical diagnosis system.  

Always consult a licensed physician for real medical advice.

## 📌 Features

- 🔍 Queries medical symptoms or health-related questions with mixed-language input (eg.,'covid19,'四神湯','勞宮穴"…)
- 📚 Retrieves relevant information from Wikipedia
- 🧠 Computes relevance via **TF-IDF vectorization + cosine similarity** for semantic matching
- 💬 Supports multi-turn queries with history tracking
- 🌐 Interactive web UI powered by Gradio and shows:
    --The most relevant snippets
    --Their similarity scores ( threshold > 0.2)
    --A simple chat-style history in the UI

---

## 🛠️ Tech Stack

- **Python**
- **Gradio** (UI)
- **scikit-learn**
  - TF-IDF Vectorizer
  - Cosine Similarity
- **Wikipedia API**

---

## 🧠 How It Works

1. User inputs a medical-related question (e.g., headache, fever)
2. System retrieves related content from Wikipedia
3. Text is vectorized using TF-IDF
4. Cosine similarity is computed between query and documents
5. Top relevant results are returned as the answer

---

## 🚀 Installation & Run Locally

```bash
git clone https://github.com/YOUR_USERNAME/medical-rag-wiki-demo.git
cd medical-rag-wiki-demo

pip install -r requirements.txt
python app.py
