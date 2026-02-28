# Chunking Strategy & Embedding Model Research for RAG

I wanted to understand how different ways of splitting text and different embedding models affect retrieval quality in a RAG pipeline. So I ran a series of experiments to compare them before picking one for the actual pipeline.

## What I tested

For chunking, I tried three approaches: fixed-length, overlapping, and semantic. I measured things like chunk count and average character length to see how each one behaves on the same document.

For embeddings, I compared 4 open-source models on how fast they generate embeddings and how well they capture meaning. The goal was to find something that works well without being too slow or expensive.

## Other things covered

- Built a ChromaDB vector store using LlamaIndex to store and query the embeddings
- Computed cosine similarity between sentence pairs and plotted a heatmap to visualize how similar chunks are to each other
- Connected Gemini 2.5 Flash as the LLM so I could test full end-to-end question answering

## Notebooks

- `Chunking&Embedings.ipynb` - main chunking experiments
- `Compare Open SOurce Embedding Models for RAG.ipynb` - embedding model comparison
- `Embeddings_and_Chunking_with_LlamaIndex_and_Gemini.ipynb` - full RAG setup with LlamaIndex and Gemini

## Stack
Python, LlamaIndex, ChromaDB, HuggingFace Sentence Transformers, Gemini 2.5 Flash, Scikit-learn, Matplotlib
