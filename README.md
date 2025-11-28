# 📌 DistilGPT-2 Fine-Tuning for Domain-Specific Text Generation

This project demonstrates how to fine-tune DistilGPT-2, a lightweight GPT-style language model, using HuggingFace Transformers.
The model learns from a custom text dataset and generates domain-specific sequences (e.g., finance/market, sentiment-focused text).

---

# 🚀 Features

⚪ Fine-tunes DistilGPT-2 using HuggingFace Trainer API

⚪ Preprocesses dataset with tokenization + block grouping

⚪ Trains a causal language model (next-token prediction)

⚪ Generates text using HuggingFace pipeline

⚪ Supports GPU acceleration (PyTorch)

⚪ Saves final model + tokenizer for deployment

---

# 🧠 Tech Stack

🔴 Python

🔴 PyTorch

🔴 HuggingFace Transformers

🔴 HuggingFace Datasets

🔴 Accelerate

🔴 Google Colab GPU (optional)

---

# 📂 Project Structure

├── fine_tune.ipynb   # Training notebook

├── README.md

├── requirements.txt

└── output/
    
    ├── config.json
    
    ├── pytorch_model.bin
    
    └── tokenizer files

---

## 🗃️ Dataset

This model was trained on a dataset from Kaggle.
Wikipedia Movie Plots. 

Dataset link - https://www.kaggle.com/datasets/jrobischon/wikipedia-movie-plots
---

# 🧩 Training Pipeline Summary

1. Load tokenizer + model (distilgpt2)

2. Load raw text dataset using load_dataset("text")

3. Tokenize each line

4. Group tokens into block_size length chunks

5. Fine-tune using Trainer with:

     - AdamW

     - FP16 (if GPU available)

     - Evaluation + checkpointing
  
6. Save final model + tokenizer

7. Generate text using HuggingFace pipeline

---

# ✨ Example Inference

from transformers import pipeline
```text
generator = pipeline("text-generation", model="OUTPUT_DIR", tokenizer="OUTPUT_DIR")
output = generator("Market is looking", max_new_tokens=50)
print(output[0]["generated_text"])
```
---

## ❤️ Sample Predictions

```text
Device set to use cuda:0
In a forest in a remote part of the world, I saw the strange creature at the bottom of a pond, it had dark fur,
an odd nose, blood gushing out of its mouth like a sick rat and its stomach churning blood.
As I scoured carefully for the strange creature's name.
  
```
---

## 👨‍💻 Author

Abhijith Babu
Passionate about ML & AI 🚀

📌 GitHub: [https://github.com/AbhijithBabu12]

📌 LinkedIn: [https://www.linkedin.com/in/abhijith-babu-856170201/]
