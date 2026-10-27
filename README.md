<div align="center">

<img src="https://capsule-render.vercel.app/api?type=venom&color=0:0b132b,50:1c2541,100:3a506b&height=230&section=header&text=Nezha%20En-Naji%20El%20Idrissi&fontSize=44&fontColor=e0fbfc&fontAlignY=40&desc=Data%20Science%20%C2%B7%20Natural%20Language%20Processing%20%C2%B7%20Retrieval-Augmented%20Generation&descAlignY=62&descSize=16&descColor=9fb3c8" width="100%"/>

<a href="https://github.com/NezhaIdrissi">
  <img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=500&size=19&pause=1400&color=5BC0BE&center=true&vCenter=true&width=760&lines=I+build+language+systems+that+answer+in+three+languages.;From+sensors+to+LLMs%2C+I+ship+end-to-end.;Data+Engineering+foundation.+Data+Science+ambition.;Applicant%3A+MSc+in+Data+Science%2C+University+of+Padua+2027%2F28." alt="Typing animation" />
</a>

<br/><br/>

[LinkedIn](https://linkedin.com/in/nezha-en-naji-el-idrissi-097a01364) &nbsp;|&nbsp; [Email](mailto:n.ennajielidrissi@gmail.com) &nbsp;|&nbsp; Morocco, El Kelaa des Sraghna

</div>

---

## Profile

I am a Data Science student with a **DUT in Data Engineering** (Mention Bien, 14.57/20), and I work where data meets language. My strongest work is a **multilingual retrieval-augmented generation system** built during my end-of-studies internship at OCP Group, which answers IT support questions in French, English and Arabic and was evaluated quantitatively rather than judged by feel.

Before that, I built a full IoT health-monitoring platform (hardware, mobile app, cloud) and a SQL-backed internal web application for an automotive dealership. I like owning a system from the raw signal to the user interface, and I care about measuring whether it actually works.

**I am applying to the MSc in Data Science at the University of Padua (2027/2028).**

---

## At a glance

| | |
|---|---|
| **Focus** | NLP, retrieval-augmented generation, data engineering |
| **Education** | Bachelor in Data Science (2026-2027), DUT in Data Engineering (2024-2026) |
| **Industry experience** | OCP Group (2026), NABAM AUTO, Peugeot Citroen (2025-2026) |
| **Languages** | Arabic (native), French, English, Italian (learning) |
| **Looking for** | Internships and collaborations in NLP, RAG and data-driven applications |

---

## Flagship project: multilingual RAG assistant

A question in French, English or Arabic goes in; a grounded answer comes out, built only from the retrieved knowledge base.

```mermaid
%%{init: {'theme':'base','themeVariables':{'primaryColor':'#1c2541','primaryTextColor':'#e0fbfc','primaryBorderColor':'#5bc0be','lineColor':'#5bc0be','secondaryColor':'#3a506b','tertiaryColor':'#0b132b','fontFamily':'monospace'}}}%%
flowchart LR
    subgraph OFFLINE["Offline: knowledge preparation"]
        direction TB
        A["IT knowledge base<br/>documents"] --> B["Ingestion<br/>load and clean"]
        B --> C["Chunking<br/>3,384+ chunks"]
        C --> D["Embedding"]
        D --> E[("Chroma<br/>vector index")]
    end

    subgraph ONLINE["Online: question answering"]
        direction TB
        F["User question<br/>FR / EN / AR"] --> G["FastAPI backend"]
        G --> H["LangChain<br/>retrieval chain"]
        H -->|"top-k similarity search"| E
        E -->|"relevant passages"| H
        H --> I["Mistral Large<br/>grounded generation"]
        I --> J["Answer<br/>from retrieved context"]
        J --> K["Streamlit interface"]
    end

    subgraph EVAL["Evaluation"]
        direction TB
        L["Test questions"] --> M["RAGAS metrics<br/>approx. 0.81 to 0.83"]
    end

    J -.-> M

    style OFFLINE fill:#0b132b,stroke:#3a506b,color:#e0fbfc
    style ONLINE fill:#0b132b,stroke:#3a506b,color:#e0fbfc
    style EVAL fill:#0b132b,stroke:#3a506b,color:#e0fbfc
```

| | |
|---|---|
| **Stack** | Python, LangChain, Chroma, Mistral Large, FastAPI, Streamlit |
| **Scale** | 3,384+ indexed chunks |
| **Quality** | RAGAS scores approx. 0.81 to 0.83 |
| **Languages** | French, English, Arabic |
| **Code** | [github.com/NezhaIdrissi/chatbot-it-rag](https://github.com/NezhaIdrissi/chatbot-it-rag) |

---

## Project: SmartHealth, an IoT health platform from sensor to screen

A team project covering hardware, cloud and mobile: vital signs are measured on a microcontroller, stored in the cloud and shown in real time with alerts.

```mermaid
%%{init: {'theme':'base','themeVariables':{'primaryColor':'#1c2541','primaryTextColor':'#e0fbfc','primaryBorderColor':'#5bc0be','lineColor':'#5bc0be','secondaryColor':'#3a506b','tertiaryColor':'#0b132b','fontFamily':'monospace'}}}%%
flowchart LR
    S1["MAX30102<br/>heart rate and SpO2"] --> MCU
    S2["MLX90614<br/>body temperature"] --> MCU
    MCU["WeMos D1<br/>ESP8266"] -->|"Wi-Fi"| FB[("Firebase<br/>Realtime DB, Firestore, Auth")]
    FB <-->|"live sync"| APP["Flutter app<br/>Dart"]
    APP --> AL["Threshold alerts"]
    APP --> AU["User authentication"]
```

---

## Project: internal process digitalisation at NABAM AUTO

A register-management web application for a Peugeot Citroen dealership, built with Flask and a SQL database.

```mermaid
%%{init: {'theme':'base','themeVariables':{'primaryColor':'#1c2541','primaryTextColor':'#e0fbfc','primaryBorderColor':'#5bc0be','lineColor':'#5bc0be','secondaryColor':'#3a506b','tertiaryColor':'#0b132b','fontFamily':'monospace'}}}%%
flowchart TB
    U["Staff user"] --> W["Flask-WTF<br/>validated forms"]
    U --> L["Flask-Login<br/>sessions and access"]
    W --> F["Flask application<br/>business logic"]
    L --> F
    F --> O["Flask-SQLAlchemy<br/>data layer"]
    O --> D[("SQL database<br/>registers")]
```

---

## Path

```mermaid
%%{init: {'theme':'base','themeVariables':{'cScale0':'#1c2541','cScale1':'#3a506b','cScale2':'#5bc0be','cScaleLabel0':'#e0fbfc','cScaleLabel1':'#e0fbfc','cScaleLabel2':'#0b132b','fontFamily':'monospace'}}}%%
timeline
    title From physical sciences to language systems
    2024 : Scientific Baccalaureate, Physical Sciences, Mention Bien
         : Starts the DUT in Data Engineering
    2025 : Introductory internship at NABAM AUTO
         : Flask and SQL application for internal registers
         : Generative AI course
    2026 : DUT completed, Mention Bien, 14.57/20
         : Technical internship at OCP Group
         : End-of-studies project, multilingual RAG assistant
         : NLP and Text Mining certification
         : Starts the Bachelor in Data Science
    2027 : Bachelor in Data Science in progress
         : Applying to the MSc in Data Science, University of Padua
```

---

## Technical map

```mermaid
%%{init: {'theme':'base','themeVariables':{'fontFamily':'monospace'}}}%%
mindmap
  root((Nezha))
    AI and NLP
      Retrieval-augmented generation
      LangChain
      Chroma vector database
      Mistral Large
      RAGAS evaluation
      Text mining
    Backend and web
      FastAPI
      Flask
      Flask-SQLAlchemy
      Streamlit
    Mobile and IoT
      Flutter and Dart
      Firebase
      ESP8266
      Biomedical sensors
    Data
      Python
      SQL
      Database design
      Data visualisation
```

| Domain | Tools |
|---|---|
| **AI and NLP** | LangChain, Chroma, Mistral Large, RAG, RAGAS |
| **Backend and web** | FastAPI, Flask, Flask-SQLAlchemy, Flask-Login, Flask-WTF, Streamlit |
| **Mobile and IoT** | Flutter, Dart, Firebase, ESP8266, MAX30102, MLX90614 |
| **Data** | Python, SQL, database design, data visualisation |

---

## Education and certifications

| Period | Qualification |
|---|---|
| 2026 - 2027 |
