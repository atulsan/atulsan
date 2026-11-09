# Atul Santhosh

### Backend & AI Systems Engineer · M.Sc. Computer Science, Philipps-Universität Marburg

[![Email](https://img.shields.io/badge/Email-athulsanthosh%40gmail.com-D14836?style=flat&logo=gmail&logoColor=white)](mailto:athulsanthosh@gmail.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-atul--santhosh-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/atul-santhosh/)
![Location](https://img.shields.io/badge/Location-%2C%20Germany-555555?style=flat)


---

## About

I build production backend systems and applied AI/ML pipelines. Right now that means sole-engineer ownership of a full-stack research platform at Philipps-Universität Marburg, on top of ~3 years shipping backend services for high-traffic telecom systems at Comviva. Recent work spans a Kafka-based distributed backend handling millions of daily messages, a synthetic-data pipeline that generated 27,000 labelled images for a computer-vision thesis, and diagnosing a bug that had inflated that thesis's reported accuracy by ~52% before I caught and fixed it.

I like work that sits at the boundary of infrastructure and product — systems that have to stay up, and interfaces that make them usable by people who aren't engineers.

**Core strengths:**
- Production backend engineering — Java, Go, C/C++, Python, TypeScript, REST APIs, microservices, Kafka, PostgreSQL, MySQL, Redis, distributed systems.
- AI/ML systems — PyTorch, TensorFlow, Hugging Face Transformers, LLM workflows, RAG, agentic orchestration, semantic search, Elasticsearch, torchaudio, WhisperX, FFmpeg, model evaluation.
- Full-stack product engineering — React, TypeScript, Node.js, REST integration, component architecture, state management, researcher-facing UIs.
- DevOps and reliability — Docker, Kubernetes, Helm, Jenkins, GitLab CI/CD, Terraform, Ansible, GCP, AWS, Grafana, Prometheus, SigNoz, observability.
- Product-minded collaboration — hackathon-winning GenAI/Jira automation, documentation for non-technical domain experts, mentoring, cross-functional delivery.

---

## Experience

**🔭 Research Assistant, Machine Learning and Systems** — *Philipps-Universität Marburg* · Mar 2025 – Present
- Built a full-stack research platform (TypeScript, React, Python, REST APIs, Elasticsearch) for interactive exploration and analysis of large historical speech datasets — see [Full-Stack Speech Research Platform](#-full-stack-speech-research-platform) below.
- Designed structured retrieval and indexing pipelines for transcripts and metadata, supporting contextual search and downstream model workflows.
- Built audio and data-processing pipelines using WhisperX, torchaudio, FFmpeg, Mel-spectrogram preprocessing, and structured time-coded outputs.
- Developed and evaluated PyTorch/transformer-based workflows for historical speech annotation, including preprocessing, model adaptation, training, evaluation, and visualization tooling.
- Built and deployed LLM/agentic AI workflows for multi-step contextual retrieval, orchestration, and output validation.
- Processed and quality-checked climate-station logger data for environmental monitoring sites in Ecuador and Laipuna — see [Climate Station Data Quality Control](#️-climate-station-data-quality-control) below.
- Contributed to research ML projects including large-scale image classification for the German Insect Monitoring Scheme and 3D medical scan segmentation.
- Wrote technical documentation, system guides, and user-facing tutorials for historians, biologists, students, and other non-engineering domain experts.
- Served as University Machine Learning Teaching Assistant, supporting students on attention mechanisms, backpropagation, model evaluation, datasets, and practical debugging.
- Designed datasets for two student Kaggle hackathons: car price prediction and image object detection.
- Used AI-assisted engineering tools such as Claude Code and Cursor as part of the day-to-day development workflow.

**💼 Senior Software Engineer** — *Comviva* · Dec 2022 – Mar 2024
- Designed and shipped production backend services and REST APIs in Java and Go for high-traffic telecom messaging platforms.
- Led architecture/design for backend integration services, applying SOLID principles, service decomposition, interface design, API specifications, and architecture records.
- Engineered distributed, high-throughput systems with Kafka event pipelines, concurrent execution, load balancing, ordered message delivery, and latency-sensitive production behavior.
- Built comprehensive unit and integration test suites, regression baselines, peer review habits, and delivery discipline across production services.
- Built and tuned Docker, Kubernetes, Helm, Jenkins, GitLab CI/CD, and GCP-based deployment workflows.
- Introduced Grafana, Prometheus/SigNoz-style observability — dashboards, latency metrics, alerting, root-cause analysis, and production debugging practices.
- Implemented Redis/KeyDB failover mechanisms that improved service recovery by up to 98%.
- Mentored junior engineers and collaborated cross-functionally with product, QA, and DevOps stakeholders in Agile/Kanban teams.
- Won Comviva Hackathon 2022 as team lead — see [Agentic LLM / Jira Automation System](#-agentic-llm--jira-automation-system) below.

**💼 Software Engineer** — *Comviva* · Jul 2021 – Nov 2022
- Developed operational C/C++ and backend software for live telecom systems.
- Built SMS Gateway integration with protocol-level reliability and zero-data-loss expectations.
- Implemented SOS emergency-communication functionality for Volvo vehicle communication workflows, with safety-critical, real-time delivery requirements.
- Owned technical requirements analysis, implementation, integration support, testing, documentation, and commissioning-adjacent work.

---

## Featured Projects

### 🐛 Synthetic Data Generation & Object Detection for Automated Insect Monitoring
*M.Sc. Thesis — Python, PyTorch, RF-DETR, DINOv2, YOLOv8, BiRefNet, OpenCV, NumPy, pandas, Matplotlib, Albumentations, ONNX, COCO/YOLO formats, Label Studio, CUDA/A100, Linux/HPC*
- Built an end-to-end synthetic-data pipeline compositing BiRefNet-segmented specimen cutouts onto real tray backgrounds with physically calibrated sizing (petri-dish scale → millimetres → tray pixels), generating up to 27,000 fully labelled images across 23 taxonomic classes with no manual annotation.
- Found and fixed a train/test leakage flaw that had inflated reported accuracy by ~52% (mAP@50:95 0.467 → an honest 0.308), by redesigning the pipeline around specimen-level disjoint splits — establishing the defensible evaluation baseline for the thesis.
- Benchmarked a transformer detector (RF-DETR, DINOv2 backbone) against a CNN detector (YOLOv8-L / flatbug) on identical data: flatbug reached 0.365 vs 0.294 mAP@50:95 (+0.13 at the strict mAP@75 threshold) and won 18 of 23 classes.
- Ran controlled ablations on cutout-pool size (5k vs 20k), model capacity (YOLOv8-M vs L), and dataset scale, showing accuracy was limited by data distribution rather than model capacity or sample count — redirecting the research effort from scaling to domain realism.
- Closed the sim-to-real gap by quantitatively profiling real pitfall-trap imagery (brightness, dark-pixel fraction, colour cast) and building a procedural multi-scale soil renderer calibrated to those measurements (synthetic 92 brightness / 61% dark vs real 89 / 59%).
- Diagnosed a size-based "catch-all" failure mode funnelling 76% of real-world detections into two classes, tracing the root cause to an augmentation strategy — not input data quality — via per-class diagnostics.
- Designed a two-stage transfer-learning strategy: pretrain on real single-class arthropod imagery for localisation, fine-tune on synthetic multi-class data for classification — verified against the framework internals to confirm bounding-box weights are preserved while the classifier head is re-initialised.
- Built a model-assisted annotation handoff (1,540 pre-drawn boxes across 85 real images, Label Studio format) to cut expert labelling effort for domain scientists.
- Built a self-contained evaluation suite (COCO 101-point AP, confusion matrices, precision/recall/F1 curves, per-class reporting) for a framework that shipped without one.
- Trained on NVIDIA A100 80GB GPUs in headless Linux/HPC environments, with COCO/YOLO/ONNX format conversion and export.

### 🔎 Full-Stack Speech Research Platform
*React, TypeScript, Python, REST APIs, Elasticsearch, WhisperX, torchaudio, FFmpeg*
- Sole engineer on a full-stack platform giving historians, linguists, and biologists interactive search, annotation, and exploration access to large historical speech datasets.
- Designed structured retrieval and indexing pipelines for transcripts and metadata, supporting contextual search and downstream model workflows.
- Integrated audio-processing pipelines (WhisperX, torchaudio, FFmpeg, Mel-spectrogram preprocessing) directly into the platform, turning raw audio into structured, time-coded, searchable outputs.
- Added an LLM/agentic retrieval layer for multi-step contextual retrieval and orchestration, with output-validation loops before results reach users.
- Owned every deployment and infrastructure decision for the platform, from architecture through production operation.
- Wrote technical documentation and user-facing tutorials that let non-engineering domain experts use the platform without engineering support.
- Used AI-assisted engineering tools (Claude Code, Cursor) as a standard part of the daily build/iterate workflow.

### 🎙️ Historical Speech Annotator / Historical Speech Signal Analyser
*PyTorch, torchaudio, Mel-spectrogram preprocessing — the ML component behind the platform above*
- Adapted a PMAM Transformer model for historical speech annotation and signal analysis.
- Built speech/audio feature extraction, training/evaluation workflows, and visualization tooling.
- Built automated annotation and interpretation tooling to support historians and other domain experts.

### 🤖 Agentic LLM / Jira Automation System
*Comviva Hackathon 2022 — 1st place, team lead*
- Led a team of 4 engineers to ship an LLM support agent in 4 weeks, combining multi-step reasoning, RAG-style context, and direct Jira API automation for structured issue/output generation.
- Turned support context into auto-created engineering tickets by integrating retrieval, LLM generation, and external API calls.
- Practical proof point for LLM orchestration and developer tooling inside a real software development lifecycle, not a toy demo.

### 🌱 [Sahyog App](https://github.com/atulsan/Sahyog-App)
*Android, Firebase, Mapbox — archived*
- Android app for reducing food waste by connecting surplus-food donors with nearby recipients.
- Geolocation matching, real-time alerts, and direct messaging workflows between donors and recipients.

### 🌦️ Climate Station Data Quality Control
*Python, pandas, data visualization, EN/DE technical writing*
- Automated QC for raw logger data across a 14-station tropical/Andean sensor network (Ecuador and Laipuna).
- Checked for missing or malformed rows, duplicate timestamps, continuity gaps, physically impossible values, stuck sensors, NULL values, swapped channels, moisture issues, power gaps, and logger/communication problems.
- Analyzed meteorological and environmental sensor data — temperature, humidity, precipitation, wind, radiation, soil, pressure, fog/load-cell, and NDVI-related measurements — to identify sensor faults and maintenance needs.
- Produced plots and bilingual (English/German) technical reports with anomaly visualizations, station-outage summaries, sensor-replacement questions, and field-maintenance follow-up recommendations for collaborators.

### 🧬 ML Research Pipelines
*Python*
- Contributed to large-scale image classification for the German Insect Monitoring Scheme.
- Contributed to 3D medical/dental scan segmentation.
- Built Python pipelines for ingestion, transformation, training support, evaluation, and reproducibility.

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

Also: LLM workflows, agentic orchestration, RAG, semantic search, model evaluation, object detection (YOLOv8, RF-DETR, DINOv2), image segmentation (BiRefNet), synthetic data generation, transfer learning, CUDA/A100 training.

**Backend & Data**
![REST APIs](https://img.shields.io/badge/REST%20APIs-005571?style=flat)
![GraphQL](https://img.shields.io/badge/GraphQL-E10098?style=flat&logo=graphql&logoColor=white)
![Kafka](https://img.shields.io/badge/Apache%20Kafka-231F20?style=flat&logo=apachekafka&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat&logo=postgresql&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat&logo=mysql&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=flat&logo=mongodb&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat&logo=redis&logoColor=white)
![Elasticsearch](https://img.shields.io/badge/Elasticsearch-005571?style=flat&logo=elasticsearch&logoColor=white)

Also: gRPC/Protobufs, microservices, SOLID principles, service decomposition, event-driven design, RabbitMQ, SNS/SQS, Google Pub/Sub, concurrency, load balancing, fault-tolerant systems, API security, authentication flows.

**Frontend**
![React](https://img.shields.io/badge/React-61DAFB?style=flat&logo=react&logoColor=black)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat&logo=nodedotjs&logoColor=white)

Also: Next.js-adjacent React patterns, HTML, CSS, Material UI, react-query, component architecture, state management, responsive UI, researcher/domain-expert workflows.

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

Also: Helm, SigNoz, monitoring, alerting, root-cause analysis, incident debugging, Git/GitHub, Jira.

**Documentation & Collaboration**
Technical writing, system documentation, API specifications, architecture guides, tutorials for non-technical users, code reviews, retrospectives, Agile/Kanban, cross-functional coordination, mentoring.

---

## Education

**M.Sc. Computer Science** — Philipps-Universität Marburg · Apr 2024 – Oct 2026 (expected)
Thesis: synthetic data generation and object detection for automated insect monitoring (see Featured Projects). University Assistant Teacher for Machine Learning; Head Tutor for International Students (2024–2025); student-facing dataset design and academic support.

**B.Tech. Information Technology** — Motilal Nehru National Institute of Technology, Allahabad · 2017 – 2021
Student Arts Coordinator, 2018–2021.

**Languages:** English (fluent) · German (A1)

---

## Recognition

- 🏆 Team Lead, Comviva Hackathon 2022 — 1st place
- 🎓 University Machine Learning Teaching Assistant, Philipps-Universität Marburg
- 🌍 Head Tutor for International Students, Marburg (2024–2025)
- 🎨 Student Arts Coordinator, MNNIT Allahabad (2018–2021)

---

📫 Reach me at [athulsanthosh@gmail.com](mailto:athulsanthosh@gmail.com) or on [LinkedIn](https://www.linkedin.com/in/atul-santhosh/).
