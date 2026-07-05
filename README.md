# 🔬 AI Research Paper Intelligence System

![Python](https://img.shields.io/badge/Python-3.8-blue)
![NLP](https://img.shields.io/badge/NLP-SentenceTransformers-green)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)
![Dataset](https://img.shields.io/badge/Dataset-15000%20ArXiv%20Papers-orange)
![FAISS](https://img.shields.io/badge/Search-FAISS-red)

> An intelligent NLP system that lets you search, summarize and extract insights from 15,000 ArXiv ML research papers — built as my second project during my B.Tech first year.

---

## 📋 Table of Contents
- [About the Project](#about-the-project)
- [Dataset](#dataset)
- [Features](#features)
- [Project Structure](#project-structure)
- [Technologies Used](#technologies-used)
- [How It Works](#how-it-works)
- [Results](#results)
- [How to Run](#how-to-run)
- [What I Learned](#what-i-learned)
- [Author](#author)

---

## 📌 About the Project

Finding relevant research papers manually is slow and inefficient. This project builds an AI powered system that understands the **meaning** behind your search query — not just keywords — and returns the most relevant research papers along with summaries, keywords and entity tags.

The system works on **15,000 real ArXiv ML research papers** and combines 4 powerful NLP techniques together.

---

## 📂 Dataset
| Property | Details |
|----------|---------|
| Source | ArXiv ML Papers (via HuggingFace) |
| Size | 15,000 research papers |
| Fields | Title, Abstract |
| Domain | Machine Learning and AI |

---

## ✨ Features

**1. 🔍 Semantic Search**
Searches papers based on meaning not just keywords. Uses SentenceTransformer embeddings and FAISS for fast similarity search across all 15,000 papers.

**2. 📝 AI Summarization**
Automatically generates a short readable summary of each paper's abstract using Facebook's BART model.

**3. 🏷️ Keyword Extraction**
Extracts the most important keyphrases from each paper using KeyBERT with confidence filtering (score > 0.5).

**4. 🤖 Named Entity Recognition (NER)**
Detects and tags technical entities in both the search query and paper keywords:
- Frameworks → TensorFlow, PyTorch, Keras
- Models → BERT, GPT, ResNet, CNN
- Programming Languages → Python, Java, C++
- Organizations → Google, OpenAI, Microsoft, DeepMind

Each detected entity also includes a short description of what it is!

---

## 📊 Project Structure

📦 AI-Research-Paper-Intelligence-System
┣ 📄 AI_Research_Paper_Intelligence_System.ipynb
┣ 📄 requirements.txt

---

## 🔧 Technologies Used
| Tool | Purpose |
|------|---------|
| Python | Core programming language |
| HuggingFace Datasets | Load 15,000 ArXiv ML papers |
| SentenceTransformers | Generate semantic embeddings (all-MiniLM-L6-v2) |
| FAISS | Fast similarity search across embeddings |
| Facebook BART | Abstractive summarization of abstracts |
| KeyBERT | Keyword and keyphrase extraction |
| Scikit-learn | Cosine similarity calculations |
| Pandas, NumPy | Data handling and manipulation |
| Regex (re) | Pattern matching for NER |

---

## ⚙️ How It Works

1. User types a search query
2. NER detects technical entities in the query (frameworks, models, organizations)
3. Query is converted to a vector embedding using SentenceTransformer
4. FAISS searches through 15,000 paper embeddings to find most similar papers
5. For each paper found:
   - Similarity score and title are shown
   - Abstract is displayed
   - AI summary is generated using BART
   - Keywords are extracted using KeyBERT
   - Entities found in keywords are tagged using NER
---

## 📈 Results

Sample query: **"research using pytorch and BERT from google"**

Detected Entities:

pytorch : Framework → ML framework by Facebook
bert : Model → Language model by Google for NLP
google : Organization → AI research and technology company

Similarity score : 0.45
Title : A Tour of TensorFlow
Summary : Deep learning is a branch of AI employing deep neural network architectures...
Keywords:

tensorflow open source  [tensorflow: Framework]
tensorflow alternative  [tensorflow: Framework]
deep learning software

---

## ▶️ How to Run

1. Clone the repository git clone https://github.com/KunalSingh84/AI-Research-Paper-Intelligence-System.git

2. Install required libraries pip install -r requirements.txt

3. Open the notebook in Google Colab

4. Run all cells sequentially from top to bottom

5. Call the final function with your query:
```python
search_and_summarize_with_ner("your query here", k=5)
```

> **Note:** First run will generate embeddings for all 15,000 papers which takes ~35 minutes. After that it loads instantly from saved files!

---

## 💡 What I Learned
- How semantic search works using vector embeddings
- How FAISS indexes and searches millions of vectors in milliseconds
- How transformer models summarize text automatically
- How to build a custom NER system using dictionaries and regex
- How to combine multiple NLP techniques into one complete pipeline

---

## 👤 Author
Kunal Singh

[![GitHub](https://img.shields.io/badge/GitHub-KunalSingh84-black?logo=github)](https://github.com/KunalSingh84)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-kunalsingh2127-blue?logo=linkedin)](https://www.linkedin.com/in/kunalsingh2127/)
