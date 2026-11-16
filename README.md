# VectorDB — Build a Vector Database from Scratch in C++

A fully functional **Vector Database built from scratch in C++**, featuring a web-based dashboard, multiple vector search algorithms, semantic search, and a Retrieval-Augmented Generation (RAG) pipeline powered by a locally running LLM through Ollama.

This project demonstrates the core concepts behind modern vector databases such as Pinecone, Weaviate, Chroma, and Milvus, including vector indexing, similarity search, document embeddings, and AI-powered retrieval.

## 🚀 Features

| Feature | Description |
|---|---|
| **3 Search Algorithms** | HNSW, KD-Tree, and Brute Force search with performance comparison |
| **3 Distance Metrics** | Cosine Similarity, Euclidean Distance, and Manhattan Distance |
| **20 Demo Vectors** | Pre-loaded 16-dimensional semantic vectors across CS, Math, Food, and Sports categories |
| **2D PCA Visualization** | Interactive scatter plot to visualize semantic vector clusters |
| **Document Embeddings** | Convert user-provided text into 768-dimensional embeddings using `nomic-embed-text` |
| **RAG Pipeline** | Retrieve relevant document chunks using HNSW and generate contextual answers using `llama3.2` |
| **REST API** | Endpoints for insertion, deletion, search, benchmarking, and HNSW information |
| **Web Dashboard** | Interactive interface for exploring vector search and document retrieval |

## 🧠 How It Works

The project combines vector embeddings, indexing, semantic retrieval, and local LLM inference into one pipeline.

### RAG Architecture

```text
             Your Text / Documents
                      |
                      ▼
             Ollama Embedding Model
               nomic-embed-text
                      |
                      ▼
             768-Dimensional Vector
                      |
                      ▼
                HNSW Index
                (C++ Engine)
                      |
                      ▼
              Semantic Search
             Retrieve Relevant Chunks
                      |
                      ▼
                Context Builder
                      |
                      ▼
              Ollama Language Model
                   llama3.2
                      |
                      ▼
              Contextual AI Answer
```

### Search Algorithms

**1. HNSW (Hierarchical Navigable Small World)**

A graph-based approximate nearest neighbor search algorithm. It creates a multilayer graph where each successive layer is progressively sparser, allowing searches to navigate from coarse to more precise regions of the vector space.

**2. KD-Tree**

A space-partitioning data structure that organizes vectors into a tree, enabling efficient nearest-neighbor searches in suitable low-dimensional spaces.

**3. Brute Force**

Compares the query vector against every stored vector and calculates the distance to identify the nearest neighbors. It serves as a baseline for evaluating search performance.

## 🛠️ Technology Stack

- **Language:** C++17
- **Frontend:** HTML, CSS, JavaScript
- **Vector Search:** HNSW, KD-Tree, Brute Force
- **Similarity Metrics:** Cosine, Euclidean, Manhattan
- **Embeddings:** Ollama – `nomic-embed-text`
- **LLM:** Ollama – `llama3.2`
- **API:** REST API
- **Visualization:** 2D PCA Scatter Plot
- **Development Environment:** Ubuntu on WSL (Windows)

## ⚙️ Installation & Setup

### Prerequisites

- C++ compiler supporting C++17
- Git
- Ubuntu / Linux environment
- Ollama installed
- Required Ollama models

### 1. Clone the Repository

```bash
git clone https://github.com/Eshpreet/VectorDB.git
cd VectorDB
```

### 2. Install Dependencies (Ubuntu)

```bash
sudo apt update
sudo apt install build-essential g++ libssl-dev zlib1g-dev git
```

### 3. Download Ollama Models

```bash
ollama pull nomic-embed-text
ollama pull llama3.2
```

### 4. Compile the Project

```bash
g++ -std=c++17 -O2 main.cpp -o db -pthread
```

### 5. Start the Application

```bash
./db
```

### 6. Open the Dashboard

Visit:

```text
http://localhost:8080
```

**Note:** When running the project through WSL with Ollama installed on Windows, Ollama must be configured to accept connections from WSL. See the Ollama documentation and the project configuration for details.

## 📡 REST API

The backend exposes REST API functionality for interacting with the vector database.

| Operation | Description |
|---|---|
| Insert | Add vectors to the database |
| Delete | Remove stored vectors |
| Search | Find nearest neighbors |
| Benchmark | Compare search algorithm performance |
| HNSW Info | Inspect HNSW index information |

## 📊 Project Highlights

- Implemented multiple vector search approaches in C++.
- Compared approximate nearest-neighbor search with exact brute-force search.
- Integrated local embedding generation using Ollama.
- Built a document retrieval and RAG pipeline.
- Developed an interactive web dashboard for vector search and visualization.
- Explored the internal architecture of modern vector database systems.

## 🎯 Project Objective

The primary objective is to understand how vector databases work internally rather than relying on pre-built vector database frameworks.

By implementing indexing, distance calculations, nearest-neighbor search, document embeddings, and retrieval-based generation, this project provides hands-on exposure to the foundations of modern AI-powered search systems.
