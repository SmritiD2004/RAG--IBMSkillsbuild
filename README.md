# Document-Based RAG System using Google Gemini & FAISS

A Retrieval-Augmented Generation (RAG) system built in Google Colab that enhances Large Language Model (LLM) responses using an external knowledge base.

This project demonstrates how an LLM can generate more accurate and context-aware responses by retrieving relevant information from a document before answering a user's query.

> **Note:** The original lab used IBM Granite via Replicate. In this implementation, the paid Replicate API has been replaced with Google's free Gemini API while preserving the complete RAG workflow.

---

# Objective

The objective of this project is to demonstrate the implementation of a document-based Retrieval-Augmented Generation (RAG) pipeline.

The system:

- Accepts a user query
- Retrieves relevant information from an external knowledge base
- Uses the retrieved information as context
- Generates a context-aware response using Google Gemini
- Compares responses with and without RAG

---

# Project Workflow

```
                 User Query
                      │
                      ▼
         Baseline Response (Gemini)
                      │
                      ▼
        Upload Knowledge Base (.txt)
                      │
                      ▼
            Split into Chunks
                      │
                      ▼
      Sentence Transformer Embeddings
                      │
                      ▼
              FAISS Vector Store
                      │
                      ▼
        Retrieve Relevant Chunks
                      │
                      ▼
      Context + User Query → Gemini
                      │
                      ▼
          RAG-Enhanced Response
```

---

# Features

- Baseline LLM response (without RAG)
- Document chunking
- Semantic embeddings using Sentence Transformers
- FAISS vector similarity search
- Retrieval of relevant document chunks
- Context-aware response generation using Gemini
- Side-by-side comparison of baseline and RAG responses

---

# Technologies Used

| Technology | Purpose |
|------------|---------|
| Python | Programming Language |
| Google Colab | Development Environment |
| Google Gemini 2.5 Flash | Large Language Model |
| Sentence Transformers | Generate text embeddings |
| FAISS | Vector database for similarity search |
| NumPy | Numerical computations |

---

# Project Structure

```
.
├── README.md
├── External_KB_for_RAG.txt
└── RAG_Experiment.ipynb
```

---

# Installation

Install the required libraries:

```bash
pip install sentence-transformers faiss-cpu google-generativeai
```

---

# Setup

## Step 1

Create a Google AI Studio API key.

## Step 2

Open Google Colab.

## Step 3

Store your API key in Colab Secrets.

Secret Name:

```
GOOGLE_API_KEY
```

---

# Running the Notebook

Execute the notebook cells in the following order:

1. Install libraries
2. Import libraries
3. Load Gemini API
4. Generate baseline response
5. Upload knowledge base
6. Split document into chunks
7. Generate embeddings
8. Create FAISS index
9. Retrieve relevant chunks
10. Generate RAG response
11. Compare results

---

# How the RAG Pipeline Works

### 1. User enters a query

Example:

```
Do I need a Schengen visa if I travel to France?
```

---

### 2. Baseline LLM Response

The query is directly sent to Gemini.

The response relies only on the model's pre-trained knowledge.

---

### 3. Knowledge Base Upload

The external document is uploaded into Google Colab.

---

### 4. Document Chunking

The document is divided into smaller overlapping chunks to improve retrieval accuracy.

---

### 5. Embedding Generation

Each chunk is converted into a high-dimensional vector using the **all-MiniLM-L6-v2** Sentence Transformer model.

---

### 6. FAISS Index Creation

The embeddings are stored inside a FAISS vector index for efficient similarity search.

---

### 7. Query Embedding

The user query is converted into an embedding using the same embedding model.

---

### 8. Semantic Retrieval

FAISS searches for the document chunks most similar to the user's query.

---

### 9. Context Augmentation

The retrieved chunks are combined into a context prompt.

---

### 10. Response Generation

Gemini receives:

- Retrieved Context
- User Question

It generates an answer using the retrieved information.

---

# Example

### User Question

```
Hi. I'm a citizen of Romania.
Do I need a Schengen visa if I travel to France?
```

### Without RAG

```
The response is generated using the LLM's built-in knowledge.
```

### With RAG

```
The response is generated using the retrieved travel policy document, making it more accurate and context-aware.
```

---

# Advantages of RAG

- Reduces hallucinations
- Provides up-to-date information
- Uses external knowledge without retraining the LLM
- Produces more reliable responses
- Easily scalable with additional documents

---

# Future Improvements

- Support PDF and DOCX documents
- Use LangChain for pipeline orchestration
- Implement Hybrid Search
- Add metadata filtering
- Build a Streamlit web interface
- Store vectors in Pinecone, ChromaDB, or Milvus
- Support multi-document retrieval

---

# Learning Outcomes

After completing this project, you will understand:

- Retrieval-Augmented Generation (RAG)
- Document chunking
- Text embeddings
- Semantic search
- Vector databases
- FAISS indexing
- Prompt engineering
- Context-aware response generation

---

# References

- Google Gemini API
- Sentence Transformers
- FAISS
- Google Colab

---

# Author

**Smriti Dawane**

B.E. Computer Science Engineering

Project: Document-Based Retrieval-Augmented Generation (RAG) System
