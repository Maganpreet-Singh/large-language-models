# Large Language Models

<div align="center">

## 🤖 Large Language Models

### From Neural Networks to Transformers, RAG & LLM Applications

<img src="https://img.shields.io/badge/Focus-Large%20Language%20Models-blueviolet?style=for-the-badge">
<img src="https://img.shields.io/badge/Python-3.x-3776AB?style=for-the-badge&logo=python&logoColor=white">
<img src="https://img.shields.io/badge/NLP-Transformers-brightgreen?style=for-the-badge">
<img src="https://img.shields.io/badge/Hugging%20Face-Ecosystem-FFD21E?style=for-the-badge&logo=huggingface&logoColor=black">
<img src="https://img.shields.io/badge/RAG-Applications-8A2BE2?style=for-the-badge">

<br><br>

<a href="#-about">About</a> •
<a href="#-learning-roadmap">Roadmap</a> •
<a href="#-topics-covered">Topics</a> •
<a href="#-repository-structure">Structure</a> •
<a href="#-getting-started">Getting Started</a> •
<a href="#-projects">Projects</a>

</div>

---

## 📌 About

**Large Language Models** is a learning and implementation repository focused on understanding how modern language models work — from sequence modeling and attention to Transformers, pretrained language models, fine-tuning, Retrieval-Augmented Generation (RAG), and practical LLM applications.

The objective is to build understanding across the full stack:

```
Text
  ↓
Tokenization
  ↓
Embeddings
  ↓
Attention
  ↓
Transformers
  ↓
Language Modeling
  ↓
Pretraining
  ↓
Fine-Tuning
  ↓
Retrieval
  ↓
RAG
  ↓
LLM Applications
```

This repository is intended to grow progressively with notebooks, implementations, experiments, and end-to-end projects.

> **Build the fundamentals. Understand the architecture. Implement the pieces. Then build useful systems.**

---

## 🎯 Objectives

- Understand the foundations behind modern LLMs.
- Learn how text becomes tokens, vectors, and model inputs.
- Build strong intuition for self-attention and multi-head attention.
- Understand Transformer architecture in detail.
- Study encoder-only, decoder-only, and encoder-decoder models.
- Work with pretrained models through the Hugging Face ecosystem.
- Learn fine-tuning and parameter-efficient adaptation.
- Build RAG systems that combine retrieval with generation.
- Understand prompting, evaluation, inference, and deployment.
- Create portfolio-ready LLM projects.

---

# 🧭 Learning Roadmap

## 01. 🧠 Deep Learning Foundations

Important prerequisites:

- Neural networks
- Forward propagation
- Backpropagation
- Loss functions
- Gradient descent
- Optimizers
- Regularization
- Activation functions
- Sequence modeling

Recommended progression:

```
Machine Learning
      ↓
Neural Networks
      ↓
CNN
      ↓
RNN
      ↓
LSTM
      ↓
GRU
      ↓
Attention
      ↓
Transformers
      ↓
LLMs
```

---

## 02. 📝 NLP Foundations

Core NLP concepts:

- Text preprocessing
- Vocabulary construction
- One-hot encoding
- Bag of Words
- TF-IDF
- Word embeddings
- Word2Vec
- GloVe
- Contextual representations
- Sequence modeling
- Language modeling
- Next-token prediction

---

## 03. 🔤 Tokenization

Tokenization converts raw text into representations a language model can process.

Topics:

- Character-level tokenization
- Word-level tokenization
- Subword tokenization
- Byte Pair Encoding (BPE)
- Unigram tokenization
- SentencePiece
- Special tokens
- Vocabulary size
- Token IDs
- Attention masks
- Padding and truncation

Flow:

```
Raw Text
   ↓
Tokenizer
   ↓
Tokens
   ↓
Token IDs
   ↓
Embeddings
```

---

## 04. 🎯 Embeddings

Learn how language is represented numerically.

Topics:

