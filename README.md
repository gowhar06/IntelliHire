# 🧠 IntelliHire – Smart Talent Matching System

**IntelliHire** is an AI-powered resume screening and job matching platform that leverages state-of-the-art Natural Language Processing (NLP) to automatically analyze resumes and job descriptions, compute fit scores, and help recruiters identify the best candidates efficiently.

---

## 🔍 Features

- Upload and extract text from resumes (PDF/DOCX)
- Parse job descriptions
- Generate embeddings using BERT/Sentence-BERT
- Perform semantic similarity matching
- Return top matching resumes with scores
- Clean and intuitive UI with React + Tailwind
- RESTful API using FastAPI
- Vector search using FAISS or Pinecone
- Store structured data using PostgreSQL or MongoDB

---

## ⚙️ Tech Stack

| Component     | Technology                      |
|---------------|----------------------------------|
| Frontend      | React.js, Tailwind CSS           |
| Backend       | FastAPI (Python)                 |
| NLP Models    | Sentence-BERT, spaCy             |
| File Parsing  | PyMuPDF, python-docx             |
| Vector DB     | FAISS / Pinecone                 |
| Database      | PostgreSQL / MongoDB             |
| Deployment    | Vercel (Frontend), Render or HF Spaces (Backend) |

---

## 📁 Project Structure

```
intellihire/
├── backend/
│   ├── main.py
│   ├── matcher/
│   ├── parser/
│   └── requirements.txt
├── frontend/
│   ├── src/
│   ├── public/
│   └── package.json
├── README.md
└── .env
```

---

## 🚀 Getting Started

### ✅ Prerequisites

- Python 3.8+
- Node.js 18+
- pip
- npm or yarn

---

### 🔧 Backend Setup (FastAPI)

```bash
# Navigate to backend
cd intellihire/backend

# Create virtual environment
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Run server
uvicorn main:app --reload
```

---

### 🖥️ Frontend Setup (React)

```bash
# Navigate to frontend
cd ../frontend

# Install dependencies
npm install

# Run dev server
npm run dev
```

---

## 💡 Resume Matching Logic

```python
from sentence_transformers import SentenceTransformer, util

model = SentenceTransformer('all-MiniLM-L6-v2')

def calculate_score(resume_text, job_text):
    resume_vec = model.encode(resume_text, convert_to_tensor=True)
    job_vec = model.encode(job_text, convert_to_tensor=True)
    score = util.cos_sim(resume_vec, job_vec)
    return float(score[0][0])
```

---

## 🛠️ API Endpoints

| Method | Endpoint           | Description                  |
|--------|--------------------|------------------------------|
| POST   | `/upload-resume`   | Upload and extract text      |
| POST   | `/submit-job`      | Submit job description       |
| GET    | `/get-matches`     | Get top matches              |

---

## 📦 Backend Dependencies

```
fastapi
uvicorn
sentence-transformers
spacy
PyMuPDF
python-docx
pinecone-client
faiss-cpu
pydantic
```

---

## 📊 Frontend Dependencies

```bash
npm install react tailwindcss axios vite
```

---

## 📤 Deployment

| Component  | Platform            | Notes                      |
|------------|---------------------|----------------------------|
| Frontend   | Vercel              | Connect GitHub repo        |
| Backend    | Render / HF Spaces  | Python app hosting         |
| Database   | MongoDB Atlas       | Free tier available        |
| Vector DB  | Pinecone            | Free tier for 1 index      |

---

## 📈 Future Improvements

- Resume OCR support (image to text)
- Bias detection and explanation
- Candidate notifications
- Admin dashboard with analytics
- Export results as PDF/CSV

---

## 🤝 Contributing

```bash
# Fork repo
# Create branch
git checkout -b feature/your-feature
# Commit and push
git commit -m "Add feature"
git push origin feature/your-feature
# Create Pull Request
```

---

## 📄 License

Licensed under the [MIT License](LICENSE)

---

## 📬 Contact

- 📧 Email: your.email@example.com
- 🌐 GitHub: [https://github.com/yourusername](https://github.com/yourusername)
