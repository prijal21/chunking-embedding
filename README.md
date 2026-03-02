# 🧩 Chunking & Embedding Research for RAG

Before building a RAG pipeline I wanted to actually understand what happens when you change how you split text or swap out embedding models. So I ran a bunch of experiments and compared the results. Turns out it makes a bigger difference than I expected.

## 🔬 What I tested

**Chunking strategies** — I tried three: fixed-length, overlapping, and semantic. Fixed-length is simple but can cut sentences mid-thought. Overlapping helps with context at chunk boundaries. Semantic tries to split at natural topic breaks. I measured chunk count and average character length across all three on the same document.

**Embedding models** — Compared 4 open-source models on speed and how well they captured meaning. Some were faster but missed nuance, some were slower but significantly better at similarity tasks. The goal was to find the sweet spot for RAG without overspending on compute.

## 📊 Other stuff in here

- Built a ChromaDB vector store using LlamaIndex and tested queries against it
- Computed cosine similarity between sentence pairs and plotted a heatmap — really useful for seeing which chunks are too similar or too far apart
- Hooked up Gemini 2.5 Flash at the end to test full end-to-end QA

## 📂 Notebooks

- `Chunking&Embedings.ipynb` — the chunking experiments 🍕
- `Compare Open SOurce Embedding Models for RAG.ipynb` — model comparison
- `Embeddings_and_Chunking_with_LlamaIndex_and_Gemini.ipynb` — full setup with LlamaIndex + Gemini

## 🚀 Try it yourself

Runs fully on Google Colab.

1. Open any notebook in Colab
2. Click the 🔑 key icon on the left sidebar → add a secret called `GOOGLE_API_KEY`
3. Paste your Gemini API key and run all cells

> Free Gemini API key at [aistudio.google.com](https://aistudio.google.com)

Good starting point is `Chunking&Embedings.ipynb` → then `Compare Open SOurce Embedding Models` to see how the models stack up.

## ⚙️ Stack
Python · LlamaIndex · ChromaDB · HuggingFace Sentence Transformers · Gemini 2.5 Flash · Scikit-learn · Matplotlib