- Word embeddings
- Token embeddings
- Positional embeddings
- Sinusoidal positional encoding
- Learned positional representations
- Sentence embeddings
- Semantic similarity
- Embedding spaces

---

## 05. 👀 Attention Mechanism

The core conceptual bridge from sequence models to Transformers.

Topics:

- Query, Key, Value
- Attention scores
- Scaled dot-product attention
- Softmax
- Self-attention
- Causal self-attention
- Cross-attention
- Masked attention
- Multi-head attention

Core equation:

```
Attention(Q, K, V)
=
softmax(QKᵀ / √dₖ)V
```

---

## 06. 🏗️ Transformer Architecture

Understand the building blocks behind modern language models.

Topics:

- Transformer blocks
- Residual connections
- Layer normalization
- Feed-forward networks
- Multi-head attention
- Positional information
- Encoder
- Decoder
- Cross-attention
- Causal masking

High-level architecture:

```
Tokens
  ↓
Token Embeddings
  +
Positional Information
  ↓
Transformer Blocks
  ├── Multi-Head Attention
  ├── Residual Connection
  ├── Layer Normalization
  ├── Feed-Forward Network
  └── Residual Connection
  ↓
Language Modeling Head
  ↓
Next-Token Probabilities
```

---

## 07. 🤖 Language Model Families

### Encoder-only

Focused primarily on representation and understanding tasks.

Examples:

- BERT
- RoBERTa
- DistilBERT

### Decoder-only

Designed primarily for autoregressive text generation.

Examples:

- GPT-style models
- LLaMA-family models
- Mistral-family models

### Encoder-decoder

Designed for sequence-to-sequence tasks.

Examples:

- T5
- FLAN-T5
- BART

---

## 08. 📚 Pretraining

Understand how language models learn general language patterns.

Topics:

- Causal language modeling
- Masked language modeling
- Next-token prediction
- Dataset preparation
- Data cleaning
- Batching
- Sequence length
- Learning-rate schedules
- Checkpointing
- Validation
- Training loss
- Perplexity

Simplified causal language-model objective:

```
P(x₁, x₂, ..., xₜ)
=
∏ P(xₜ | x₁, ..., xₜ₋₁)
```

---

## 09. 🧪 Fine-Tuning & Adaptation

Move from general pretrained models toward task- or domain-specific behavior.

Topics:

- Transfer learning
- Supervised fine-tuning
- Instruction tuning
- Full fine-tuning
- Parameter-efficient fine-tuning
- LoRA
- QLoRA
- Adapters
- Dataset formatting
- Training configuration
- Evaluation

---

## 10. 🤗 Hugging Face Ecosystem

Practical model development using the Hugging Face ecosystem.

Core tools:

- Transformers
- Tokenizers
- Datasets
- Model Hub
- Pipelines
- AutoTokenizer
- AutoModel
- Trainer
- Generation APIs
- Model configuration
- Checkpoint management

Typical workflow:

```
Dataset
   ↓
Tokenizer
   ↓
Pretrained Model
   ↓
Fine-Tuning
   ↓
Evaluation
   ↓
Inference
   ↓
Application
```

---

## 11. 🧩 Prompt Engineering

Learn how to design clearer and more reliable interactions with generative models.

Topics:

- Zero-shot prompting
- Few-shot prompting
- Role prompting
- Instruction design
- Prompt decomposition
- Prompt templates
- Context management
- Structured outputs
- Output constraints
- Prompt evaluation

---

## 12. 🔎 Retrieval-Augmented Generation (RAG)

RAG combines external information retrieval with generation.

Pipeline:

```
Documents
   ↓
Chunking
   ↓
Embedding Model
   ↓
Vector Database
   ↓
Retriever
   ↓
Relevant Context
   ↓
Prompt
   ↓
LLM
   ↓
Generated Answer
```

Topics:

