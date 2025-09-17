# RAG Demo

A Retrieval-Augmented Generation (RAG) demonstration project using Chinese literature as the knowledge base.

## Overview

This project implements a RAG system that uses doc.md as the text corpus to demonstrate information retrieval and generation capabilities.

![alt text](./doc/rag-jupyter-demo.gif)

## Project Structure

```
rag-demo/
├── README.md           # This file
├── pyproject.toml      # Project configuration
├── main.py             # Main application entry point
├── .python-version     # Python version specification
├── .gitignore          # Git ignore rules
├── docker-compose.yml  # Docker Compose for local Ollama LLM
└── doc.md              # Source text corpus
```

## Features

- **Text Segmentation + Indexing**: Efficient text chunking and indexing for retrieval
- **Retrieval + Reranking + Generation**: Multi-stage RAG pipeline for accurate responses
- Support for Chinese text processing
- Optimized for literary content queries
- **Local LLM with Ollama via Docker Compose**

## Requirements

- Python >= 3.12
- Docker (for Ollama LLM)

### Dependencies

- **chromadb** (>=1.0.21) - Vector database for document storage and retrieval
- **sentence-transformers** (>=5.1.0) - Text embedding models for semantic search
- **python-dotenv** (>=1.1.1) - Environment variable management
- **Ollama** (via Docker Compose) - Local LLM for generation

## Getting Started

```bash
# 1. Initialize project (if not already done)
uv init .

# 2. Install dependencies
uv add chromadb>=1.0.21 python-dotenv>=1.1.1 sentence-transformers>=5.1.0

# 3. Alternative installation method
pip install -e .

# 4. Start Ollama LLM locally (recommended)
docker compose up -d

# 5. install chinese language model in ollama
ollama pull qwen2.5:7b

# 6. Run the demo
python main.py

# 7. Run Jupyter notebook
uv run --with jupyter jupyter lab
```

## RAG Pipeline

The system implements a three-stage RAG approach:

1. **分片+索引** (Segmentation + Indexing): Text is chunked and indexed for efficient retrieval
2. **召回+重排+生成** (Retrieval + Reranking + Generation): 
   - Retrieve relevant text segments
   - Rerank results for relevance
   - Generate responses based on retrieved context

## Use Cases

- Literature analysis and question answering
- Character and plot information retrieval
- Chinese text processing demonstration
- RAG system architecture showcase

## License

[Add your license information here]

---

**📚 Additional Resources:**
- [📓 Complete Implementation Guide](./main.md) - Generated from Jupyter notebook
- [🔧 Configuration Options](./main.md#configuration)
- [💡 Examples & Use Cases](./main.md#examples)