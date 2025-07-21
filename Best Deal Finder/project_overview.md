# Smart Deal Hunter

Smart Deal Hunter is an LLM-powered system that estimates product prices and identifies great online deals using Retrieval-Augmented Generation (RAG), ensemble modeling, and real-time notifications.

## 💾 Data Sources

- **Product Knowledge Base:** [Amazon Reviews 2023 (McAuley Lab)](https://huggingface.co/datasets/McAuley-Lab/Amazon-Reviews-2023/tree/main/raw/meta_categories)

  - Transformed into ChromaDB for efficient semantic retrieval.

- **Online Deal Feed:** [DealNews RSS - Computers](https://www.dealnews.com/c39/Computers/?rss=1)
  - Scraped and processed periodically to collect current online product deals.

---

## 🧠 Models and Components

### 1. **RAG Pricer**

- Uses **LLaMA 3.2 8B** (running locally) with **ChromaDB context** retrieval.
- Predicts price based on retrieved product embeddings and descriptions.

### 2. **Specialist Agent**

- Fine-tuned **LLaMA 3.2 8B** model on historical pricing data.
- Learns to directly predict price from raw product metadata.

### 3. **Random Forest Regressor**

- Trained on ChromaDB product embeddings and known prices.
- Provides a traditional ML baseline for price estimation.

### 4. **Ensemble Model**

- Combines the above three models' predictions using **Linear Regression**.
- Produces a single final price estimate for each product.

---

## 📲 Notification & Display System

- **Pushover** is used to send push notifications with product name, predicted price, and link to the best deals.
- **Gradio** provides a minimal web interface to display the latest matched deals and their predicted prices.

---

## 🚀 Run the System

Ensure dependencies are installed, then run the main script:

```bash
python smart_deal_hunter.py
```
