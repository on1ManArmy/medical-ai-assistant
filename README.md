🏥 Multimodal Medical AI System

A production-ready Multimodal Disease Prediction System that integrates:

🩻 Chest X-ray imaging

📝 Clinical text reports

🧠 Medical Knowledge Graph (Neo4j)

🔄 Cross-modal attention fusion

📊 Uncertainty estimation (Monte Carlo Dropout)

🔥 Explainability (Grad-CAM)

🚀 FastAPI inference API

🐳 Dockerized deployment

⚠️ Disclaimer

This project is intended strictly for research and educational purposes.
It is NOT approved for medical diagnosis or clinical use.

🎯 Objective

Medical decision-making often requires combining:

Radiology imaging

Clinical documentation

Prior medical knowledge

This system builds a unified AI model that fuses:

Vision features (Chest X-ray via DenseNet121)

Text embeddings (ClinicalBERT)

Knowledge graph embeddings (Neo4j)

to perform multi-label disease prediction with:

Uncertainty estimation

Model explainability

API-based deployment

🏗 System Architecture
🔹 Vision Encoder

DenseNet121 backbone

Pretrained on ImageNet

Multi-label classifier

🔹 Text Encoder

ClinicalBERT (emilyalsentzer/Bio_ClinicalBERT)

Contextual medical text embeddings

🔹 Knowledge Graph

Neo4j database

Disease–Symptom–Treatment relationships

Embedding projection layer

🔹 Fusion Module

Multihead cross-attention

Shared embedding space

Final classification head

🔹 Uncertainty Module

Monte Carlo Dropout

Returns predictive mean + variance

🔹 Explainability

Grad-CAM heatmaps for visual reasoning

📂 Project Structure
medical-multimodal-ai/
│
├── app/
│   ├── main.py
│   ├── config.py
│   ├── inference.py
│   │
│   ├── models/
│   │   ├── vision.py
│   │   ├── text.py
│   │   ├── kg.py
│   │   ├── fusion.py
│   │   ├── multimodal.py
│   │   └── uncertainty.py
│   │
│   ├── services/
│   │   ├── preprocessing.py
│   │   ├── kg_service.py
│   │   └── explainability.py
│
├── training/
│   ├── dataset.py
│   ├── train.py
│   └── evaluate.py
│
├── docs/
│   └── Medical_AI_Assistant.pdf
│
├── Dockerfile
├── docker-compose.yml
├── requirements.txt
├── environment.yml
└── README.md
📄 Documentation

Full system design and architecture:

docs/Medical_AI_Assistant.pdf

Includes:

Problem framing

Dataset selection

Model architecture

Knowledge graph design

Deployment strategy

Research extensions

🧪 Environment Setup (Anaconda)
1️⃣ Create Environment
conda create -n medical-ai python=3.10 -y
conda activate medical-ai
2️⃣ Install Dependencies
pip install -r requirements.txt

Or recreate environment:

conda env create -f environment.yml
conda activate medical-ai
🚀 Running the API

Start FastAPI server:

uvicorn app.main:app --reload

Open Swagger UI:

http://localhost:8000/docs
🐳 Docker Deployment

Run full stack (API + Neo4j):

docker-compose up --build

Services:

API → http://localhost:8000

Neo4j → http://localhost:7474

📊 API Output Example
{
  "prediction": [0.12, 0.87, ...],
  "uncertainty": [0.03, 0.15, ...],
  "disclaimer": "Research use only. Not for diagnosis."
}
📈 Evaluation Metrics

AUROC (per class)

Macro-F1 score

Precision / Recall

Expected Calibration Error (ECE)

☁️ Deployment Options

AWS EC2 (GPU enabled)

GCP Cloud Run

Azure App Service

Kubernetes cluster

🔐 Production Hardening (Recommended)

HTTPS via NGINX

JWT authentication

Rate limiting

MLflow model registry

Prometheus + Grafana monitoring

GPU inference server

🔬 Research Extensions

Graph Neural Networks (GNN) for KG reasoning

Contrastive multimodal pretraining

Active learning pipelines

Federated hospital training

Differential privacy

🧠 Tech Stack

PyTorch

HuggingFace Transformers

Neo4j

FastAPI

Docker

Monte Carlo Dropout

Grad-CAM

📜 License

Add your preferred license (MIT recommended).

👨‍💻 Author

Abhishek Kumar
AI Systems | Backend Engineering | Distributed Systems
