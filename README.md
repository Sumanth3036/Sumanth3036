<!-- Save as README.md in a PUBLIC repo named exactly: Sumanth3036 -->

<div align="center">

![header](https://capsule-render.vercel.app/api?type=waving&color=0:0b132b,50:1c2541,100:3a506b&height=210&section=header&text=Sumanth%20Ponugupati&fontSize=44&fontColor=ffffff&animation=fadeIn&fontAlignY=38&desc=Backend%20%26%20AI%2FML%20Engineer&descAlignY=60&descSize=18)

[![Typing SVG](https://readme-typing-svg.demolab.com?font=Fira+Code&weight=500&size=19&pause=1300&color=5BC0BE&center=true&vCenter=true&width=760&lines=Real-time+systems+that+stay+up;LLM+agents+that+fail+less;I+find+why+it+breaks%2C+then+fix+the+pattern)](https://github.com/Sumanth3036)

![Location](https://img.shields.io/badge/Pune-India-1c2541?style=for-the-badge&logo=googlemaps&logoColor=5bc0be)
![Open to](https://img.shields.io/badge/Open_to-Backend_%7C_AI%2FML_%7C_SWE-5bc0be?style=for-the-badge&labelColor=1c2541)
![IEEE](https://img.shields.io/badge/IEEE-ICSSES_2025-3a506b?style=for-the-badge&logo=ieee&logoColor=white)

[Selected work](#selected-work) | [Research](#inside-the-research) | [System design](#system-design-think9) | [Experience](#experience) | [Stack](#stack) | [Contact](#contact)

</div>

---

## Snapshot

```text
name          Sumanth Ponugupati
role          Backend & AI/ML Engineer  |  B.Tech ECE, Amrita Vishwa Vidyapeetham (2026)
location      Pune, India
now           Trainee Engineer @ omniXM: built an internal product that monitors the health of all company products
before        Research Intern @ IIT Kharagpur (LLM data agents)  |  ML Intern @ LogiXair (real-time telemetry)
papers        3 published (IEEE ICSSES 2025 as sole author)
looking_for   Backend Engineer | AI/ML Engineer | Software Engineer  (Pune, Bengaluru, Hyderabad, remote)
```

## Selected work

| Project | What it proves | Stack |
|---|---|---|
| [**Data Agent Reliability Evaluation**](https://github.com/Sumanth3036/Data-Agent-Reliability-Evaluation) | Entity-resolution F1 **0.8992 to 0.9333**; found a sampling bug that tested only 3 of 900 true matches | Python, GPT-OSS-120B |
| [**Think9**](https://github.com/Sumanth3036/Think9-Multi-Agent-Knowledge-Assistant) | Multi-agent RAG with a confidence gate, human review and decision memory, with a pytest suite | FastAPI, Streamlit, ChromaDB, Llama 3.1 8B |
| [**DefectAI**](https://github.com/Sumanth3036/defectai) | **0.842 ROC-AUC** on unseen repositories; leakage-safe split; SHAP explanations | PyTorch, CodeBERT, FastAPI, React |
| [**Distributed Traffic Surveillance**](https://github.com/Sumanth3036/Distributed-Traffic-Surveillance-System) | Fault-tolerant master-worker pipeline: **+40% throughput, zero task loss** under worker failure | FastAPI, RabbitMQ, Redis, YOLOv11 |
| [**CipherTalk**](https://github.com/Sumanth3036/secure-chat-app) | Encrypted chat (AES-256, JWT, OTP) with a **96%+** accurate phishing classifier | FastAPI, CatBoost, MongoDB |
| [**SafeRoute**](https://github.com/Sumanth3036/Saferoute-Multi-Modal-Optimization-for-Crisis-Management-and-Evacuation) | Evacuation routing with **92.6% / 91.9%** earthquake / flood accuracy; [IEEE ICSSES 2025](https://ieeexplore.ieee.org/document/11009902) | Python, OSMnx, A*, Dijkstra |

## Inside the research

Budgeted pilot on Abt-Buy entity resolution (175 pairs), with failures analysed instead of just tuned away. The baseline made 13 false positives; grouping them showed 5 distinct failure patterns, and targeted prompt fixes corrected 9 of them.

| | Precision | Recall | F1 |
|---|---|---|---|
| Baseline | 0.8169 | 1.0000 | 0.8992 |
| After fixes | 0.9032 | 0.9655 | **0.9333** |

Precision rose and recall dropped slightly; the full trade-off, new errors and limitations are in the [report](https://github.com/Sumanth3036/Data-Agent-Reliability-Evaluation/blob/main/REPORT.md).

```mermaid
pie showData title 13 baseline false positives by failure pattern
    "Brand or category treated as identity" : 6
    "Specific SKU matched to generic listing" : 3
    "Matched on brand or product type only" : 2
    "Form-factor or SKU variant" : 1
    "Same model, different colour" : 1
```

**Lesson:** my first schema-matching run looked fine but sampled only 3 of 900 true matches. Check what your evaluation is actually measuring before trusting the score.

## System design: Think9

```mermaid
flowchart TD
    Q[Question] --> O[Orchestrator: keyword routing]
    O --> L[Legal agent]
    O --> B[Brand agent]
    O --> P[Operations agent]
    L --> R[Retrieval: ChromaDB + Sentence Transformers]
    B --> R
    P --> R
    R --> S[Synthesis: Llama 3.1 8B via Ollama]
    S --> G{Confidence at least 80?}
    G -- yes --> A[Approved]
    G -- no --> H[Human review]
    H --> A
    A --> M[(Decision memory)]
```

The model only sees retrieved evidence, must cite sources, and a human decides whenever confidence is low.

## Experience

| When | Where | What I did |
|---|---|---|
| Aug 2026 to now | **omniXM**, Trainee Engineer | Built an internal product end to end that monitors the health of all company products; redesigned AI systems |
| Aug to Sep 2026 | **IIT Kharagpur**, Research Intern | LLM data-agent reliability; reviewed 100+ papers (SIGMOD, VLDB, SIGIR, ICDE, CIKM) |
| May to Jul 2025 | **LogiXair**, ML Intern | Async telemetry APIs at **50 Hz, under 5 ms latency**; ML fault detection cut position error by **52%** |

## Stack

<div align="center">

![Stack](https://skillicons.dev/icons?i=py,fastapi,pytorch,tensorflow,js,ts,react,postgres,mysql,mongodb,redis,docker,aws,githubactions,linux,git,c&perline=9)

</div>

**Backend** FastAPI, REST, WebSocket, JWT, async Python, microservices, RabbitMQ
**AI/ML** PyTorch, TensorFlow, scikit-learn, CatBoost, YOLOv11, RAG, LLM evaluation
**Infra** Docker, GitHub Actions (CI/CD), AWS, Linux

## Publications

- **SafeRoute: Multi-Modal Optimization for Crisis Management and Evacuation**, IEEE ICSSES 2025 (sole author) | [IEEE Xplore](https://ieeexplore.ieee.org/document/11009902)
- **Embedded VPN Router Using Raspberry Pi**, ETCOM 2025 | [Semantic Scholar](https://www.semanticscholar.org/paper/Embedded-VPN-Router-Using-Raspberry-Pi-Renesh-Yallamelli/d8e2aa16d37d8f88aef62ad0baab0969131ccdcd)
- **Revolutionizing University Placements: Advanced Technologies for Streamlined Ecosystems**, ICRDICCT 2025

## Contact

<div align="center">

[![Portfolio](https://img.shields.io/badge/Portfolio-5bc0be?style=for-the-badge&logo=githubpages&logoColor=black)](https://sumanth3036.github.io/my-portfolio/)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/sumanthponugupati/)
[![Email](https://img.shields.io/badge/Email-1c2541?style=for-the-badge&logo=gmail&logoColor=white)](mailto:sumanthponugupati@gmail.com)

![footer](https://capsule-render.vercel.app/api?type=waving&color=0:3a506b,100:0b132b&height=100&section=footer)

</div>
