<div align="center">

# 🧬 PharmaGuard

**Precision Medicine. Personalized Dosing. Powered by AI.**

[![RIFT '26](https://img.shields.io/badge/Hackathon-RIFT_'26-7224ff.svg?style=for-the-badge)](https://rift.hackathon.com)
[![Team](https://img.shields.io/badge/Team-Squirtle_Squad-00cba9.svg?style=for-the-badge)]()
[![Track](https://img.shields.io/badge/Track-Pharmacogenomics_%2F_XAI-ff5a5f.svg?style=for-the-badge)]()
[![License](https://img.shields.io/badge/license-MIT-blue.svg?style=for-the-badge)]()

<br />

> **PharmaGuard bridges the gap between complex genetic data and clinical decision-making.** It analyses patient DNA against specific drug profiles to predict adverse reactions and provide explainable, guideline-aligned dosing recommendations.

[Explore the Demo](https://your-demo-link.com) · [Report Bug](https://github.com/your-username/pharmaguard/issues) · [Request Feature](https://github.com/your-username/pharmaguard/issues)

</div>

---

## 📸 Project UI/UX Showcase

We designed PharmaGuard with a clean, intuitive interface focused on clinical usability.

| **1. Data Input & Analysis** | **2. Explainable Results & Dosing** |
| :---: | :---: |
| _Medical professionals input the drug name and securely upload patient VCF genetic data._ | _AI-powered, easy-to-read summaries of genetic risks aligned with CPIC guidelines._ |
| ![Input Screen Placeholder](https://placehold.co/600x400/2a2a2a/FFF?text=Input+UI:+Upload+VCF+&+Drug+Name) | ![Results Screen Placeholder](https://placehold.co/600x400/2a2a2a/FFF?text=Results+UI:+AI+Summary+&+Dosing+Recs) |

---

## ✨ Key Features

PharmaGuard cuts through the noise of raw genetic data to provide actionable insights.

* **🧬 Secure VCF Parsing:** Efficiently processes raw Variant Call Format (VCF) patient files directly in the JavaScript backend.
* **🎯 Targeted Gene Analysis:** Focuses on 6 critical pharmacokinetic genes (including major *CYP450* enzymes) responsible for metabolizing most medications.
* **⚖️ Predictive Risk Profiling:** Determines the patient's metabolic phenotype (e.g., Poor Metabolizer, Ultra-Rapid Metabolizer) based on their specific genetic variants.
* **✅ CPIC Guideline Integration:** Dosing recommendations are strictly mapped to established Clinical Pharmacogenetics Implementation Consortium guidelines for safety.
* **🧠 Explainable AI (XAI):** We don't just give a score. We use an LLM to generate clear, natural language explanations for *why* a specific dose is recommended based on the genetics.

---

## 🛠️ Tech Stack

Our architecture is built for speed and data processing, relying heavily on a robust JavaScript backend.

<div align="center">

[![Node.js](https://img.shields.io/badge/Node.js-43853D?style=for-the-badge&logo=node.svg&logoColor=white)](https://nodejs.org/)
[![Express.js](https://img.shields.io/badge/Express.js-404D59?style=for-the-badge)](https://expressjs.com/)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)

[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)]()
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)]()

[![LLM API](https://img.shields.io/badge/AI-LLM_Integration-FF9900?style=for-the-badge)]()
[![Git](https://img.shields.io/badge/GIT-E44C30?style=for-the-badge&logo=git&logoColor=white)]()

</div>

### Architecture Overview

1.  **Client (Frontend):** Accepts drug name string and VCF file upload.
2.  **API Layer (Node/Express):** Receives data via POST request.
3.  **Data Processing Core (JS):**
    * Parses the complex VCF file structure.
    * Filters for specific variants within targeted CYP genes.
    * Maps found variants to known metabolic function profiles.
4.  **AI Integration:** The structured genetic profile + drug info is sent to the LLM API to generate the "Explainable rationale."
5.  **Response:** The backend compiles the risk profile, CPIC recommendation, and AI explanation and sends JSON back to the UI.

---

## 🚀 Getting Started Locally

To run the PharmaGuard backend and connect your UI for testing:

### Prerequisites
* [Node.js](https://nodejs.org/) (v18+)
* npm

### Installation Steps

1.  **Clone the Repo**
    ```bash
    git clone [https://github.com/your-username/pharmaguard.git](https://github.com/your-username/pharmaguard.git)
    cd pharmaguard
    ```

2.  **Install Backend Dependencies**
    The core logic lives here.
    ```bash
    cd backend
    npm install
    ```

3.  **Environment Setup