- Document loading
- Chunking strategies
- Embedding models
- Vector similarity
- Vector databases
- Retrieval
- Metadata filtering
- Context injection
- Hybrid search
- RAG evaluation
- Hallucination analysis

---

## 13. 🗃️ Vector Databases

Study the infrastructure used for semantic retrieval.

Topics:

- Dense vectors
- Cosine similarity
- Euclidean distance
- Approximate nearest neighbors
- Indexing
- Metadata filtering
- Similarity search

Tools worth exploring:

- FAISS
- Chroma
- Qdrant
- Weaviate
- Pinecone

---

## 14. 🛠️ LLM Application Development

Turn models into useful software systems.

Potential applications:

- Chatbots
- Document Q&A
- Semantic search
- Summarization
- Text classification
- Information extraction
- AI assistants
- Code assistants
- Knowledge-base systems
- Recommendation systems

Architecture:

```
User
  ↓
Frontend / API
  ↓
Application Logic
  ├── Prompting
  ├── Retrieval
  ├── Tools
  └── Model
  ↓
Response
```

---

## 15. ⚡ Inference & Optimization

Learn how to make models faster and more memory-efficient.

Topics:

- Batching
- Token limits
- KV cache
- Quantization
- 8-bit inference
- 4-bit inference
- Model compression
- Memory optimization
- GPU inference
- CPU inference
- Latency
- Throughput

---

## 16. 🧠 Advanced LLM Concepts

Future advanced topics can include:

- Mixture of Experts (MoE)
- Multimodal LLMs
- Function calling
- Tool use
- Agents
- Long-context modeling
- Synthetic data
- RLHF concepts
- DPO
- Evaluation frameworks
- Guardrails
- Observability
- Production deployment

---

# 📚 Topics Covered

| Area | Focus |
|---|---|
| Deep Learning | Neural networks, optimization, sequence models |
| NLP | Language processing and representations |
| Tokenization | BPE, subwords, token IDs |
| Embeddings | Semantic vector representations |
| Attention | Self-attention, causal attention, multi-head attention |
| Transformers | Transformer blocks and language modeling |
| LLMs | Pretrained and autoregressive language models |
| Fine-Tuning | SFT, LoRA, QLoRA and adaptation |
| Hugging Face | Models, tokenizers, datasets and pipelines |
| Prompt Engineering | Prompt design and structured generation |
| RAG | Retrieval + generation systems |
| Vector Search | Semantic retrieval and vector databases |
| Inference | Generation, optimization and deployment |
| Applications | End-to-end LLM systems |

---

# 🗂️ Repository Structure

The repository is intentionally designed to evolve as implementations are added.

Recommended structure:

```
large-language-models/
│
├── README.md
│
├── 01_nlp_foundations/
│   ├── notebooks/
│   ├── src/
│   └── README.md
│
├── 02_tokenization/
│   ├── notebooks/
│   ├── src/
│   └── README.md
│
├── 03_embeddings/
│   ├── notebooks/
│   ├── src/
│   └── README.md
│
├── 04_attention/
│   ├── notebooks/
│   ├── src/
│   └── README.md
│
├── 05_transformers/
│   ├── notebooks/
│   ├── src/
│   └── README.md
│
├── 06_language_models/
│   ├── notebooks/
│   ├── src/
│   └── README.md
│
├── 07_fine_tuning/
│   ├── notebooks/
│   ├── src/
│   └── README.md
│
├── 08_huggingface/
│   ├── notebooks/
│   ├── src/
│   └── README.md
│
├── 09_prompt_engineering/
│   ├── notebooks/
│   └── README.md
│
├── 10_rag/
│   ├── notebooks/
│   ├── src/
│   └── README.md
│
├── 11_vector_databases/
│   ├── notebooks/
│   ├── src/
│   └── README.md
│
├── 12_llm_applications/
│   ├── projects/
│   ├── src/
│   └── README.md
│
├── 13_inference_optimization/
│   ├── notebooks/
│   ├── src/
│   └── README.md
│
├── requirements.txt
├── .gitignore
└── LICENSE
```

