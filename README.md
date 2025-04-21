# Carbon Manager

**Authors**: Sagnik Chakraborty, Purbayon Sarkar, Hrishikesh Saha  
**Institution**: South Point High School, Kolkata, West Bengal, India

## License

Copyright © 2025 Purbayon Sarkar, 2025
All Rights Reserved.

1. Definitions
   a. “The Software” refers to the entire contents of this repository, including source code, documentation, images, and any other files.
   b. “You” (or “Licensee”) refers to any person or entity that accesses or uses The Software.
   c. “Licensor” refers to the copyright owner.

2. Grant of Rights
   No rights are granted to You under this license. All rights in and to The Software are retained exclusively by the Licensor.

3. Restrictions
   You may NOT, under any circumstances:
   a. Copy, distribute, or sublicense The Software, in whole or in part;
   b. Create derivative works or adaptations of The Software;
   c. Use The Software for any purpose, commercial or non‑commercial;
   d. Reverse engineer, decompile, disassemble, or otherwise attempt to discover the source code of The Software;
   e. Remove or modify any copyright, trademark, or other proprietary notices contained in or on The Software.

4. Termination
   This license and your right to access The Software terminate immediately upon any breach of the terms laid out herein. Upon termination, you must destroy all copies of The Software in your possession.

5. Disclaimer of Warranty
   The Software is provided “AS IS” and without any warranty, express or implied, including but not limited to warranties of merchantability, fitness for a particular purpose, or non‑infringement. The entire risk as to the quality, performance, and accuracy of The Software remains with You.

6. Limitation of Liability
   Under no circumstances shall the Licensor be liable for any damages (including, without limitation, direct, indirect, incidental, consequential, special, punitive, or exemplary damages) arising out of or in connection with the use of or inability to use The Software, even if advised of the possibility of such damages.

7. Governing Law
   This License shall be governed by and construed in accordance with the laws of Indian Jurisdiction, without regard to conflict‑of‑law principles.
© 2025 Purbayon Sarkar. All rights reserved.

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Security & Privacy](#security--privacy)

## Youtube Video
Please go through our [project demonstration video](https://www.youtube.com/watch?v=ENhW6AN1RK0).

## Overview

Carbon Manager is an AI-powered platform designed to help individuals and organizations accurately track, analyze, and mitigate their carbon footprints through intuitive dashboards and actionable insights. By answering a simple set of daily-activity questions via an interactive Q&A interface, even children as young as 5 can understand their environmental impact. Our platform addresses the pressing threat of global warming caused by greenhouse gases like carbon dioxide and methane, which trap heat in the Earth's atmosphere, deplete the ozone layer, and lead to extreme weather events and ecosystem disruptions. Understanding one’s personal carbon footprint is the first step towards meaningful climate action. Watch our demo video for a quick walkthrough: 

## ([Features](https://carbon-manager.vercel.app/features))

- **[AI Carbon Footprint Calculator](https://carbonmanager.streamlit.app/)**  
  Possibly the world’s first fully AI‑driven footprint calculator, delivering highly accurate monthly carbon emissions predictions via an intuitive Q&A interface—even children aged 5+ can use it. Includes a dynamic graph and “Did You Know?” educational widget that surfaces global carbon facts and model insights at the bottom of the main tab.

- **Offset Options & Expert-Guided Planting**  
  Calculates the exact number of trees needed to counterbalance emissions and offers two pathways: self‑planting under certified expert supervision (with issuance of planting certificates) or donating carbon credits to partner NGOs for large‑scale reforestation projects.

- **Report & Offset Proof Submission with Blockchain Verification**  
  Users can export printable monthly reports (via browser print or menu) and submit offset proofs (e.g., certificates, bills) directly through the app. All submissions undergo immutable blockchain-backed verification alongside manual review, ensuring transparent and tamper‑proof record‑keeping.

- **Carbon Reward Points & Leaderboard**  
  Verified monthly submissions earn users redeemable Carbon Reward Points for eco‑friendly products, plus placement on a “Carbon Warriors” leaderboard to drive community competition and inspire broader participation.

- **Correction Factor**  
  An expert feedback mechanism invites industry authorities to compare their sensor or lab‑generated data against app predictions. Validated discrepancies feed into a dynamic correction factor that refines the neural network for ever‑greater accuracy.

- **[Chat2Eco LLM](https://cm-chat.onrender.com/)**  
- **Plugin Integration**: Available on the documentation page and via an icon at the bottom-right of the footprint interface. *Please note the Chat UI is hosted on Render and may take up to 40 seconds to load on first access.*
- **Base Model (Chat2Eco-180B)**: A sparse decoder-only Mixture-of-Experts network selecting **2 experts per token per layer**, merging parameter slices from Gemini 7B, LLaMA 70B-Chat, and Mixtral 8x7b via SLERP interpolation for high-capacity yet efficient inference.  
- **Fine-Tuned Model (Chat2Eco-180B-Chat)**: 132B total parameters (36B active per input), refined with QLoRA and SFT trainers on a ~12T-token corpus (Common Crawl, Wikipedia, proprietary). Training pipelines employ Jupyter Notebooks, Apache Spark, and advanced data processing tools.  
- **Capabilities**:  
  - **Multilingual** – Answers queries in multiple languages.  
  - **Idea Generation** – Provides innovative, domain-focused suggestions for carbon reduction.  
  - **Accurate Domain Responses** – Delivers precise environmental science insights.  
  - **Creative Writing** – Crafts poems, reports, speeches, and slogans on sustainability topics in various languages.  
- **Disclaimer**: Users should verify critical outputs against real-world data.  

**[Community Discussion Forum](https://appdevelopersagnik.wixsite.com/carbon-manager-forum)**  
Powered by WIX with Velo APIs and Firebase for backend services, the forum replicates a social-media experience with user profiles, privacy settings, followable topics/groups, and customizable feeds. Users can ask questions, start discussions, share carbon-reduction strategies, and showcase their own projects. A badge system recognizes contributions, and monthly leaderboards highlight top “Carbon Warriors” to inspire continued engagement.

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

## Additional Resources

- **Project Documentation**: [Carbon Manager Docs](https://teamhackminors.github.io)  
- **AI Carbon Footprint Calculator**: [Live Application](https://teamhackminors.github.io/carbonfootprintmanager)  
- **Chat2Eco UI**: [AI Chatbot Interface](https://cm-chat.onrender.com/) *(may take up to 40 seconds to load)*  
- **Carbon Manager Forum**: [Community Discussion](https://appdevelopersagnik.wixsite.com/carbon-manager-forum)  
- **Live Features Demo**: [Features Page](https://carbon-manager-hackminors-2025.vercel.app/features)  
- **Google Drive Presentation**: [Project Overview](https://drive.google.com/uc?export=download&id=14MoovBMj2122y3CTeu4lmf-2yW3lRqpc)

## Contact

For questions or support, reach out to Team Hackminors at [teamhackminors@gmail.com](mailto:teamhackminors@gmail.com).
