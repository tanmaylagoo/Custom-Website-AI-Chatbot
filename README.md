# AI Website Chatbot using RAG, LangChain, Pinecone & Qwen

## Overview

This project is a Retrieval-Augmented Generation (RAG) chatbot that can answer questions based on the contents of one or more websites.

The application extracts website content, converts it into vector embeddings, stores them in Pinecone, retrieves relevant information for a user's query, and generates grounded answers using a Hugging Face large language model.

## Features

* Load and process content from websites
* Automatic text chunking using LangChain
* Semantic search using vector embeddings
* Pinecone vector database integration
* Retrieval-Augmented Generation (RAG)
* Question answering based on website content
* Hugging Face open-source LLM integration
* Interactive chatbot interface

## Tech Stack

* Python
* LangChain 1.3.9
* Pinecone
* Hugging Face Transformers
* Qwen/Qwen2.5-1.5B-Instruct
* BAAI BGE Embeddings
* Google Colab
* Unstructured URL Loader

## Project Architecture

Website URLs
→ Content Extraction
→ Text Chunking
→ Embedding Generation
→ Pinecone Vector Store
→ Retrieval
→ Qwen LLM
→ Response Generation

## Why RAG?

Large Language Models are trained on historical data and may not know information contained in specific websites.

RAG solves this problem by:

1. Retrieving relevant website content.
2. Supplying that content to the model.
3. Generating answers grounded in retrieved information.

This significantly reduces hallucinations and enables answers based on custom knowledge sources.

## Why Qwen 2.5 1.5B Instead of Llama 2?

The project uses **Qwen/Qwen2.5-1.5B-Instruct** instead of Llama 2 for several reasons:

### Better Performance-to-Size Ratio

Qwen 2.5 1.5B delivers strong instruction-following capabilities while requiring substantially fewer resources than Llama 2 7B.

### Faster Inference

The smaller model size results in lower memory consumption and faster response times, making it well-suited for Google Colab environments.

### Easier Deployment

Unlike Llama 2, Qwen models do not require separate Meta access approvals, simplifying setup and reproducibility.

### Strong Instruction Following

Qwen 2.5 models are optimized for conversational and instruction-based tasks, making them highly effective for question-answering applications.

### Cost Efficiency

The model can run efficiently on free Google Colab GPU instances, reducing infrastructure requirements while maintaining good performance.

## How It Works

1. Website URLs are loaded.
2. Content is extracted and cleaned.
3. Documents are split into smaller chunks.
4. Chunks are converted into embeddings using BGE embeddings.
5. Embeddings are stored in Pinecone.
6. User questions are converted into embeddings.
7. Pinecone retrieves the most relevant chunks.
8. Retrieved context is passed to the Qwen model.
9. The model generates a context-aware answer.

## Example Query

Question:

"What is LangChain?"

Process:

* Query embedding generated
* Relevant website chunks retrieved from Pinecone
* Context supplied to Qwen
* Final answer generated

## Future Improvements

* Multi-website support
* PDF document ingestion
* Chat history and memory
* Streamlit web interface
* Source citations
* Hybrid search
* Advanced reranking models

## Author

Tanmay Lagoo

Computer Engineering Undergraduate (Honors in Data Science & Analytics)
KJ Somaiya School of Engineering
