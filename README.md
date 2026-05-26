# OCR-Ti-ng-Vi-t-
# Handwritten Text Segmentation & Vector Search System

A pipeline designed to segment, cluster, and retrieve handwritten Vietnamese text based on visual features and vector database indexing. The system breaks down a handwritten sentence into individual words/characters, extracts their structural features, and finds the closest matches.

---

## 📌 Pipeline Overview

Based on the system architecture, the workflow consists of three main stages:

### 1. Segmentation & Clustering
* **Input:** An image containing a handwritten sentence (e.g., *"tôi tên là linh"*).
* **Segmentation:** Separates the text foreground from the background.
* **Clustering:** Groups pixels/regions to isolate individual words or characters.
* **Result:** The sentence is successfully split into separate token images: `tôi`, `tên`, `là`, and `linh`.

### 2. Feature Extraction
* Each segmented word image is processed using the **HOG (Histogram of Oriented Gradients)** algorithm.
* Structural and shape features are converted into numerical **Vectors**.

### 3. Vector Database Indexing & Search
* **Dataset & Vector DB:** A reference dataset is pre-processed, vectorized, and stored inside a **Vector Database**.
* **Matching (Cosine Similarity):** The query vector from the input image is compared against the stored vectors using **Cosine Similarity**.
* **Output:** The system returns the closest matching text or character label.

---

## 🛠️ Tech Stack & Algorithms
* **Image Processing & Segmentation:** OpenCV, Clustering algorithms.
* **Feature Extraction:** HOG (Histogram of Oriented Gradients).
* **Metrics:** Cosine Similarity.
* **Storage:** Vector Database (e.g., Faiss, ChromaDB, Milvus, or custom matrices).

---

## 📂 Project Structure
```text
├── data/                  # Sample images and test datasets
├── src/
│   ├── segmentation.py    # Text segmentation and word bounding code
│   ├── feature_extract.py # HOG feature extraction -> vector generation
│   ├── vector_db.py       # Vector database initialization and indexing
│   └── search.py          # Cosine similarity matching and output delivery
├── main.py                # Main execution script
└── README.md
