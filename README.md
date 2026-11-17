<div align="center">

<img src="assets/banner.svg" alt="Nezha En-Naji El Idrissi: Data Science, NLP and Retrieval-Augmented Generation" width="100%"/>

<br/>

<img src="assets/status.svg" alt="Open to internships and collaborations" width="340"/>

<br/><br/>

[About](#about) &nbsp;·&nbsp; [Direction](#academic-direction) &nbsp;·&nbsp; [RAG project](#featured-project-multilingual-rag-assistant) &nbsp;·&nbsp; [SmartHealth](#smarthealth-iot-health-monitoring-platform) &nbsp;·&nbsp; [NABAM AUTO](#nabam-auto-internal-process-digitalisation) &nbsp;·&nbsp; [Stack](#technical-expertise) &nbsp;·&nbsp; [Timeline](#timeline) &nbsp;·&nbsp; [Contact](#contact)

[LinkedIn](https://linkedin.com/in/nezha-en-naji-el-idrissi-097a01364) &nbsp;·&nbsp; [Email](mailto:n.ennajielidrissi@gmail.com) &nbsp;·&nbsp; El Kelaa des Sraghna, Morocco

</div>

<img src="assets/divider.svg" alt="" width="100%"/>

## About

I hold a **DUT in Data Engineering** (2024–2026, *Mention Bien*, 14.57/20) and I am currently pursuing a **Bachelor in Data Science** (2026–2027). My work sits at the intersection of data engineering, machine learning and language technologies.

My main project is a **multilingual Retrieval-Augmented Generation (RAG) assistant** for IT support questions in French, English and Arabic, developed during my internship at OCP Group and evaluated with quantitative metrics. Alongside it, I have built an IoT health-monitoring platform (as part of a team) and a Flask web application for internal process management.

I like to follow a system from raw data to a usable interface, and to measure whether it actually works.

| | |
|---|---|
| **Focus** | NLP, Information Retrieval, RAG, data engineering |
| **Education** | Bachelor in Data Science (2026–2027) · DUT in Data Engineering (2024–2026) |
| **Experience** | OCP Group internship (2026) · NABAM AUTO |
| **Languages** | Arabic (native) · French · English · Italian (learning) |
| **Open to** | Internships, academic collaborations and technical projects in Data Science and NLP |

<img src="assets/divider.svg" alt="" width="100%"/>

## Academic direction

My path started with a Scientific Baccalaureate in Physical Sciences, continued with a DUT in Data Engineering, and now with a Bachelor in Data Science. Across these stages my interests have moved from data pipelines and databases toward NLP, information retrieval and applied AI.

My academic objective is to pursue an **MSc in Data Science at the University of Padua** starting in the 2027/2028 academic year.

<img src="assets/divider.svg" alt="" width="100%"/>

## Featured project: Multilingual RAG Assistant

**Repository:** [NezhaIdrissi/chatbot-it-rag](https://github.com/NezhaIdrissi/chatbot-it-rag)

### Problem and objective

IT support knowledge is often scattered across documents, and users ask questions in different languages. The goal was an assistant that answers in **French, English and Arabic**, using only the content of a knowledge base, so that answers can be traced back to retrieved passages instead of relying on the model's general memory.

### Architecture

<img src="assets/rag-architecture.svg" alt="Architecture of the multilingual RAG assistant: offline ingestion, chunking, embeddings and Chroma indexing; online FastAPI, LangChain retrieval, Mistral Large generation and Streamlit interface; RAGAS evaluation." width="100%"/>

### How it works

| Stage | Description |
|---|---|
| **Ingestion and preprocessing** | Knowledge-base documents are loaded and cleaned. |
| **Chunking** | Documents are split into passages, producing **3,384+ indexed chunks**. <!-- VERIFY: figure, chunk size and overlap --> |
| **Embeddings and indexing** | Chunks are embedded and stored in a Chroma vector index. <!-- VERIFY: embedding model name --> |
| **Retrieval** | The question is matched against the index and the most similar chunks are returned. <!-- VERIFY: top-k value --> |
| **Generation** | Mistral Large answers from the retrieved context. |
| **Serving** | A FastAPI backend exposes the pipeline; a Streamlit interface lets users ask questions. |

### Why multilingual retrieval matters

A question in French should find the right passage even when the passage is written in English or Arabic. That only works if questions and chunks live in a shared semantic space. The interactive demo below illustrates the idea in 3D.

<p align="center">
  <a href="https://nezhaidrissi.github.io/NezhaIdrissi-/demo/">
    <img src="assets/embedding-space.svg" alt="Animated preview of a multilingual semantic space. Click to open the interactive 3D demo." width="100%"/>
  </a>
</p>

<p align="center"><a href="https://nezhaidrissi.github.io/NezhaIdrissi-/demo/"><b>Open the interactive 3D demo</b></a> (drag to rotate, pick a question in French, English or Arabic). It is an illustration with synthetic data, not the project's real embeddings.</p>

<!-- VERIFY: the demo URL depends on the repository name and on GitHub Pages being enabled (Settings > Pages > main branch, root). -->

### Evaluation

The system was evaluated with **RAGAS**, with reported scores between approximately **0.81 and 0.83**.

### Technical considerations

- **Grounded generation** constrains the language model to retrieved evidence, which reduces unsupported answers and makes them easier to audit.
- **Systematic evaluation** replaces subjective impressions with measurable criteria.

### Possible next steps (not implemented)

- Report evaluation results separately for each language.
- Compare retrieval strategies and embedding models.
- Extend the test set and document failure cases.

<img src="assets/divider.svg" alt="" width="100%"/>

## SmartHealth: IoT health monitoring platform

A **team project** covering hardware, cloud and mobile development: vital signs are measured by sensors, sent over Wi-Fi, stored in the cloud and displayed in real time with alerts.

<img src="assets/smarthealth-architecture.svg" alt="SmartHealth architecture: MAX30102 and MLX90614 sensors feed a WeMos D1 ESP8266, which sends data over Wi-Fi to Firebase, synchronised in real time with a Flutter app providing alerts and sign-in." width="100%"/>

**Stack:** MAX30102, MLX90614, WeMos D1 (ESP8266), Firebase, Flutter, Dart.


<img src="assets/divider.svg" alt="" width="100%"/>

## NABAM AUTO: internal process digitalisation

**Problem:** internal registers at a car dealership needed a structured, controlled way of being recorded and consulted.
**Solution:** a Flask web application backed by a SQL database, with validated forms and controlled access.

<img src="assets/flask-architecture.svg" alt="NABAM AUTO architecture: a staff user goes through Flask-Login and Flask-WTF to a Flask application, which uses Flask-SQLAlchemy to store registers in a SQL database." width="100%"/>

**Stack:** Flask, Flask-SQLAlchemy, Flask-Login, Flask-WTF, SQL.

<img src="assets/divider.svg" alt="" width="100%"/>

## Technical expertise

<img src="assets/stack-orbit.svg" alt="Animated technical map with four orbits: AI, NLP and retrieval; data engineering; backend; mobile and IoT." width="100%"/>

| Domain | Technologies |
|---|---|
| **AI, NLP & Information Retrieval** | Retrieval-Augmented Generation · LangChain · Chroma · Mistral · RAGAS · Text Mining |
| **Data Engineering & Databases** | Python · SQL · Database Design · Data Processing |
| **Backend & Application Development** | FastAPI · Flask · Flask-SQLAlchemy · Streamlit |
| **Mobile & IoT** | Flutter · Dart · Firebase · ESP8266 · MAX30102 · MLX90614 |

<img src="assets/divider.svg" alt="" width="100%"/>

## Timeline

| Period | Milestone |
|---|---|
| 2024 | Scientific Baccalaureate, Physical Sciences |
| 2024–2026 | DUT in Data Engineering: *Mention Bien* |
| 2025 | NABAM AUTO: Flask and SQL application for internal registers |
| 2026 | OCP Group internship: multilingual RAG assistant |
| 2026–2027 | Bachelor in Data Science (in progress) |
| 2027/2028 | Academic objective: MSc in Data Science, University of Padua |

<img src="assets/divider.svg" alt="" width="100%"/>

## Education and certifications

### Education

| Period | Qualification | Institution |
|---|---|---|
| 2026–2027 | Bachelor in Data Science | Higher School of Technology El Kellaa des Sraghnas |
| 2024–2026 | DUT in Data Engineering, *Mention Bien* |Higher School of Technology El Kellaa des Sraghnas |
| 2024 | Scientific Baccalaureate, Physical Sciences | Al Maghreb Al Arabi |

### Certifications

| Certification | Issuer | Verification |
|---|---|---|
| NLP and Text Mining | SimpliLearn| <!-- VERIFY: real link only --> |
| Generative AI course | <!-- VERIFY --> | <!-- VERIFY: real link only --> |

<img src="assets/divider.svg" alt="" width="100%"/>

## Research interests

These are areas I want to study and work on, not completed research.

- Multilingual NLP
- Semantic search and information retrieval
- Retrieval-Augmented Generation
- Evaluation of LLM-based systems
- Data engineering for AI applications
- Applied machine learning

<img src="assets/divider.svg" alt="" width="100%"/>

## Contact

I am open to academic collaborations, internships and technical projects in Data Science and NLP.

- **LinkedIn:** [nezha-en-naji-el-idrissi](https://linkedin.com/in/nezha-en-naji-el-idrissi-097a01364)
- **Email:** [n.ennajielidrissi@gmail.com](mailto:n.ennajielidrissi@gmail.com)
- **GitHub:** [NezhaIdrissi](https://github.com/NezhaIdrissi)
- **CV:** [View CV](assets/cv.pdf) 
