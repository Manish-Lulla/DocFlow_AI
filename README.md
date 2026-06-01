# 📄 DocFlow-AI

> A full-stack document digitization tool that uses vision LLMs to read documents so humans don't have to.

Upload a document image — DocFlow-AI extracts the content, structures it, and stores it. No more manual data entry. No more brittle template-based OCR.

---

## ✨ What It Does

Traditional OCR breaks the moment a document layout changes. DocFlow-AI doesn't care about layouts — it **understands** documents the way a human would.

- 📸 Upload any document (invoices, forms, receipts, IDs, handwritten notes)
- 🤖 Vision LLM reads and understands the content
- 📊 Get clean, structured data back
- 💾 Everything stored for later review and analytics

---

## 🛠️ Tech Stack

**Frontend**
- React
- Tailwind CSS
- Recharts (analytics dashboard)

**Backend**
- FastAPI (Python)
- SQLAlchemy (ORM)

**AI**
- Groq API
- LLaMA 4 Scout Vision (multimodal model)

---

## 🚀 Getting Started

### Prerequisites
- Python 3.10+
- Node.js 18+
- A free [Groq API key](https://console.groq.com)

### 1. Clone the repo

```bash
git clone https://github.com/Manish-Lulla/docflow-ai.git
cd docflow-ai
```

### 2. Backend setup

```bash
cd backend
python -m venv venv
source venv/bin/activate   # On Windows: venv\Scripts\activate
pip install -r requirements.txt

# Create .env file
echo "GROQ_API_KEY=your_groq_api_key_here" > .env

# Run the server
uvicorn main:app --reload
```

Backend runs at `http://localhost:8000`  
API docs auto-generated at `http://localhost:8000/docs`

### 3. Frontend setup

```bash
cd frontend
npm install
npm run dev
```

Frontend runs at `http://localhost:5173`

---

## 🏗️ How It Works

```
┌─────────────┐      ┌──────────────┐      ┌─────────────────────┐
│  React UI   │ ───> │   FastAPI    │ ───> │  Groq + LLaMA 4     │
│   Upload    │      │   Backend    │      │  Scout Vision       │
└─────────────┘      └──────┬───────┘      └──────────┬──────────┘
                            │                          │
                            v                          │
                     ┌──────────────┐                  │
                     │  SQLAlchemy  │ <────────────────┘
                     │   Database   │   structured data
                     └──────────────┘
                            │
                            v
                     ┌──────────────┐
                     │  Analytics   │
                     │  Dashboard   │
                     │  (Recharts)  │
                     └──────────────┘
```

1. User uploads a document image via the React frontend
2. FastAPI receives it and sends it to Groq's LLaMA 4 Scout Vision endpoint
3. The model reads, understands, and extracts content as structured data
4. Results are persisted via SQLAlchemy
5. Dashboard visualizes processing history and trends

---

## 🎯 Use Cases

- 🧾 **Invoice & receipt digitization** — Automate expense tracking
- 📋 **Form processing** — Extract fields from any form layout
- 🪪 **ID card parsing** — KYC and onboarding workflows
- ✍️ **Handwritten notes** — Turn whiteboards and notebooks into text
- 📄 **Any image-of-text** → **structured data** workflow

---

## 📂 Project Structure

```
docflow-ai/
├── backend/
│   ├── main.py              # FastAPI entry point
│   ├── models.py            # SQLAlchemy models
│   ├── services/
│   │   ├── llm_service.py   # Groq + LLaMA integration
│   │   └── db_service.py    # Database operations
│   ├── requirements.txt
│   └── .env                 # API keys (not committed)
│
├── frontend/
│   ├── src/
│   │   ├── components/      # Reusable UI components
│   │   ├── pages/           # Page-level components
│   │   ├── services/        # API client
│   │   └── App.tsx
│   └── package.json
│
└── README.md
```

---

## 🔮 Roadmap

- [ ] Batch upload support
- [ ] Export extracted data to CSV / Excel / JSON
- [ ] User authentication & multi-user workspaces
- [ ] Support for additional vision models (GPT-4V, Gemini Vision)
- [ ] Confidence scores on extracted fields
- [ ] PDF multi-page support

---

## 💡 Why I Built This

This was my **first time shipping LLM vision in production**. I wanted to see how far you could push vision models beyond simple OCR — could they actually replace the brittle, template-locked tools we've been stuck with for years?

Turns out: yes. And it was a wild ride building it.

---

## 🤝 Contributing

Pull requests welcome! For major changes, please open an issue first to discuss what you'd like to change.

---

## 📄 License

MIT — feel free to use, fork, and modify.

---

## 👨‍💻 Author

**Manish Lulla** — B.E. IT graduate from Mumbai, building full-stack apps with a love for AI and clean UX.
- 📧 Email: manisshh.ml@gmail.com


Your repo will instantly look 10x more professional! 🚀

Let me know if you want me to tweak anything — make it shorter, more casual, add specific features, etc.
