## 🩺 Medical -AI -Assistant
A lightweight **Medical Retrieval-Augmented Generation (RAG) system** that retrieves health-related information from Wikipedia and provides relevant answers based on semantic similarity.  This AI assistant helps users understand medical conditions using reliable sources.


##🔗 **Live Demo (Hugging Face Space):**  
 https://sncarenyang-medical-rag-demo.hf.space/

 __________________


## 📌 Overview

This is a simple retrieval‑enhanced QA demo for medical and health‑related queries. It:

- Does **not** rely on any large language model API (LLM).  
- Uses only the wikipedia Python package and sklearn TF‑IDF + cosine similarity.  
- Is intended as an educational / demonstration project, **not** as a medical diagnosis system.  


## 📌 Features

- 🔍 Queries medical symptoms or health-related questions with mixed-language input (eg.,'covid19,'四神湯','勞宮穴"…)
- 📚 Retrieves relevant information from Wikipedia
- 🧠 Computes relevance via **TF-IDF vectorization + cosine similarity** for semantic matching
- 💬 Supports multi-turn queries with history tracking
- 🌐 Interactive web UI powered by Gradio and shows:
    --The most relevant snippets
    --Their similarity scores ( threshold > 0.2)
    --A simple chat-style history in the UI


## 🛠️ Tech Stack

- **Python**
- **Gradio** (UI)
- **scikit-learn**
  - TF-IDF Vectorizer
  - Cosine Similarity
- **Wikipedia API**


## 🧠 How It Works

1. User inputs a medical-related question (e.g., headache, fever)
2. System retrieves related content from Wikipedia
3. Text is vectorized using TF-IDF
4. Cosine similarity is computed between query and documents
5. Top relevant results are returned as the answer

## 🏗️ System Architecture

1. **User Input**  
   - User enters a medical-related query via Gradio interface  

2. **Data Retrieval**  
   - Fetch relevant content from Wikipedia  

3. **Text Processing**  
   - Clean and prepare text data  

4. **Vectorization**  
   - Convert text into TF-IDF vectors  

5. **Similarity Matching**  
   - Compute cosine similarity between query and documents  

6. **Ranking**  
   - Select top-k most relevant results  

7. **Response Output**
   - Display results in the UI with similarity scores


## 🚀 Installation & Run Locally

```bash
git clone https://github.com/YOUR_USERNAME/medical-rag-wiki-demo.git
cd medical-rag-wiki-demo

pip install -r requirements.txt
python app.py


## 📚 Project Structure

medical-rag-wiki-demo/
├── app.py                    # Gradio UI & Main application
├── requirements.txt          # Python dependencies
└── README.md                 # Project Documentation
```


## 💡 Future Improvements

 - Integrate LLM (e.g., GPT / open-source models) for better answer generation
 - Add multilingual support (Chinese/English medical queries)
 - Improve retrieval with embeddings (e.g., Sentence Transformers)
 - Add document sources (PDF, medical guidelines)



## 👩‍💻 Author
Shi-Ning Caren Yang



## ⭐ Highlights

 - Built and deployed a working RAG system on Hugging Face Spaces
 - Demonstrates understanding of information retrieval + NLP
 - Implemented TF-IDF based semantic retrieval  
 - Combines real-world medical use case with AI techniques



## ⚠️ Disclaimer
This project is for educational purposes only and does not provide medical advice. Always consult a licensed physician for real medical advice.


## 🌐 License & Copyright
-  The code in this repository is released under the MIT License.
-  The Wikipedia content retrieved via this demo is subject to Wikipedia’s own license and copyright terms.


## 📚 Acknowledgements
-  Thanks to **Hugging Face Space** for providing the free deployment platform.
-  Contributions are welcome

