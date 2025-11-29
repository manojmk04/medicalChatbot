# 🩺 AI Medical Chatbot — Langchain + RAG + Pinecone + Gemini

A smart **Medical Q&A chatbot** using **Langchain** and **Retrieval Augmented Generation (RAG)** to pull medical knowledge from PDFs stored in a serverless index, while generating concise answers via Google Gemini.

This project runs **100% locally** using Flask and Pinecone — **no AWS deployment needed**.

---

## ✨ Key Highlights

- 🧠 RAG-powered medical answers with minimal hallucination  
- 📄 Reads & processes PDF database from local `data/` directory  
- 🧩 Keeps only source metadata for clean vector storage  
- 🔎 Cosine similarity search using Pinecone index  
- 🤖 LLM = Google Gemini 2.5 Pro  
- 🧬 Embeddings = Sentence Transformers (384 dim)  
- 🌐 Flask API backend + simple UI (HTML/CSS)    

---

## 🧰 Tech Stack

| Component | Tool |
|---|---|
| LLM | `Gemini 2.5 Pro` |
| Vector DB | `Pinecone` |
| Embeddings | `sentence-transformers/all-MiniLM-L6-v2` |
| Framework | `LangChain` |
| Backend API | `Flask` |
| UI | `HTML + CSS (local template)` |

---

## 🛠 Installation

1. **Clone the repo**
git clone https://github.com/manojmk04/medicalChatbot
cd medicalChatbot


2. **Create virtual environment**
python -m venv medicalChatbotEnv
medicalChatbotEnv\Scripts\activate # Windows


3. **Install dependencies**
pip install -r requirements.txt


4. **Create `.env` file**
PINECONE_API_KEY=your_pinecone_api_key
GEMINI_API_KEY=your_gemini_api_key


5. **Create Pinecode Index and Initialize Pinecone with your PDF data**
python store_index.py #creates pinecode index
python src/helper.py # builds embeddings + upserts into Pinecone


6. **Run the Flask server**
python src/app.py


---

## 💬 Usage

Ask medical questions via UI or send a request to:

POST /get
Form field → "msg": "What is diabetes?"


Answers are generated using top-3 similar PDF chunks and limited to **3 short sentences**.

---

## 🤝 Contribute

You're welcome to raise issues or suggest improvements!

---

## 📜 License

MIT License © 2025 — Open for personal projects and learning.

---

## 📌 Note

I have first tried in ipynb file for practice and changed to modular code structure. I have also committed the python resources\trials.ipynb file for the reference.

