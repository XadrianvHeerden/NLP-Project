<p align="center">
  <img src="" width="240" height="auto">

  <h1 align="center">NLP Project</h1>
  <h3 align="center">African Languages for Emotion Analysis</h3>

<div align="center">

<h3 align="center">Intro
</h3>

| Resource                             | Description                                                                                                                         |
|--------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| [Documentation]()                                                                                                                             | Details on project         |
| [Report]()                                                                                                                                    | Finalised Report        |
| [Baseline Model]()                                                                                                             | Base Model        |
| [Augmentation Models]()                                                                                                        | Augmentation methods        |

<h1 align="center"> Demo Recoreded </h1>

|                         | Video | Slides |
|---------------------------------|---------------------------------|---------------------------------|
| NLP Project | [Video]() | [Slides]() |

<h3 align="center">Requirements</h3>

<h3 align="center">Installation and running
</h3>

# 🧠 African Languages for Emotion Analysis
**Enhancing Emotion Classification through Data Augmentation Strategies for Low-Resource African Languages**

This repository contains the code, models, and data processing workflows for our research on applying **data augmentation** techniques to improve **multi-label emotion classification** in **low-resource African languages** — specifically Swahili, Hausa, and Afrikaans — using the **BRIGHTER dataset** and the `Davlan/afro-xlmr-small` model.

---

## 📂 Folder Structure

```
├── notebooks/
│   ├── 1_basemodel.ipynb             # Base training without augmentation
│   ├── 2_random_insertion.ipynb      # Training with Random Insertion augmentation
│   ├── 3_masking.ipynb               # Training with Masked Language Model augmentation
│   ├── 4_back_translation.ipynb      # Training with Round Trip Back Translation
│
├── data/
│   ├── raw/                          # Unprocessed BRIGHTER dataset splits
│   ├── processed/                    # Preprocessed & multi-hot encoded data
│
├── models/                           # Saved fine-tuned model checkpoints
│
├── utils/
│   ├── data_loader.py                # Data loading, splitting, encoding
│   ├── augmentation.py               # Core augmentation functions
│
├── reports/
│   ├── slides.pdf                    # Final presentation slides
│   ├── report.pdf                    # Final project writeup or paper (optional)
│
├── README.md                         # Project overview and instructions
├── requirements.txt                  # Python dependencies
└── run.sh                            # Shell script to reproduce training from CLI
```

---

## 📘 Project Overview

Despite rapid progress in NLP, **low-resource African languages** remain severely underrepresented in emotion classification research. This project evaluates the effectiveness of **three data augmentation techniques**:
- **Random Insertion using fastText**
- **Masked Token Prediction (MLM)**
- **Round-Trip Back Translation (Helsinki-NLP & NLLB)**

All experiments are conducted using the **Davlan/afro-xlmr-small** transformer model, trained on a subset of the **BRIGHTER dataset** for Swahili, Hausa, and Afrikaans.

---

## 🛠️ Requirements

Before running the code, create a virtual environment and install dependencies:

```bash
python -m venv env
source env/bin/activate  # or .\env\Scripts\activate on Windows
pip install -r requirements.txt
```

> Requires Python 3.8+, PyTorch 1.13+, HuggingFace Transformers, Datasets, fastText, and sacreBLEU

---

## 🚀 How to Run

You can execute each experiment by opening the corresponding notebook under `/notebooks`:

| Task                              | Notebook Name                 |
|----------------------------------|-------------------------------|
| Baseline training                | `1_basemodel.ipynb`           |
| Random Insertion Augmentation    | `2_random_insertion.ipynb`    |
| Masked Language Model Augmentation | `3_masking.ipynb`            |
| Back Translation Augmentation    | `4_back_translation.ipynb`    |

Alternatively, you can run experiments from terminal:

```bash
bash run.sh baseline
bash run.sh random_insertion
bash run.sh masking
bash run.sh back_translation
```

---

## 🎥 Presentation & Slides

- 📽️ [Watch our project video](https://example.com/project-video)  
- 📑 [View our final slides](https://example.com/slides)

*(Replace links with your actual URLs)*

---

## 📈 Results Summary

| Language  | Augmentation        | Micro F1 | Macro F1 | Hamming Loss | Subset Accuracy |
|-----------|---------------------|----------|----------|---------------|------------------|
| Afrikaans | Back Translation    | 0.7912   | 0.6667   | 0.0688        | 0.7408           |
| Swahili   | Back Translation    | 0.6726   | 0.6006   | 0.1027        | 0.6049           |
| Hausa     | Random Insertion    | 0.7690   | 0.7624   | 0.0865        | 0.6175           |

---

## 🤝 Acknowledgements

This project was developed as part of a research initiative at the **University of Pretoria** and contributes toward inclusive NLP for African languages. The BRIGHTER dataset is used under **CC-BY 4.0**, and the base model is `Davlan/afro-xlmr-small`.