> **Note:** This is the intended future structure. The repository currently contains the main README only.

---

# 🚀 Getting Started

## 1. Clone the repository

```bash
git clone https://github.com/Maganpreet-Singh/large-language-models.git
cd large-language-models
```

## 2. Create a virtual environment

### Windows

```bash
python -m venv .venv
.venv\Scripts\activate
```

### Linux / macOS

```bash
python3 -m venv .venv
source .venv/bin/activate
```

## 3. Upgrade pip

```bash
python -m pip install --upgrade pip
```

## 4. Install dependencies

Once implementations are added:

```bash
pip install -r requirements.txt
```

Typical packages for future experiments:

```bash
pip install numpy pandas matplotlib scikit-learn jupyter
pip install torch transformers datasets tokenizers
```

Install only the dependencies required by each notebook or project when possible.

---

# 💻 Suggested Tech Stack

| Technology | Purpose |
|---|---|
| Python | Primary programming language |
| PyTorch | Deep learning and model implementation |
| TensorFlow | Optional deep learning experiments |
| Hugging Face Transformers | Pretrained LLMs |
| Hugging Face Datasets | Dataset management |
| Hugging Face Tokenizers | Fast tokenization |
| NumPy | Numerical computing |
| Pandas | Data manipulation |
| Matplotlib | Visualization |
| Scikit-learn | Classical ML and evaluation |
| Jupyter | Interactive experimentation |
| FAISS / Chroma / Qdrant | Vector retrieval |
| FastAPI / Flask | Backend APIs |
| Git & GitHub | Version control |

---

# 🧪 Implementation Philosophy

The repository follows a simple workflow:

### 1. Learn

Understand the concept and the mathematics behind it.

### 2. Implement

Code important components from scratch where practical.

Examples:

- Tokenizers
- Embedding layers
- Attention
- Multi-head attention
- Transformer blocks
- Language-model training loops

### 3. Experiment

Change parameters and measure the effect.

Examples:

- Learning rate
- Batch size
- Sequence length
- Embedding dimension
- Number of attention heads
- Number of layers

### 4. Build

Use the concepts in complete applications.

---

# 🏗️ Project Roadmap

## 🔹 Character-Level Language Model

A small language model that predicts the next character.

Skills:

- Vocabulary creation
- Tokenization
- Sequence generation
- Training loops
- Sampling

---

## 🔹 Transformer From Scratch

Build a small decoder-only Transformer.

Skills:

- Token embeddings
- Positional embeddings
- Self-attention
- Multi-head attention
- Feed-forward networks
- Residual connections
- Layer normalization
- Causal masking

---

## 🔹 Fine-Tuned Text Classifier

Fine-tune a pretrained Transformer for a custom classification task.

Skills:

- Hugging Face
- Dataset preparation
- Tokenization
- Fine-tuning
- Evaluation
- Inference

---

## 🔹 RAG Document Assistant

Build a question-answering application over a document collection.

Pipeline:

```
Documents
→ Chunking
→ Embeddings
→ Vector Store
→ Retrieval
→ Prompt Construction
→ LLM
→ Answer
```

---

## 🔹 Production-Style LLM Assistant

Combine:

- LLM inference
- Prompt templates
- Retrieval
- Tools
- Memory
- Backend APIs
- Evaluation
- Logging
- Deployment

---

# 📊 Evaluation

LLM systems need more than a single accuracy number.

### Model-Level

- Training loss
- Validation loss
- Perplexity
- Accuracy
- Precision
- Recall
- F1 score

### Generation-Level

- Relevance
- Coherence
- Factuality
- Faithfulness
- Diversity

### RAG-Level

- Retrieval precision
- Retrieval recall
- Context relevance
- Answer faithfulness
- End-to-end answer quality

### System-Level

