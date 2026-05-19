
# AI-Powered Role-Based Candidate Screening System

An intelligent interview system that dynamically generates interview questions based on a candidate's resume and selected job role using RAG (Retrieval-Augmented Generation).

## 🚀 Features
- Resume upload and parsing
- Role-based interview question generation
- RAG pipeline using role-specific knowledge base
- Interactive interview session
- Session summary and insights

## 🏗️ System Architecture

```
frontend/        → React app (UI)
backend/         → FastAPI app (API + business logic)
rag/             → RAG pipeline (embeddings + retrieval)
db/              → Database models
```

## 🛠️ Tech Stack

| Layer     | Technology                          |
|-----------|--------------------------------------|
| Frontend  | React, Axios                         |
| Backend   | Python, FastAPI                      |
| AI/ML     | LangChain, ChromaDB, Sentence-Transformers |
| Database  | SQLite (dev) / PostgreSQL (prod)     |
| LLM       | OpenAI GPT / Groq                    |

## ⚙️ Setup Instructions

### 1. Clone the repository
```bash
git clone https://github.com/shirisha0/AI-powered-role-based-candidate-screening-system.git
cd AI-powered-role-based-candidate-screening-system
```

### 2. Backend setup
```bash
cd backend
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate
pip install -r requirements.txt
uvicorn main:app --reload
```

### 3. RAG setup
```bash
cd rag
pip install -r requirements.txt
python ingest.py  # loads and embeds the knowledge base
```

### 4. Frontend setup
```bash
cd frontend
npm install
npm start
```

## 🔑 Environment Variables

Create a `.env` file in the `backend/` folder:
```
OPENAI_API_KEY=your_key_here
DATABASE_URL=sqlite:///./screening.db
```

## 📌 Key Design Decisions
- **Chunking strategy**: 500-word chunks with 50-word overlap for context preservation
- **Embeddings**: sentence-transformers/all-MiniLM-L6-v2 for efficiency
- **Vector DB**: ChromaDB for lightweight local vector storage
- **Question generation**: Context-aware prompts using retrieved chunks + resume data

## 👩‍💻 Author
Shirisha — [GitHub](https://github.com/shirisha0)
