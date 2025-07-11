# DPP-Based Diversified Recommendation Demo

This repository contains demo code for the implementation of **Determinantal Point Process (DPP)** sampling in the *pass Culture* recommendation pipeline.

> 🔬 This code is a simplified demonstration of the approach used in our paper:  
> **"Diversified recommendations of cultural activities with personalized determinantal point processes"**  
> It is meant for educational and research purposes and does **not reflect the complexity of the production system** used in the actual pass Culture infrastructure.
> The production code can be found in these PRs: [PR with quality scores equal to two tower relevance score](https://github.com/pass-culture/data-gcp/pull/4074) and [PR with quality scores equal to 1](https://github.com/pass-culture/data-gcp/pull/4073)

---

## About the Project

In the pass Culture application, we aim to generate **diverse and personalized recommendations** of cultural activities (e.g., theater, books, concerts). While standard recommenders often prioritize only relevance, our method incorporates **diversity** using **Determinantal Point Processes (DPPs)**.

This demo shows how we integrated DPP into our recommendation pipeline illustrated in the following chart.

![alt text](images/pipeline_diagram.png "Overview of the pass Culture recommender architecture with DPP integration.")

This demo simplifies the production pipeline by only showing the interesting part: 
- the Data folder contains sample item embeddings and samples of usera nd item two tower embeddings. These samples are taken from production model from July 2025. Users information are completely protected.
- We use the same dpp class as in the prodcution code but with the samples embeddings
- the [`dppy`](https://github.com/guilgautier/dppy) library is the one we use in production 
- Visualize the impact of DPP-based diversification on items recommended with and without the dpp filter. We also add metrics calculations like used in the paper. 

---

## 📁 Repository Structure
run tree after you finish

---

## Getting Started

### Prerequisites

- Python ≥ 3.8
- Install dependencies:

```bash
pip install -r requirements.txt
```

## Main libraries used:

- numpy, scikit-learn, matplotlib

- [dppy](https://dppy.readthedocs.io/en/latest/) (Determinantal Point Process library)

## Running the Demo
Run the main pipeline via script:

```bash
python src/recommender.py
```

Or explore interactively with the notebook demo_dpp.ipynb

## Demo Overview
1- Simulate user-item relevance scores
2- Create item embeddings (toy data or realistic embeddings)
3- Sample diverse recommendation sets using DPP
4- Compare top-k relevance-only selection with DPP-enhanced selection

## Reference
If you find this project useful in your work, please consider citing:

Diversified recommendations of cultural activities with personalized determinantal point processes
Authors: Carole Ibrahim, Hiba Bederina, Daniel Cuesta, Laurent Montier, Cyrille Delabre, Jill-Jênn Vie
Submitted to: RecSoGood
Year: 2025

## 💡 Notes
The production-grade implementation used at pass Culture is significantly more complex, integrating:
- APIs and feature stores
- Multi-stage recommender logic
- Real-time and batch environments

This demo focuses solely on the core DPP sampling logic for clarity and reproducibility.

## 📬 Contact
Feel free to reach out with questions or feedback via Issues or email.

License: MIT
Maintainers: Carole Ibrahim, pass Culture
