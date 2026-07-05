# Retrieval-Augmented Generation (RAG) Experiments using Google Gemini

This repository demonstrates the implementation of **Retrieval-Augmented Generation (RAG)** using entirely **free and open tools**. It contains two progressively advanced experiments that showcase how external knowledge sources can enhance the responses of Large Language Models (LLMs).

The original IBM SkillsBuild labs used **IBM Granite via Replicate** for response generation. Since Replicate requires API credits, these experiments have been adapted to use **Google Gemini 2.5 Flash (Free API)** while preserving the complete RAG workflow.

---

# Repository Structure

```
📦 RAG-Experiments
│
├── 📄 README.md
├── 📓 RAG.ipynb
├── 📓 Dynamic_RAG_Web_Crawling_Gemini.ipynb
└── 📄 External_KB_for_RAG.txt
```

---

# Experiments Included

## Experiment 1 — Document-Based Retrieval-Augmented Generation

### Objective

Implement a basic RAG pipeline using a static external knowledge base.

### Workflow

```
External Knowledge Base
        │
        ▼
Document Chunking
        │
        ▼
Sentence Transformer Embeddings
        │
        ▼
FAISS Vector Database
        │
        ▼
Semantic Retrieval
        │
        ▼
Google Gemini
        │
        ▼
Context-Aware Response
```

### Features

- Static document knowledge base
- Text chunking
- Sentence embeddings
- FAISS similarity search
- Retrieval-Augmented Generation
- Baseline vs RAG comparison

### Files

- `RAG.ipynb`
- `External_KB_for_RAG.txt`

---

## Experiment 2 — Dynamic Knowledge-Augmented RAG using Web Crawling

### Objective

Enhance the RAG system by replacing the static knowledge base with dynamically retrieved web content.

Instead of answering only from a local document, the system first crawls a live website, extracts its textual content, builds a vector database, retrieves relevant information, and then generates a response using Gemini.

### Workflow

```
Website
   │
   ▼
Web Crawling
   │
   ▼
Extract Visible Text
   │
   ▼
Chunking
   │
   ▼
Sentence Transformer Embeddings
   │
   ▼
FAISS Vector Database
   │
   ▼
Semantic Retrieval
   │
   ▼
Google Gemini
   │
   ▼
Dynamic Context-Aware Response
```

### Features

- Live web crawling
- Dynamic knowledge source
- Automatic text extraction
- Semantic indexing
- Context-aware response generation
- Baseline vs Dynamic RAG comparison

### Files

- `Dynamic_RAG_Web_Crawling_Gemini.ipynb`

---

# Technology Stack

| Component | Technology |
|-----------|------------|
| Language | Python |
| Development Environment | Google Colab |
| LLM | Google Gemini 2.5 Flash |
| Embedding Model | all-MiniLM-L6-v2 |
| Vector Database | FAISS |
| Web Crawling | Requests + BeautifulSoup |
| Numerical Computing | NumPy |

---

# Comparison of Experiments

| Feature | Experiment 1 | Experiment 2 |
|---------|--------------|--------------|
| Knowledge Source | Static Text File | Live Website |
| Data Collection | Manual Upload | Web Crawling |
| Chunking | ✓ | ✓ |
| Embeddings | ✓ | ✓ |
| FAISS Retrieval | ✓ | ✓ |
| Gemini Response | ✓ | ✓ |
| Dynamic Updates | ✗ | ✓ |

---

# Learning Outcomes

These experiments demonstrate the complete Retrieval-Augmented Generation pipeline, including:

- Document preprocessing
- Web crawling
- Text chunking
- Semantic embeddings
- Vector similarity search
- FAISS indexing
- Context retrieval
- Prompt augmentation
- Context-aware response generation
- Static vs Dynamic knowledge integration

---

# Why Google Gemini?

The original IBM SkillsBuild labs used **IBM Granite through Replicate** for text generation. This repository replaces Replicate with **Google Gemini 2.5 Flash**, enabling the experiments to be executed entirely with free tools while maintaining the same RAG architecture and learning objectives.

---

# Future Enhancements

- Multi-document RAG
- Hybrid Search (Keyword + Semantic)
- ChromaDB / Pinecone Integration
- PDF and DOCX support
- LangChain Integration
- Streamlit-based User Interface
- Conversational Memory
- Multi-source Retrieval

---

# Author

**Smriti Dawane**

B.E. Computer Science Engineering

This repository was created as part of hands-on learning in Retrieval-Augmented Generation (RAG), demonstrating both static and dynamic knowledge integration using modern open-source tools and Google Gemini.
