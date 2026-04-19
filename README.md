# Conversational RAG with PDF

A Streamlit app that lets you upload a PDF and chat with its content using LangChain, Groq (LLaMA 3.3), and HuggingFace embeddings — with full chat history support.

## Demo

> Upload any PDF → Ask questions → Get context-aware answers

---

## Features

- Upload any PDF and ask questions about its content
- Remembers chat history within a session
- Powered by `llama-3.3-70b-versatile` via Groq API
- Uses `all-MiniLM-L6-v2` for embeddings (HuggingFace)
- ChromaDB as the vector store
- Built with LangChain's RAG pipeline

---

## Tech Stack

| Tool | Purpose |
|------|---------|
| Streamlit | UI framework |
| LangChain | RAG pipeline |
| Groq | LLM inference (LLaMA 3.3 70B) |
| HuggingFace | Sentence embeddings |
| ChromaDB | Vector store |
| PyPDF | PDF loading |

---

## Getting Started

### 1. Clone the repo

```bash
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name
```

### 2. Create a virtual environment

```bash
python -m venv .venv
source .venv/bin/activate      # Mac/Linux
.venv\Scripts\activate         # Windows
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Set up environment variables

Create a `.env` file in the root directory:

```env
HF_TOKEN=your_huggingface_token_here
```

Get your HuggingFace token from: https://huggingface.co/settings/tokens

### 5. Run the app

```bash
streamlit run app.py
```

---

## Usage

1. Enter your **Groq API key** in the app (get it from https://console.groq.com)
2. Enter a **Session ID** (default is `default_session`)
3. Upload a **PDF file**
4. Ask questions in the chat box

---

## Project Structure

```
├── app.py               # Main Streamlit app
├── requirements.txt     # Python dependencies
├── .env                 # Environment variables (not committed)
├── .gitignore
└── README.md
```

---

## Deployment (Streamlit Community Cloud)

1. Push your code to GitHub
2. Go to [share.streamlit.io](https://share.streamlit.io)
3. Click **New app** → select your repo → set `app.py` as the main file
4. Go to **Settings → Secrets** and add:

```toml
HF_TOKEN = "your_huggingface_token"
```

5. In `app.py`, replace the dotenv line:

```python
# Replace this:
load_dotenv()
os.environ['HF_TOKEN'] = os.getenv("HF_TOKEN")

# With this:
os.environ['HF_TOKEN'] = st.secrets["HF_TOKEN"]
```

---

## Requirements

```txt
streamlit
langchain
langchain-groq
langchain-chroma
langchain-huggingface
langchain-community
langchain-text-splitters
pypdf
python-dotenv
sentence-transformers
chromadb
```

---

## License

MIT License — free to use and modify.
