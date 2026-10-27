# Multilingual IT Support Chatbot (RAG)

A retrieval-augmented generation (RAG) assistant that answers IT support questions in **French, English and Arabic**, grounded in a private knowledge base. Built during my end-of-studies internship at OCP Group.

![Python](https://img.shields.io/badge/Python-3.x-blue?style=flat-square)
![LangChain](https://img.shields.io/badge/LangChain-RAG-1C3C3C?style=flat-square)
![FastAPI](https://img.shields.io/badge/FastAPI-backend-009688?style=flat-square)
![Streamlit](https://img.shields.io/badge/Streamlit-UI-FF4B4B?style=flat-square)
![Status](https://img.shields.io/badge/status-functional-success?style=flat-square)

---

## Overview

IT support teams answer the same questions repeatedly, and the answers are scattered across documents. This project indexes an IT knowledge base and lets users ask questions in natural language, in their own language. Each answer is generated from the retrieved passages instead of the model's memory, which limits hallucinations and keeps answers traceable to a source.

[Add a 1–2 sentence description of the real use case at OCP, if you are allowed to share it.]

## Key results

| Metric | Value |
|---|---|
| Indexed chunks | 3,384+ |
| Languages supported | French, English, Arabic |
| RAGAS scores | approx. 0.81 – 0.83 |
| LLM | Mistral Large |

[Detail which RAGAS metrics these scores correspond to (faithfulness, answer relevancy, context precision, etc.) and on how many test questions. A precise table is far more convincing than a range.]

## Architecture

```
                    +---------------------+
   Documents  --->  |  Ingestion pipeline |
 (IT knowledge      |  load, clean, chunk |
     base)          +----------+----------+
                               |
                               v
                    +---------------------+
                    |  Chroma vector DB   |
                    |  (embeddings index) |
                    +----------+----------+
                               ^
                               | top-k retrieval
User question  --->  +---------+-----------+  --->  Answer + sources
  (FR / EN / AR)     |  FastAPI backend    |        (Mistral Large)
                     |  LangChain RAG chain|
                     +---------+-----------+
                               ^
                               |
                     +---------+-----------+
                     |  Streamlit interface|
                     +---------------------+
```

**Pipeline in short**

1. **Ingestion**: documents are loaded, cleaned and split into chunks.
2. **Indexing**: each chunk is embedded and stored in Chroma.
3. **Retrieval**: the question is embedded and the most relevant chunks are fetched.
4. **Generation**: Mistral Large answers using only the retrieved context.
5. **Serving**: a FastAPI backend exposes the chain; Streamlit provides the chat interface.

## Features

- Multilingual question answering in French, English and Arabic
- Answers grounded in the knowledge base, with the source passages available
- Clean separation between backend (FastAPI) and interface (Streamlit)
- Quantitative evaluation of the pipeline with RAGAS
- [Add anything else that is true: conversation memory, source display, language detection, etc.]

## Tech stack

| Layer | Technology |
|---|---|
| Language | Python |
| Orchestration | LangChain |
| Vector store | Chroma |
| LLM | Mistral Large |
| Backend | FastAPI |
| Frontend | Streamlit |
| Evaluation | RAGAS |

## Getting started

### Prerequisites

- Python [version]
- A Mistral API key

### Installation

```bash
git clone https://github.com/NezhaIdrissi/chatbot-it-rag.git
cd chatbot-it-rag
python -m venv venv
source venv/bin/activate        # Windows: venv\Scripts\activate
pip install -r requirements.txt
```

### Configuration

Create a `.env` file at the project root:

```
MISTRAL_API_KEY=your_key_here
```

### Build the index

```bash
python [ingest_script].py
```

### Run the backend

```bash
uvicorn [app.main]:app --reload
```

### Run the interface

```bash
streamlit run [app.py]
```

## Evaluation

The system was evaluated with RAGAS on [number] questions covering [categories]. Scores are in the 0.81 – 0.83 range.

[Insert a table with one row per RAGAS metric. Add one sentence on what you improved based on the evaluation (chunk size, top-k, prompt, etc.): this is what shows engineering maturity.]

## Project structure

```
chatbot-it-rag/
├── [data/]            knowledge base documents
├── [ingestion/]       loading, chunking, indexing
├── [backend/]         FastAPI application and RAG chain
├── [frontend/]        Streamlit interface
├── [evaluation/]      RAGAS scripts and test questions
├── requirements.txt
└── README.md
```

## Design decisions

- **Why RAG instead of fine-tuning**: the knowledge base changes often, and RAG updates by re-indexing, with no retraining.
- **Why multilingual**: users write in the language they are most comfortable with; the system answers accordingly.
- [Add 1–2 real decisions: why Chroma, why this chunk size, how Arabic is handled.]

## Limitations and next steps

- [Honest limitation, for example: Arabic retrieval quality compared with French]
- [Possible improvement, for example: hybrid search (BM25 + vectors), re-ranking, user feedback loop]
- [Possible improvement, for example: Docker deployment, automatic re-indexing]

## Author

**Nezha En-Naji El Idrissi**, Data Science student, applicant to the MSc in Data Science at the University of Padua.

[LinkedIn](https://linkedin.com/in/nezha-en-naji-el-idrissi-097a01364) · [Email](mailto:n.ennajielidrissi@gmail.com)