- Latency
- Throughput
- Memory usage
- Token consumption
- Cost

---

# 🔐 Responsible AI

Language models can generate incorrect, biased, unsafe, or misleading content.

The project should therefore emphasize:

- Reproducible experiments
- Dataset quality checks
- Explicit evaluation
- Awareness of model limitations
- Privacy-aware data handling
- Secure secret management
- Careful deployment

### Never commit secrets

Do not push API keys, passwords, tokens, credentials, or private configuration files.

Use environment variables instead:

```bash
OPENAI_API_KEY=your_key_here
```

---

# 📈 Progress Tracker

```
[ ] NLP Foundations
      ↓
[ ] Tokenization
      ↓
[ ] Embeddings
      ↓
[ ] Attention
      ↓
[ ] Transformers
      ↓
[ ] Language Modeling
      ↓
[ ] Pretraining
      ↓
[ ] Fine-Tuning
      ↓
[ ] Hugging Face
      ↓
[ ] Prompt Engineering
      ↓
[ ] RAG
      ↓
[ ] Vector Databases
      ↓
[ ] LLM Applications
      ↓
[ ] Inference Optimization
      ↓
[ ] Advanced LLM Systems
```

---

# ✅ Learning Checklist

## Foundations

- [ ] NLP fundamentals
- [ ] Word embeddings
- [ ] Tokenization
- [ ] Language modeling

## Attention & Transformers

- [ ] Query / Key / Value
- [ ] Self-attention
- [ ] Causal attention
- [ ] Multi-head attention
- [ ] Positional encoding
- [ ] Transformer block
- [ ] Encoder
- [ ] Decoder

## LLM Development

- [ ] Causal language modeling
- [ ] Hugging Face Transformers
- [ ] Dataset preprocessing
- [ ] Text generation
- [ ] Fine-tuning
- [ ] LoRA
- [ ] QLoRA

## RAG

- [ ] Document loading
- [ ] Chunking
- [ ] Embeddings
- [ ] Vector database
- [ ] Retrieval
- [ ] Context injection
- [ ] RAG evaluation

## Production

- [ ] API development
- [ ] Inference optimization
- [ ] Quantization
- [ ] Monitoring
- [ ] Evaluation
- [ ] Deployment

---

# 📌 Current Repository Status

**Stage:** Repository foundation

At the current stage, the repository contains the main README and is prepared to become a structured collection of LLM implementations, experiments, notebooks, and projects.

As development progresses, this README can become the central index for:

- Implementations
- Notebooks
- Experiments
- Projects
- Models
- Datasets
- Benchmarks
- Deployment examples

---

# 🌱 Future Direction

The long-term progression is:

```
RNN / LSTM / GRU
        ↓
Attention
        ↓
Transformers
        ↓
GPT-style Models
        ↓
Fine-Tuning
        ↓
RAG
        ↓
Agents & Tool Use
        ↓
Inference Optimization
        ↓
Production LLM Systems
```

The goal is to move beyond simply calling pretrained models and develop the ability to **understand, implement, evaluate, fine-tune, and deploy language-model systems**.

---

# 🤝 Contributing

This is primarily a personal learning repository, but useful improvements and corrections are welcome.

A good contribution should ideally include:

1. Clear explanation
2. Reproducible code
3. Required dependencies
4. Example usage
5. Evaluation or expected output
6. References when appropriate

---

# 📜 License

A license can be added as the project evolves.

Until a license is explicitly added, assume repository contents are **not automatically licensed for unrestricted reuse**.

---

# 🔗 Connect

**GitHub:** [Maganpreet-Singh](https://github.com/Maganpreet-Singh)

**Repository:** [large-language-models](https://github.com/Maganpreet-Singh/large-language-models)

---

<div align="center">

### 🧠 Learn Deeply. Build From Scratch. Ship Real Systems.

⭐ Star the repository if you find the learning path useful.

</div>
