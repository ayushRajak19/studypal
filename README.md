# 🌌 AstraLearn

> **RAG-powered study assistant for smarter learning**

AstraLearn is an AI-powered study companion that uses **Retrieval-Augmented Generation (RAG)** to help students interact with their textbook content conversationally. Ask questions, get chapter-specific answers, and study more effectively — all grounded in your actual curriculum material.

Currently tuned for **Class 12 Biology**, with an architecture designed to scale across subjects and grade levels.

---

## ✨ Features

- 📚 **Curriculum-aware Q&A** — Ask anything from your Biology chapters and get accurate, contextual answers
- 🔍 **Vector search** — Chapters are embedded and stored in a vector database for fast, relevant retrieval
- 🤖 **RAG pipeline** — Combines document retrieval with LLM generation for grounded responses
- 🧩 **Modular design** — Easily extend to other subjects or grade levels by adding new data and vector stores

---

## 🗂️ Project Structure

```
AstraLearn/
├── data/
│   └── class_12/
│       └── biology/          # Raw source documents (PDFs / text)
├── chapters_vector_db/       # Vector DB for chapter-level embeddings
├── vector_db/
│   └── class_12_biology_vector_db/  # Subject-specific vector store
├── src/                      # Core application source code
├── requirements.txt          # Python dependencies
└── .gitignore
```

---

## 🚀 Getting Started

### Prerequisites

- Python 3.9+
- pip

### Installation

```bash
# 1. Clone the repository
git clone https://github.com/ayushRajak19/AstraLearn.git
cd AstraLearn

# 2. Create a virtual environment (recommended)
python -m venv venv
source venv/bin/activate    # On Windows: venv\Scripts\activate

# 3. Install dependencies
pip install -r requirements.txt
```

### Environment Setup

Create a `.env` file in the root directory and add your API keys:

```env
GOOGLE_API_KEY=your_google_api_key_here
# Add any other required keys
```

### Running the App

```bash
# From the project root
python src/main.py
```

---

## 🧠 How It Works

```
User Question
     │
     ▼
Embed the Query
     │
     ▼
Vector Similarity Search  ──►  chapters_vector_db / vector_db
     │
     ▼
Retrieve Relevant Chunks
     │
     ▼
Pass to LLM with Context
     │
     ▼
Generate Grounded Answer
```

1. **Ingestion** — Biology textbook content is chunked and embedded, then stored in a vector database.
2. **Retrieval** — When a user asks a question, semantically similar chunks are retrieved.
3. **Generation** — An LLM uses the retrieved context to generate an accurate, curriculum-grounded answer.

---

## 📦 Dependencies

Key libraries used (see `requirements.txt` for full list):

| Library | Purpose |
|---|---|
| `langchain` | RAG pipeline orchestration |
| `chromadb` / vector store | Storing and querying embeddings |
| `google-generativeai` | LLM for answer generation |
| `sentence-transformers` | Text embeddings |
| `streamlit` | Web UI (if applicable) |

---

## 🗺️ Roadmap

- [x] Class 12 Biology RAG pipeline
- [ ] Add support for other Class 12 subjects (Physics, Chemistry, Math)
- [ ] Multi-grade support (Class 10, 11)
- [ ] Quiz generation from chapters
- [ ] Chapter summary feature
- [ ] Deployed web interface

---

## 🤝 Contributing

Contributions are welcome! Feel free to open issues or submit pull requests.

1. Fork the repo
2. Create your feature branch (`git checkout -b feature/add-physics`)
3. Commit your changes (`git commit -m 'Add Class 12 Physics support'`)
4. Push to the branch (`git push origin feature/add-physics`)
5. Open a Pull Request

---

## 👤 Author

**Ayush Rajak**
- GitHub: [@ayushRajak19](https://github.com/ayushRajak19)

---

## 📄 License

This project is open source. Feel free to use and build upon it.
