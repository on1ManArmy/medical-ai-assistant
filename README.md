# 🏥 Multimodal Medical AI System

> A production-ready **Multimodal Disease Prediction System** integrating medical imaging, clinical text, and structured knowledge graphs.

---

## 🚀 Features

- 🩻 **Chest X-ray Imaging (DenseNet121)**
- 📝 **Clinical Text Encoding (ClinicalBERT)**
- 🧠 **Medical Knowledge Graph (Neo4j)**
- 🔄 **Cross-Modal Attention Fusion**
- 📊 **Uncertainty Estimation (Monte Carlo Dropout)**
- 🔥 **Explainability (Grad-CAM)**
- 🚀 **FastAPI Inference API**
- 🐳 **Dockerized Deployment (API + Neo4j)**

---

## 🎯 Objective

Medical diagnosis often requires combining:

- Radiology imaging  
- Clinical documentation  
- Prior medical knowledge  

This system builds a unified AI architecture that fuses:

- **Vision features** (Chest X-ray via DenseNet121)  
- **Text embeddings** (ClinicalBERT)  
- **Knowledge graph embeddings** (Neo4j)  

To perform:

- ✅ Multi-label disease prediction  
- ✅ Predictive uncertainty estimation  
- ✅ Model explainability  
- ✅ API-based deployment  

---

## 🏗 System Architecture

### 🔹 Vision Encoder
- DenseNet121 backbone  
- Pretrained on ImageNet  
- Multi-label classifier  

### 🔹 Text Encoder
- ClinicalBERT  
- Model: `emilyalsentzer/Bio_ClinicalBERT`  
- Contextual medical embeddings  

### 🔹 Knowledge Graph
- Neo4j database  
- Relations:
  - `(Disease) → HAS_SYMPTOM → (Symptom)`
  - `(Disease) → HAS_TREATMENT → (Treatment)`
- Embedding projection layer  

### 🔹 Fusion Module
- Multihead cross-attention  
- Shared embedding space  
- Final classification head  

### 🔹 Uncertainty Module
- Monte Carlo Dropout  
- Returns predictive mean and variance  

### 🔹 Explainability
- Grad-CAM heatmaps for X-ray reasoning  

---

## 📂 Project Structure
medical-multimodal-ai/
│
├── app/
│ ├── main.py
│ ├── config.py
│ ├── inference.py
│ │
│ ├── models/
│ │ ├── vision.py
│ │ ├── text.py
│ │ ├── kg.py
│ │ ├── fusion.py
│ │ ├── multimodal.py
│ │ └── uncertainty.py
│ │
│ ├── services/
│ │ ├── preprocessing.py
│ │ ├── kg_service.py
│ │ └── explainability.py
│
├── training/
│ ├── dataset.py
│ ├── train.py
│ └── evaluate.py
│
├── docs/
│ └── Medical_AI_Assistant.pdf
│
├── Dockerfile
├── docker-compose.yml
├── requirements.txt
├── environment.yml
└── README.md

---

Includes:

- Problem framing  
- Dataset selection  
- Model architecture  
- Knowledge graph design  
- Deployment strategy  
- Research extensions  

---

## 🧪 Environment Setup (Anaconda)

### 1️⃣ Create Environment

```bash
conda create -n medical-ai python=3.10 -y
conda activate medical-ai

pip install -r requirements.txt

conda env create -f environment.yml
conda activate medical-ai
```

## Tech Stack

- **PyTorch**

- **HuggingFace Transformers**

- **Neo4j**

- **FastAPI**

- **Docker**

- **Monte Carlo Dropout**

- **Grad-CAM**

- **GenAI**

---
# 🏗 System Architecture

## 🔷 High-Level Pipeline

flowchart LR
    A[Chest X-ray] --> B[Vision Encoder<br/>DenseNet121]
    C[Clinical Notes] --> D[Text Encoder<br/>ClinicalBERT]
    E[Knowledge Graph<br/>Neo4j] --> F[KG Encoder]

    B --> G[Cross-Modal Attention Fusion]
    D --> G
    F --> G

    G --> H[Multi-Label Classifier]
    H --> I[Predictions]
    H --> J[Uncertainty (MC Dropout)]
    B --> K[Grad-CAM Explainability]
    
---

## 👨‍💻 Author

**Abhishek Kumar**  
AI Engineer | Distributed Systems | Backend Engineering  

---

## 📜 License

This project is licensed under the **MIT License**.

See the [LICENSE](LICENSE) file for full details.
