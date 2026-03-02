# Chunking Strategy and Embedding Model Research for RAG

Before building a full RAG pipeline I wanted to understand what actually changes when you split text differently or swap out embedding models. So I ran experiments comparing both and measured the results.

## What I tested

For chunking I tried three approaches: fixed-length, overlapping, and semantic. Fixed-length is simple but can cut sentences in the middle. Overlapping helps with context at chunk boundaries. Semantic tries to split at natural topic breaks. I measured chunk count and average character length across all three on the same document.

For embeddings I compared 4 open-source models on generation speed and how well they captured meaning. The goal was to find the best balance between accuracy and compute cost for a RAG use case.

## Other things I covered

- Built a ChromaDB vector store using LlamaIndex and tested queries against it
- Computed cosine similarity between sentence pairs and plotted a heatmap to see which chunks were too similar or too far apart
- Connected Gemini 2.5 Flash at the end to test full end-to-end question answering

## Run the notebooks directly

Click any badge below to open that notebook in Google Colab and run it right away.

| Notebook | Open |
|----------|------|
| Chunking Experiments | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/prijal21/chunking-embedding/blob/main/Chunking%26Embedings.ipynb) |
| Compare Open Source Embedding Models | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/prijal21/chunking-embedding/blob/main/Compare%20Open%20SOurce%20Embedding%20Models%20for%20RAG.ipynb) |
| Full RAG Setup with LlamaIndex and Gemini | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/prijal21/chunking-embedding/blob/main/Embeddings_and_Chunking_with_LlamaIndex_and_Gemini.ipynb) |

## How to run

1. Click any badge above to open it in Colab
2. Click the key icon on the left sidebar and add a secret named `GOOGLE_API_KEY` with your Gemini API key
3. Run all cells from top to bottom

Free Gemini API key at [aistudio.google.com](https://aistudio.google.com).

## Stack
Python, LlamaIndex, ChromaDB, HuggingFace Sentence Transformers, Gemini 2.5 Flash, Scikit-learn, Matplotlib
