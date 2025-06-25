# rag-pdf-chatbot

A Retrieval-Augmented Generation (RAG) chatbot that answers questions from unstructured PDF documents using Sentence-BERT and GPT-4.

This project implements a text-only RAG pipeline for semantic document question answering. It processes PDF files, embeds text chunks with Sentence-BERT, retrieves the most relevant segments, and uses GPT-4.1 to generate source-grounded answers. The interface is built with Gradio for real-time interaction.

## Overview

The pipeline includes:
- PDF text extraction and chunking
- Semantic search using Sentence-BERT + FAISS
- Query answering using GPT-4.1 via GitHub Models API
- Prompt engineering (zero-shot, few-shot, chain-of-thought)
- Gradio web interface for interactive use

## Data Sources

1. Annual Report 2023–24  
2. Financial Statements  
3. Final Year Project Handbook 2023  

## Key Features

- Supports natural language queries on multi-page PDFs  
- Retrieves and ranks relevant text chunks with metadata  
- Provides source-linked answers with traceability  
- Embeddings are persisted locally for reproducibility  
- Web interface supports real-time queries and responses  

## Example Queries and Responses

- **Q:** What does the PDF say about FYP Proposal Defense?  
  **A:** It evaluates feasibility and planning readiness. *(Source: FYP Handbook)*

- **Q:** What is the Balance Sheet breakdown?  
  **A:** Details current/non-current assets and liabilities. *(Source: Financials)*

- **Q:** What are the financial highlights in the annual report?  
  **A:** Increased operating income, R&D investment, and digital growth. *(Source: Annual Report 2023–24)*

## Prompt Engineering Techniques

- **Zero-shot prompting** – direct queries using retrieved context  
- **Few-shot prompting** – enhanced reasoning using example Q&A  
- **Chain-of-Thought prompting** – used for comparative or multi-step questions

## Performance Metrics

- Manual BLEU / ROUGE evaluation for output quality  
- Cosine similarity for retrieval relevance  
- Recall@5 and Mean Average Precision (MAP)  
- Average query latency: ~2.8 seconds  

## Embedding Space Visualization

- Visualized text chunk embeddings using PCA and t-SNE  
- Clear semantic clustering of related content (e.g., financial tables)

## Web Interface

Built using Gradio:
- Text input with real-time QA response  
- Chunk highlighting with document section references  
- Clean UI for exploration and experimentation  

## Challenges and Solutions

- **API and token setup**: Managed GitHub Models and Colab installations  
- **PDF formatting inconsistencies**: Standardized chunking logic  
- **Chunk size tuning**: Balanced between LLM input limits and context richness  
- **LLM query optimization**: Used prompt tuning for stability  

## Conclusion

This project demonstrates a complete RAG pipeline for text-based document QA using open tools and GPT-4.1. It supports document parsing, semantic search, and answer generation with traceable sources. Future work includes hybrid retrieval (BM25 + dense), query rewriting, and document summarization.

## Author

Minha Rehman  
Graduated Computer Science student, FAST NUCES  
[LinkedIn](https://www.linkedin.com/in/minha-rehman-b67204250/) • minharehman45@gmail.com
