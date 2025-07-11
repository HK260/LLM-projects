# 💰 SmartPricer: LLM-Powered Price Estimator

SmartPricer is a hybrid machine learning and language model pipeline designed to estimate the price of home appliances using structured metadata and unstructured product descriptions. This project compares a traditional linear regression baseline with a fine-tuned **LLaMA 3.1 8B** model using **QLoRA** for regression from natural language.

---

## 🧠 Project Goals

- Predict product prices based on metadata and description text
- Benchmark traditional ML against LLM-based regression
- Showcase the impact of instruction-tuned LLaMA models on numerical prediction tasks

---

## 📦 Dataset

- Source: [Amazon Reviews 2023 (McAuley Lab)](https://huggingface.co/datasets/McAuley-Lab/Amazon-Reviews-2023)
- Subset: **Home Appliances** category
- Samples:
  - **25,000** for training
  - **2,000** for testing (only **250** used in final evaluation)

---

## 📊 Models Compared

### 1. Linear Regression (Baseline)

- **Features Used**: weight, rank, text length, is_top_Appliances_brand
- **Metrics**:
  - Mean Absolute Error (MAE): `$33.70`
  - RMSLE: `0.89`
  - Hit Rate (within margin): `80.8%`

### 2. Fine-Tuned LLaMA 3.1 (8B) with QLoRA

- **Trained On**: Product descriptions
- **Fine-Tuning Framework**: PEFT + QLoRA
- **Training Hardware**: T4 GPU
- **Training Settings**:

  - Epochs: 1
  - LoRA r: 32, Alpha: 64, Dropout: 0.1
  - 4-bit quantization
  - Batch size: 4, Cosine LR scheduler

- **Metrics**:
  - Mean Absolute Error (MAE): `$21.58`
  - RMSLE: `0.59`
  - Hit Rate: `88.4%`

---

## 📈 Evaluation Metrics

```python
error = abs(guess - truth)
log_error = log(truth + 1) - log(guess + 1)
sle = log_error ** 2
average_error = sum(errors) / N
rmsle = sqrt(sum(sles) / N)

```
