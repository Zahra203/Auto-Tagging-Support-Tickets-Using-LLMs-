# 🎯 Auto-Tagging Support Tickets Using LLMs  

## 📖 Project Overview
This project demonstrates how **Large Language Models (LLMs)** can be used to automatically tag support tickets into relevant categories.  
We explore and compare **Zero-Shot**, **Few-Shot**, and **Fine-Tuned** approaches for text classification.  

**Objective:**  
- Given a free-text support ticket, predict the **top 3 most probable tags**.  

---

## 📂 Dataset
- **Dataset Used:** [Tobi-Bueck/customer-support-tickets](https://huggingface.co/datasets/Tobi-Bueck/customer-support-tickets)  
- Contains customer support tickets with fields like `subject`, `body`, `language`, and multiple `tags`.  
- Preprocessing steps:
  - Filtered English tickets  
  - Concatenated `subject + body` → `text` field  
  - Extracted all non-null tags  
  - Train/Validation/Test split  

---

## ⚙️ Approaches Implemented
### 1️⃣ Zero-Shot Classification
- Model: `facebook/bart-large-mnli`, `valhalla/distilbart-mnli-12-1`  
- Approach: Directly classify tickets against candidate tags without training.  
- Pros: No training required, quick baseline.  
- Cons: Accuracy is moderate.  

### 2️⃣ Few-Shot Classification
- Model: `mistralai/Mistral-7B-Instruct-v0.2`  
- Approach: Prompted model with a few labeled examples + new ticket.  
- Pros: Improves over zero-shot, captures context better.  
- Cons: Slower, depends on prompt quality.  

### 3️⃣ Fine-Tuned Model
- Model: `distilbert-base-uncased` (multi-label classification)  
- Approach: Fine-tuned using Hugging Face Trainer.  
- Pros: Best accuracy & stable predictions.  
- Cons: Requires training time/resources.  

---

## 📊 Results & Comparison

| Method       | Pros                          | Cons                             | Performance |
|--------------|-------------------------------|----------------------------------|-------------|
| Zero-Shot    | Instant setup, no training    | Lower accuracy, confused on tags | ★★☆☆☆ |
| Few-Shot     | Better than zero-shot         | Slower, prompt-sensitive         | ★★★☆☆ |
| Fine-Tuning  | Best accuracy & stable output | Needs training resources         | ★★★★★ |

**Conclusion:**  
- Zero-shot = quick prototype  
- Few-shot = moderate improvement  
- Fine-tuning = best real-world solution  

---

## 🚀 Skills Gained
- Prompt Engineering  
- Zero-Shot & Few-Shot Learning  
- Fine-Tuning Transformer Models  
- Multi-Label Text Classification  
- Model Evaluation & Comparison  

---

## 🛠️ Tech Stack
- Python  
- Hugging Face Transformers  
- Datasets  
- PyTorch  
- scikit-learn  

---


   git clone https://github.com/your-username/support-ticket-auto-tagging.git
   cd support-ticket-auto-tagging
