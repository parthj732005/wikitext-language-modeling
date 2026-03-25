# 🤖 WikiText Language Modeling Pipeline (GPT from Scratch)

🚧 This project is currently under active development (Work in Progress)

---

## 📌 Overview

This project presents an **end-to-end pipeline for training GPT-style language models from scratch** on the WikiText-103 dataset.

The pipeline covers:
- Raw data preprocessing
- Sentence-level dataset construction
- Tokenization (Character-level and BPE)
- Dataset analysis
- Transformer-based language modeling
- Text generation

---

## 🎯 Objective

The goal is to build a **complete language modeling system from scratch** without relying on pretrained weights, while understanding:

- Data preprocessing for large-scale text
- Tokenization strategies (char vs subword)
- Transformer architecture
- Training dynamics and optimization
- Text generation techniques

---

## 🧠 Methodology

### 1️⃣ Data Preprocessing

The raw WikiText dataset is cleaned and normalized to produce high-quality training data.

Key steps:
- Removal of section titles and noisy lines
- Handling special tokens (`@-@`, `<unk>`)
- Filtering non-English characters
- Sentence segmentation using NLTK
- Removal of noisy sentences (high `UNK` ratio)
- Shuffling for better training distribution

📄 Output:
- `clean_wikitext.txt` (sentence-level dataset) :contentReference[oaicite:0]{index=0}

---

### 2️⃣ Tokenization Strategies

#### 🔹 Character-Level Tokenization
- Each character treated as a token
- Simple but limited semantic understanding

#### 🔹 BPE Tokenization (GPT-2)
- Subword-level tokenization using GPT-2 tokenizer
- Handles rare and unknown words efficiently
- Improves language modeling capability

---

### 3️⃣ Dataset Analysis

Statistical analysis performed on processed data:

- Total words and tokens
- Unique words and tokens
- Average tokens per word
- Average word length

👉 Helps understand dataset complexity and token efficiency

---

### 4️⃣ Model Architecture

Custom implementation of a **GPT-style Transformer** using PyTorch:

- Token + positional embeddings
- Multi-head self-attention (causal masking)
- Feedforward networks
- Residual connections + LayerNorm
- Stacked Transformer blocks

---

### 5️⃣ Training Strategy

- Train/validation split (90/10)
- Cross-entropy loss
- AdamW optimizer
- Early stopping based on validation loss
- Efficient batching using random sampling

---

### 6️⃣ Model Variants

#### 🔹 Baseline (Character-Level GPT)
- Smaller model
- Simpler tokenization
- Faster but less expressive

#### 🔹 Improved Model (BPE-based GPT)
- Subword tokenization
- Chunked encoding for large data
- Better generalization

#### 🔹 Enhanced Model
- Increased layers, heads, embedding size
- Larger context window
- Reduced dropout
- Improved convergence

---

### 7️⃣ Text Generation

Autoregressive generation using:

- Softmax sampling
- Temperature scaling
- Top-k sampling

👉 Enables control over:
- Creativity
- Diversity
- Coherence

---

---

## 🚀 Key Contributions

- ✅ Built GPT-style model from scratch (no pretrained weights)
- ✅ Designed full preprocessing pipeline for WikiText
- ✅ Implemented both char-level and BPE tokenization
- ✅ Performed dataset-level statistical analysis
- ✅ Developed scalable training pipeline with early stopping
- ✅ Implemented controlled text generation (temperature + top-k)

---

## ⚙️ Tech Stack

- Python
- PyTorch
- NLTK
- HuggingFace Tokenizers (GPT-2)

---

## 📈 Future Work

- Train on full dataset (not truncated)
- Scale model size further
- Add validation metrics (perplexity)
- Fine-tuning on domain-specific data
- Experiment with RLHF / instruction tuning
- Improve decoding strategies (top-p, beam search)

---

## 🧠 Key Learning Outcomes

- Practical understanding of Transformer architecture
- Importance of data preprocessing in NLP
- Trade-offs between tokenization methods
- Training stability techniques (early stopping)
- Impact of model scale on performance

---

## 📌 Conclusion

This project demonstrates a **complete pipeline for language model training from raw data to generation**, highlighting the importance of preprocessing, tokenization, and model design in NLP systems.

---

## 👤 Author

**Parth**  
GitHub: https://github.com/parthj732005

## 📊 Results

### Training Observations

- Training loss consistently decreases
- Early stopping prevents overfitting
- BPE model produces more coherent outputs than char-level
