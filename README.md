# Carbon Manager

**Authors**: Sagnik Chakraborty, Purbayon Sarkar, Hrishikesh Saha  
**Institution**: South Point High School, Kolkata, West Bengal, India

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Architecture](#architecture)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
- [Usage](#usage)
- [Data Preparation & Model Training](#data-preparation--model-training)
- [Deployment](#deployment)
- [Security & Privacy](#security--privacy)
- [Roadmap](#roadmap)
- [Contributing](#contributing)
- [License](#license)
- [Acknowledgments](#acknowledgments)

## Overview

Carbon Manager is an AI-powered platform designed to help individuals and organizations accurately track, analyze, and mitigate their carbon footprints through intuitive dashboards and actionable insights. By answering a simple set of daily-activity questions via an interactive Q&A interface, even children as young as 5 can understand their environmental impact. Our platform addresses the pressing threat of global warming caused by greenhouse gases like carbon dioxide and methane, which trap heat in the Earth's atmosphere, deplete the ozone layer, and lead to extreme weather events and ecosystem disruptions. Understanding one’s personal carbon footprint is the first step towards meaningful climate action. Watch our demo video for a quick walkthrough: [Team Hackminors Video](https://www.youtube.com/watch?v=ENhW6AN1RK0).
## Features

- **AI Carbon Footprint Manager**  
  Possibly the world’s first fully AI‑driven footprint calculator, delivering highly accurate monthly carbon emissions predictions via an intuitive Q&A interface—even children aged 5+ can use it. Includes a dynamic graph and “Did You Know?” educational widget that surfaces global carbon facts and model insights at the bottom of the main tab. ([carbon-manager.vercel.app](https://carbon-manager.vercel.app/features))

- **Offset Options & Expert-Guided Planting**  
  Calculates the exact number of trees needed to counterbalance emissions and offers two pathways: self‑planting under certified expert supervision (with issuance of planting certificates) or donating carbon credits to partner NGOs for large‑scale reforestation projects. ([carbon-manager.vercel.app](https://carbon-manager.vercel.app/features))

- **Report & Offset Proof Submission with Blockchain Verification**  
  Users can export printable monthly reports (via browser print or menu) and submit offset proofs (e.g., certificates, bills) directly through the app. All submissions undergo immutable blockchain-backed verification alongside manual review, ensuring transparent and tamper‑proof record‑keeping. ([carbon-manager.vercel.app](https://carbon-manager.vercel.app/features))

- **Carbon Reward Points & Leaderboard**  
  Verified monthly submissions earn users redeemable Carbon Reward Points for eco‑friendly products, plus placement on a “Carbon Warriors” leaderboard to drive community competition and inspire broader participation. ([carbon-manager.vercel.app](https://carbon-manager.vercel.app/features))

- **Correction Factor**  
  An expert feedback mechanism invites industry authorities to compare their sensor or lab‑generated data against app predictions. Validated discrepancies feed into a dynamic correction factor that refines the neural network for ever‑greater accuracy. ([carbon-manager.vercel.app](https://carbon-manager.vercel.app/features))

- **AI Chatbot Plugin & Chat2Eco LLM**  
- **Plugin Integration**: Available on the documentation page and via an icon at the bottom-right of the footprint interface. *Please note the Chat UI is hosted on Render and may take up to 40 seconds to load on first access.* ([carbon-manager.vercel.app](https://carbon-manager.vercel.app/features))  
- **Base Model (Chat2Eco-180B)**: A sparse decoder-only Mixture-of-Experts network selecting **2 experts per token per layer**, merging parameter slices from Gemini 7B, LLaMA 70B-Chat, and Mixtral 8x7b via SLERP interpolation for high-capacity yet efficient inference.  
- **Fine-Tuned Model (Chat2Eco-180B-Chat)**: 132B total parameters (36B active per input), refined with QLoRA and SFT trainers on a ~12T-token corpus (Common Crawl, Wikipedia, proprietary). Training pipelines employ Jupyter Notebooks, Apache Spark, and advanced data processing tools.  
- **Capabilities**:  
  - **Multilingual** – Answers queries in multiple languages.  
  - **Idea Generation** – Provides innovative, domain-focused suggestions for carbon reduction.  
  - **Accurate Domain Responses** – Delivers precise environmental science insights.  
  - **Creative Writing** – Crafts poems, reports, speeches, and slogans on sustainability topics in various languages.  
- **Disclaimer**: Users should verify critical outputs against real-world data.  

**Community Discussion Forum**  
Powered by WIX with Velo APIs and Firebase for backend services, the forum replicates a social-media experience with user profiles, privacy settings, followable topics/groups, and customizable feeds. Users can ask questions, start discussions, share carbon-reduction strategies, and showcase their own projects. A badge system recognizes contributions, and monthly leaderboards highlight top “Carbon Warriors” to inspire continued engagement. ([carbon-manager.vercel.app](https://carbon-manager.vercel.app/features))

## Architecture

```
+-------------+      +----------------+      +----------------+
|   Frontend  | <--> |    Backend     | <--> |   ML Models    |
| (React/Tail)|      | (FastAPI)      |      | (Scikit-learn, |
+-------------+      +----------------+      |  PyTorch, etc.) |
                                           +----------------+
```

The platform comprises a React/Tailwind UI, a FastAPI backend exposing RESTful endpoints, and modular ML pipelines for data preprocessing, training, and inference.

## Getting Started

### Prerequisites

- Python 3.9+
- Node.js 16.x+
- Docker & Docker Compose
- Git

### Installation

1. **Clone the repository**

```bash
git clone https://github.com/your-org/carbon-manager.git
cd carbon-manager
```

2. **Backend setup**

```bash
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

3. **Frontend setup**

```bash
cd frontend
npm install
npm run build
cd ..
```

4. **Environment variables**\
   Create a `.env` file at the project root with the following:

```ini
DATABASE_URL=<postgresql://user:pass@localhost:5432/carbon_db>
SECRET_KEY=<super-secret-key>
MODEL_PATH=<path-to-trained-models>
```

## Usage

- **Run locally (development)**

```bash
docker-compose up --build
```

- **Access the app**\
  Open your browser at `http://localhost:3000`.

- **API Endpoints**

  - `POST /api/footprint` – Predict carbon footprint
  - `GET /api/offsets` – Retrieve tree offset options
  - `POST /api/forum` – Submit or fetch forum posts

## Data Preparation & Model Training

### Data Source

- Sourced from Kaggle and open repositories; refined to 10,000 entries with 5 numerical and 11 categorical features.

### Preprocessing

- Categorical encoding (One-Hot, Target Encoding)
- Numerical scaling (StandardScaler)
- Train/test split (80/20)

### Training Pipeline

Scripts available under `/ml/train.py`:

```bash
python ml/train.py --config configs/train_config.yaml
```

Key steps:

1. Load and clean data
2. Hyperparameter optimization via GridSearchCV
3. Model serialization to `models/`

## Deployment

- **Docker Image**

```bash
docker build -t carbon-manager .
```

- **Helm Chart**\
  Available in `/deploy/helm` for Kubernetes orchestration.

- **CI/CD**\
  Configured via GitHub Actions (`.github/workflows/ci.yml`) for linting, testing, and Docker deployment.

## Security & Privacy

- **Encryption**: AES-256 for data at rest, TLS 1.3 for in transit
- **Authentication**: OAuth2 with JWT and multi-factor
- **Access Control**: RBAC enforced at API gateway
- **Audit Logging**: Immutable logs stored on-chain for report verification

## Project Goals & UN SDG Alignment

**UN Sustainable Development Framework**  
The 2030 Agenda for Sustainable Development, adopted by all United Nations members in 2015, established 17 Sustainable Development Goals (SDGs) aimed at achieving peace and prosperity for people and the planet while addressing climate change and preserving natural ecosystems. Our Carbon Manager platform directly supports key environmental SDGs through AI-driven footprint analysis and community engagement.

**Aligned SDGs & Expected Outcomes**  
- **Goal 3 — Good Health and Well-being**: Mitigating carbon emissions improves air quality and reduces climate-related health risks—such as respiratory illnesses and vector-borne diseases—thereby supporting healthier communities.

- **Goal 7 — Affordable and Clean Energy**: By promoting awareness of energy consumption patterns and encouraging shifts to low-carbon behaviors, Carbon Manager contributes to sustainable energy usage and efficiency.

- **Goal 11 — Sustainable Cities and Communities**: Our platform’s data-driven insights support urban planning and individual action to reduce emissions in densely populated areas, enhancing resilience against extreme weather events.

- **Goal 12 — Responsible Consumption and Production**: Carbon Manager fosters sustainable lifestyle choices by quantifying environmental impact and suggesting practical reduction strategies, aligning with circular economy principles.

- **Goal 13 — Climate Action**: At its core, the project empowers users to take tangible steps—planting trees, offsetting emissions, and verifying impact—to combat climate change and track progress.

- **Goal 15 — Life on Land**: Through expert-guided planting programs and partnerships with NGOs, the platform directly supports reforestation efforts and ecosystem restoration.

## Roadmap

- Support real-time data ingestion from IoT sensors
- Mobile application (iOS/Android)
- Advanced explainability dashboard (SHAP/LIME)
- Automated carbon credit marketplace integration

## Contributing

We welcome contributions! Please follow our [Contributing Guide](CONTRIBUTING.md):

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/YourFeature`)
3. Commit your changes (`git commit -m 'Add new feature'`)
4. Push to the branch (`git push origin feature/YourFeature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.

## Additional Resources

- **Project Documentation**: [Carbon Manager Docs](https://teamhackminors.github.io)  
- **AI Carbon Footprint Manager**: [Live Application](https://teamhackminors.github.io/carbonfootprintmanager)  
- **Chat2Eco UI**: [AI Chatbot Interface](https://chatbot-apon.onrender.com) *(may take up to 40 seconds to load)*  
- **Carbon Manager Forum**: [Community Discussion](https://bit.ly/CarbonManagerForum)  
- **Live Features Demo**: [Features Page](https://carbon-manager.vercel.app/features)  
- **Google Drive Presentation**: [Project Overview](https://drive.google.com/file/d/14MoovBMj2122y3CTeu4lmf-2yW3lRqpc/preview)

## Contact

For questions or support, reach out to Team Hackminors at [teamhackminors@gmail.com](mailto:teamhackminors@gmail.com).

## Acknowledgments
- IPCC, Global Carbon Project data references
- OpenAI, scikit-learn, FastAPI, React, and all open-source contributors

