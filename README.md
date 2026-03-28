# Self-RAG

A Self Retrieval Augmented Generation (RAG) based application that allows users to query information from PDF documents using LLMs.

This project uses LangChain, LangGraph, FAISS, and Groq LLM API to build an intelligent document question-answering system.

## Features
- Load and process PDF documents
- Smart text chunking using recursive splitting
- Vector search using FAISS
- LLM-powered responses using Groq
- Graph-based workflow using LangGraph
- Fast and efficient retrieval system

## Architecture

<img width="598" height="704" alt="Screenshot (1664)" src="https://github.com/user-attachments/assets/7b6d0ab7-5f80-46eb-94e9-4c1b30362424" /><br>

## Tech Stack
- Python
- LangChain
- LangGraph
- FAISS
- HuggingFace Embeddings
- Groq API
- Pydantic

## Project Structure
```bash
├── documents/  
├── Final.ipynb
├── README.md 
└── requirements.txt
```

## Setup Instructions

### 1. Clone the repository

```bash
[git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name](https://github.com/Nitya-Pahwa/Corrective-RAG-Based-ML-Tutor.git)
```
### 2. Install dependencies

```bash
pip install -r requirements.txt
```


### 3. Set your API keys before running

```bash
import os
os.environ["GROQ_API_KEY"] = "your_groq_key"
```

## How It Works
1. Document Processing
  - PDF files are loaded and split into smaller chunks
  - Each chunk is converted into embeddings
  - Stored in a FAISS vector database
2. User Query
  - User asks a question
3. Initial Retrieval
  - Relevant document chunks are retrieved using similarity search
4. Answer Generation
  - LLM generates an answer based on retrieved context
5. Self-Reflection (Grading Phase)
  - The system evaluates:
     - Relevance of retrieved documents
     - Quality of generated answer
     - Groundedness (hallucination check)
6. Decision Making (LangGraph Flow)
  - Based on evaluation:
    - If answer is good → return response
    - If not sufficient → trigger re-retrieval or refinement
7. Iteration
  - The system may:
  - Retrieve better context
  - Regenerate improved answers
  - Repeat until quality is acceptable
