# Atul Santhosh

### Backend & AI Systems Engineer · M.Sc. Computer Science, Philipps-Universität Marburg

[![Email](https://img.shields.io/badge/Email-athulsanthosh%40gmail.com-D14836?style=flat&logo=gmail&logoColor=white)](mailto:athulsanthosh@gmail.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-atul--santhosh-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/atul-santhosh/)
![Location](https://img.shields.io/badge/Location-Marburg%2C%20Germany-555555?style=flat)
![Open to work](https://img.shields.io/badge/Open%20to%20full--time-from%201%20Oct%202026-brightgreen?style=flat)

---

## About

I build production backend systems and applied AI/ML pipelines. Right now that means sole-engineer ownership of a full-stack research platform at Philipps-Universität Marburg, on top of ~3 years shipping backend services for high-traffic telecom systems at Comviva. Recent work spans a Kafka-based distributed backend handling millions of daily messages, a synthetic-data pipeline that generated 27,000 labelled images for a computer-vision thesis, and diagnosing a bug that had inflated that thesis's reported accuracy by ~52% before I caught and fixed it.

I like work that sits at the boundary of infrastructure and product — systems that have to stay up, and interfaces that make them usable by people who aren't engineers.

---

## Experience

**🔭 Research Assistant, Machine Learning and Systems** — *Philipps-Universität Marburg* · Mar 2025 – Present
- Built and ship a full-stack research platform solo — React/TypeScript frontend, Python/REST backend, Elasticsearch retrieval — for exploring large historical speech datasets, owning every deployment and infrastructure decision.
- Built audio/data pipelines (WhisperX, torchaudio, FFmpeg) and PyTorch/transformer workflows for historical speech annotation.
- Built and deployed LLM/agentic workflows for multi-step retrieval and orchestration, with output-validation loops before results reach users.
- Automated QC, anomaly detection, and bilingual (EN/DE) reporting for a 14-station environmental sensor network in Ecuador and Laipuna.
- University Machine Learning Teaching Assistant and Head Tutor for International Students (2024–2025).

**💼 Senior Software Engineer** — *Comviva* · Dec 2022 – Mar 2024
- Designed and shipped production backend services and REST APIs in Java and Go for high-traffic telecom messaging platforms.
- Engineered distributed, high-throughput systems with Kafka event pipelines, concurrent execution, and ordered message delivery.
- Built Docker/Kubernetes/Helm deployments, Jenkins/GitLab CI/CD pipelines, and Grafana/Prometheus/SigNoz observability.
- Implemented Redis/KeyDB failover mechanisms that improved service recovery by up to 98%.
- Won Comviva Hackathon 2022 as team lead (4 engineers) — an LLM agent with RAG-style retrieval and direct Jira API automation, shipped in 4 weeks.

**💼 Software Engineer** — *Comviva* · Jul 2021 – Nov 2022
- Developed operational C/C++ and backend software for live telecom systems under zero-data-loss reliability requirements.
- Implemented SOS emergency-communication functionality for Volvo vehicle communication workflows, with safety-critical, real-time delivery requirements.

---

## Featured Projects

### 🐛 Synthetic Data Generation & Object Detection for Automated Insect Monitoring
*M.Sc. Thesis — Python, PyTorch, RF-DETR, DINOv2, YOLOv8, BiRefNet, OpenCV, NumPy, ONNX, CUDA/A100*
- Built an end-to-end synthetic-data pipeline compositing BiRefNet-segmented specimen cutouts onto real tray backgrounds with physically calibrated sizing, generating up to 27,000 fully labelled images across 23 taxonomic classes with no manual annotation.
- Found and fixed a train/test leakage flaw that had inflated reported accuracy by ~52% (mAP@50:95 0.467 → an honest 0.308), by redesigning the pipeline around specimen-level disjoint splits.
- Benchmarked a transformer detector (RF-DETR, DINOv2 backbone) against a CNN detector (YOLOv8-L / flatbug) on identical data, improving mAP@50:95 from 0.294 to 0.365 — flatbug won 18 of 23 classes.
- Closed the sim-to-real gap by quantitatively profiling real pitfall-trap imagery (brightness, dark-pixel fraction, colour cast) and building a procedural soil renderer calibrated to those measurements.
- Diagnosed a size-based "catch-all" failure mode funnelling 76% of real-world detections into two classes, tracing the root cause to an augmentation strategy via per-class diagnostics.
- Built a self-contained evaluation suite (COCO 101-point AP, confusion matrices, precision/recall/F1) for a framework that shipped without one.

### 🔎 Full-Stack Speech Research Platform
*React, TypeScript, Python, Elasticsearch*
- Built a research interface for interactive search, annotation, and exploration of large historical speech datasets — component architecture, real-time state management, REST integration, and retrieval indexing, end to end.

### 🎙️ Historical Speech Annotator
*PyTorch, torchaudio, Mel-spectrogram preprocessing*
- Adapted a PMAM Transformer model for historical speech annotation and signal analysis, with automated annotation/interpretation tooling built for historians and other non-technical domain experts.

### 🤖 Agentic LLM / Jira Automation System
*Comviva Hackathon 2022 — 1st place*
- Led a team of 4 to build an LLM agent combining multi-step reasoning, RAG-style context, and direct Jira API automation for structured issue/output generation, shipped in 4 weeks.

### 🌱 [Sahyog App](https://github.com/atulsan/Sahyog-App)
*Android, Firebase, Mapbox — archived*
- Android app for reducing food waste by connecting surplus-food donors with nearby recipients, using geolocation matching, real-time alerts, and direct messaging.

### 🌦️ Climate Station Data Quality Control
*Python, pandas, data QC*
- Automated QC for raw logger data across a 14-station tropical/Andean sensor network (Ecuador, Laipuna) — anomaly detection, continuity checks, and bilingual (EN/DE) technical reports for field-maintenance decisions.

### 🧬 ML Research Pipelines
*Python*
- Contributed to large-scale image classification for the German Insect Monitoring Scheme and 3D medical/dental scan segmentation — ingestion, transformation, training-support, and evaluation pipelines.

<details>
<summary><strong>Academic / Coursework Projects</strong></summary>

- **[NLP_SS25](https://github.com/atulsan/NLP_SS25)** — Track A (Multi-label Emotion Detection), 2025 SemEval Shared Task 11.
- **[AAIB_SS25](https://github.com/atulsan/AAIB_SS25)** — Applied AI in Business: demand-forecasting and stocking decisions for an online retailer with limited storage capacity.
- **[XAI-WS24](https://github.com/atulsan/XAI-WS24)** — Explainable AI coursework project, WS24/25.

</details>

---

## Tech Stack

**Languages**
![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![Java](https://img.shields.io/badge/Java-007396?style=flat&logo=openjdk&logoColor=white)
![Go](https://img.shields.io/badge/Go-00ADD8?style=flat&logo=go&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat&logo=typescript&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![C++](https://img.shields.io/badge/C%2FC%2B%2B-00599C?style=flat&logo=cplusplus&logoColor=white)
![Bash](https://img.shields.io/badge/Bash-4EAA25?style=flat&logo=gnubash&logoColor=white)

**AI / ML**
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat&logo=pytorch&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=flat&logo=tensorflow&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat&logo=scikitlearn&logoColor=white)
![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?style=flat&logo=opencv&logoColor=white)
![Hugging Face](https://img.shields.io/badge/Transformers-FFD21E?style=flat&logo=huggingface&logoColor=black)

**Backend & Data**
![REST APIs](https://img.shields.io/badge/REST%20APIs-005571?style=flat)
![GraphQL](https://img.shields.io/badge/GraphQL-E10098?style=flat&logo=graphql&logoColor=white)
![Kafka](https://img.shields.io/badge/Apache%20Kafka-231F20?style=flat&logo=apachekafka&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat&logo=postgresql&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat&logo=mysql&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat&logo=redis&logoColor=white)
![Elasticsearch](https://img.shields.io/badge/Elasticsearch-005571?style=flat&logo=elasticsearch&logoColor=white)

**Frontend**
![React](https://img.shields.io/badge/React-61DAFB?style=flat&logo=react&logoColor=black)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat&logo=nodedotjs&logoColor=white)

**Cloud, DevOps & Observability**
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white)
![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=flat&logo=kubernetes&logoColor=white)
![Terraform](https://img.shields.io/badge/Terraform-7B42BC?style=flat&logo=terraform&logoColor=white)
![Ansible](https://img.shields.io/badge/Ansible-EE0000?style=flat&logo=ansible&logoColor=white)
![Jenkins](https://img.shields.io/badge/Jenkins-D24939?style=flat&logo=jenkins&logoColor=white)
![GitLab CI/CD](https://img.shields.io/badge/GitLab%20CI%2FCD-FC6D26?style=flat&logo=gitlab&logoColor=white)
![GCP](https://img.shields.io/badge/GCP-4285F4?style=flat&logo=googlecloud&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat&logo=amazonaws&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-F46800?style=flat&logo=grafana&logoColor=white)
![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=flat&logo=prometheus&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat&logo=linux&logoColor=black)

---

## Education

**M.Sc. Computer Science** — Philipps-Universität Marburg · Apr 2024 – Oct 2026 (expected)
Thesis: synthetic data generation and object detection for automated insect monitoring (see Featured Projects). University Assistant Teacher for Machine Learning; Head Tutor for International Students (2024–2025).

**B.Tech. Information Technology** — Motilal Nehru National Institute of Technology, Allahabad · 2017 – 2021
Student Arts Coordinator, 2018–2021.

---

## Recognition

- 🏆 Team Lead, Comviva Hackathon 2022 — 1st place
- 🎓 University Machine Learning Teaching Assistant, Philipps-Universität Marburg
- 🌍 Head Tutor for International Students, Marburg (2024–2025)

---

## GitHub Stats

![Atul's GitHub stats](https://github-readme-stats.vercel.app/api?username=atulsan&show_icons=true&theme=default&hide_border=true&count_private=true)
![Top Languages](https://github-readme-stats.vercel.app/api/top-langs/?username=atulsan&layout=compact&hide_border=true)

---

📫 Reach me at [athulsanthosh@gmail.com](mailto:athulsanthosh@gmail.com) or on [LinkedIn](https://www.linkedin.com/in/atul-santhosh/).
