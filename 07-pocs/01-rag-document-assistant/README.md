# 01 RAG Document Assistant

## Overview
A retrieval-augmented generation system that answers questions from uploaded documents.

## Architecture
1. **Document Ingestion**
   - Accept PDF, DOCX, TXT, markdown files
   - Chunking strategy (recursive, semantic, page-based)
   - Generate embeddings
   - Store in vector database

2. **Retrieval**
   - User query embedding
   - Similarity search (cosine, dot product)
   - Re-ranking (cross-encoder, LLM judge)
   - Context window management

3. **Generation**
   - Prompt engineering with retrieved context
   - LLM response generation
   - Source attribution
   - Source citation in responses

## Features
- [x] Multi-format document support
- [x] Custom chunking strategies
- [x] Multiple vector database backends
- [x] Source citations with references
- [x] Chat history management
- [ ] Export conversations
- [ ] Multi-document queries
- [ ] Custom system prompts
- [ ] API integration

## Tech Stack
- Frontend: React / Swift / Kotlin
- LLM: OpenAI, Anthropic, or local models
- Vector DB: ChromaDB, Pinecone, Weaviate
- Embeddings: OpenAI, Cohere, HuggingFace

## Evaluation
- Answer relevance
- Context precision
- Source accuracy
- Latency benchmarks

## API Endpoints
- `POST /upload` - Upload and process document
- `POST /query` - Ask question about documents
- `GET /documents` - List uploaded documents
- `DELETE /documents/{id}` - Remove document