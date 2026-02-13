# 🛡️ Semantics-Aware LLM Security Gateway (v3.3)
### Triple-Anchor Defense Against Multilingual Prompt Injection & Destructive Intent

[![IEEE Region 8](https://img.shields.io/badge/Target-IEEE%20Region%208-blue.svg)](https://www.ieee.org/)
[![Python 3.8+](https://img.shields.io/badge/python-3.8+-green.svg)](https://www.python.org/)

This repository contains the official implementation of the **Semantic Guard 3D**, a security middleware designed to protect Large Language Models (LLMs) from complex prompt injections. It specializes in bridging the gap for low-resource scripts like **Arabizi** (Levantine/Jordanian Arabic).

---

## 🚀 Key Innovations
- **Triple-Anchor Semantic Scoring:** A novel defense mechanism that analyzes inputs across three vector dimensions: Attack patterns, Safe anchors, and Destructive intent.
- **Arabizi Support:** Native detection for Romanized Arabic dialects, often bypassed by global safety filters.
- **Auto-Calibration Engine:** Data-driven threshold searching to optimize the balance between security (Recall) and usability (Precision).
- **Intent-Aware Filtering:** Differentiates between educational queries (e.g., "What is hacking?") and malicious instructions.

## 🧠 Methodology
The core engine computes a **Net Threat Score** ($S_{net}$) using the following weighted equation:

$$S_{net} = \text{Sim}(x, \mathcal{V}_{atk}) - (\alpha \cdot \text{Sim}(x, \mathcal{V}_{safe})) + (\beta \cdot \text{Sim}_{gated}(x, \mathcal{V}_{dest}))$$

Where:
- $\alpha$: Safe Dampening coefficient.
- $\beta$: Destructive Boost coefficient.

## 📊 Experimental Results (N=4,368)
| Metric | Keywords (Baseline) | **Proposed AI Gateway** |
| :--- | :---: | :---: |
| **Accuracy** | 61.5% | **75.9%** |
| **Recall (Detection Rate)** | 24.9% | **90.1%** |
| **F1-Score** | 0.38 | **0.79** |

---

## 📂 Repository Structure
- `src/`: Core implementation and gateway logic.
- `data/`: The augmented multilingual dataset (CSV).
- `figures/`: Benchmark visualizations and confusion matrices.
- `requirements.txt`: Necessary Python dependencies.

## 🛠️ Installation
```bash
git clone [https://github.com/YOUR_USERNAME/Semantic-LLM-Guard.git](https://github.com/YOUR_USERNAME/Semantic-LLM-Guard.git)
cd Semantic-LLM-Guard
pip install -r requirements.txt
