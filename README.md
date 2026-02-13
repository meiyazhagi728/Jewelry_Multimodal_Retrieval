# JewelUX – Multimodal Jewelry Retrieval System

  JewelUX is a multimodal retrieval system designed for jewelry discovery using vision–language embeddings and vector similarity search.The system enables users to search across a jewelry catalog using natural language, reference images, hand-drawn sketches, or handwritten notes. It combines semantic vector search with structured metadata filtering to deliver consistent and scalable results.

  This project was developed as a capstone implementation of multimodal retrieval and RAG-inspired search architecture.

## Overview

  Traditional e-commerce search relies heavily on manually curated metadata and keyword matching. JewelUX replaces this dependency with embedding-based retrieval using a shared representation space across text and images.

## Core objectives:

  Enable cross-modal retrieval (text ↔ image ↔ sketch ↔ handwriting)

  Reduce reliance on manual tagging

  Support scalable similarity search

  Maintain modular architecture for future dataset expansion

## System Architecture

  The system follows a dual-layer retrieval design:

### Embedding Layer

  OpenAI CLIP generates image and text embeddings in a shared vector space.

  Sketch queries are processed using edge normalization before embedding.

  Handwritten text is extracted using OCR and converted into semantic queries.

### Retrieval Layer

  FAISS is used for high-performance approximate nearest neighbor search.

  Hybrid ranking combines semantic similarity with keyword-aware filtering.

  Category-level filtering improves precision in ambiguous queries.

  The architecture isolates retrieval pipelines for different modalities to prevent cross-interference between text, image, and sketch embeddings.

## Key Features

### Multimodal Search:

  Text-to-Image retrieval using CLIP text embeddings

  Image similarity search using CLIP image embeddings

  Sketch-based image retrieval (SBIR)

  Handwritten query extraction via OCR integration

### Hybrid Retrieval:

  Semantic vector similarity (FAISS)

  Keyword-aware re-ranking

  Metadata-based filtering

  Recommendation Engine:

  Similarity-based related item suggestions

  Embedding clustering for product grouping

## Scalability:

  Precomputed embedding indices

  Modular embedding and indexing pipelines

  Support for dataset growth without retraining

##  Technology Stack

### Backend:

  Python

  FastAPI

  OpenAI CLIP (ViT-B/32)

  FAISS (vector indexing)

  OCR module (handwriting extraction)

### Frontend:

  React (Vite)

  Tailwind CSS

  Framer Motion

  Axios

### Infrastructure:

  Precomputed embedding storage

  Modular indexing system

  GPU acceleration (optional)

## Installation
### Prerequisites

  Python 3.10.x

  Node.js 18+

  Optional: CUDA-enabled GPU

### Clone the Repository
git clone https://github.com/meiyazhagi728/Jewelry_Multimodal_Retrieval.git
cd Jewelry_Multimodal_Retrieval

### Backend Setup
cd backend
python -m venv .venv

### Windows
.\.venv\Scripts\Activate.ps1

### macOS / Linux
source .venv/bin/activate

pip install -r requirements.txt

### Frontend Setup
cd ../frontend
npm install

## Run the Application

### Backend:

cd backend
python run.py

```
Runs on: http://localhost:8000
```

### Frontend:

cd frontend
npm run dev


Runs on: http://localhost:5173

Project Structure
backend/
  ├── utils/          # Embedding, FAISS, OCR pipelines
  ├── metadata/       # Attribute data and CSV files
  ├── embeddings/     # Vector indices
  └── main.py         # API endpoints

frontend/
  ├── src/components/ # UI components
  └── App.jsx         # State management and routing

## Technical Highlights

  Cross-modal embedding alignment using CLIP

  Separate indexing pipelines for sketch and image queries

  Hybrid semantic + keyword ranking

  OCR integration for handwritten search intent

  Scalable vector search using FAISS

## Future Improvements

  Fine-tuning CLIP on domain-specific jewelry datasets

  Dedicated sketch-trained embedding models

  Attribute extraction using vision-language prompting

  Deployment with containerized infrastructure

  This project demonstrates practical implementation of multimodal retrieval systems, vector search architecture, and hybrid ranking pipelines in a real-world domain setting.
