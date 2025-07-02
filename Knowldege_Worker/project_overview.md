```markdown
# 🧠 Expert Knowledge Worker – QA Assistant for Insurellm

A Retrieval-Augmented Generation (RAG) based Question Answering assistant built for _Insurellm_, an insurance tech company. This system uses a local LLM to accurately respond to user queries based on a custom markdown document knowledge base — all implemented in a Jupyter notebook for flexibility and rapid experimentation.

---

## 🚀 Features

- 🔍 Contextual QA from 31 markdown documents representing internal insurance knowledge
- 🧠 Runs locally with **LLaMA 3 (via Ollama)** — zero API cost and full data privacy
- 📦 Uses **ChromaDB** for document indexing and retrieval
- 📘 Fully implemented in a Jupyter Notebook environment
- ⏱️ Average query response time: ~5 seconds
- ⭐ Users can rate answers from 1–5; feedback stored for future evaluation

---

## 🧰 Tech Stack

- **LLM:** LLaMA 3 (via Ollama)
- **Framework:** LangChain
- **Vector Store:** ChromaDB
- **Embeddings:** Ollama Embeddings
- **Documents:** Markdown files (synthetic insurance content)
- **Environment:** Jupyter Notebook

---

## ⚙️ How to Run

1. Launch the notebook (`expert_knowledge_worker.ipynb`), run all cells sequentially.
2. Input a question when prompted and receive an answer with a rating option.

---

## 📏 Evaluation

- ⏱️ **Average Response Time:** \~5 seconds per query (local inference)
- 📚 **Document Base:** 31 markdown files
- ⭐ **User Ratings:** Collected (1–5 scale) per query to support future accuracy tracking
```
