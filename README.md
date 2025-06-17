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
├── reports/
│   ├── COS760 Presentation.pdf                          # Final presentation slides
│   ├── COS760_Group8_FinalReport_DataAugmentation.pdf   # Final project writeup or paper (optional)
│
├── README.md                         # Project overview and instructions
├── requirements.txt                  # Python dependencies
```

---

## 📘 Project Overview

Despite rapid progress in NLP, **low-resource African languages** remain severely underrepresented in emotion classification research. This project evaluates the effectiveness of **three data augmentation techniques**:
- **Random Insertion using fastText**
- **Masked Token Prediction (MLM)**
- **Round-Trip Back Translation (Helsinki-NLP & NLLB)**

All experiments are conducted using the **Davlan/afro-xlmr-small** transformer model, trained on a subset of the **BRIGHTER dataset** for Swahili, Hausa, and Afrikaans.

---

## 👥 Project Contributors

<table>
  <tr>
    <th>Name</th>
    <th>Student Number</th>
    <th>Links</th>
  </tr>
  <tr>
    <td><strong>Mignon Erasmus</strong></td>
    <td>u22492586</td>
    <td>
      <a href="https://github.com/MignonErasmus" style="text-decoration: none; margin-right: 10px;">
        <img src="https://skillicons.dev/icons?i=github" alt="GitHub"/>
      </a>
      <a href="https://www.linkedin.com/in/mignon-erasmus-57202b266" style="text-decoration: none;">
        <img src="https://skillicons.dev/icons?i=linkedin" alt="LinkedIn"/>
      </a>
    </td>
  </tr>
  <tr>
    <td><strong>Caitlin Simon</strong></td>
    <td>u22608495</td>
    <td>
      <a href="https://github.com/CaitMS" style="text-decoration: none; margin-right: 10px;">
        <img src="https://skillicons.dev/icons?i=github" alt="GitHub"/>
      </a>
      <a href="http://www.linkedin.com/in/caitlin-simon-4a8757230" style="text-decoration: none;">
        <img src="https://skillicons.dev/icons?i=linkedin" alt="LinkedIn"/>
      </a>
    </td>
  </tr>
  <tr>
    <td><strong>Xadrian van Heerdan</strong></td>
    <td>u22699572</td>
    <td>
      <a href="[https://github.com/xadrianvh](https://github.com/XadrianvHeerden)" style="text-decoration: none; margin-right: 10px;">
        <img src="https://skillicons.dev/icons?i=github" alt="GitHub"/>
      </a>
      <a href="https://www.linkedin.com/in/xadrian-van-heerden-05635123b/" style="text-decoration: none;">
        <img src="https://skillicons.dev/icons?i=linkedin" alt="LinkedIn"/>
      </a>
    </td>
  </tr>
</table>

---

## 🛠️ Requirements
If you do not run this project on Google Colabs, the following is required for your python environment.
To set up the environment, ensure you have Python 3.8–3.10 installed, then install the required packages:

```bash
pip install -r requirements.txt
```

In addition, your system must support the following CLI tools for downloading and extracting fastText vectors:

- `wget`
- `unzip`

These can be installed via your package manager (e.g., `apt`, `brew`, or `choco` depending on OS).

> 💡 Pre-trained word vectors for Swahili, Hausa, and Afrikaans are downloaded directly from [fastText](https://fasttext.cc/docs/en/pretrained-vectors.html).

---

## 🚀 How to Run

You can execute each experiment by opening the corresponding notebook under `/notebooks`,and run it using [Google Colab](https://colab.google/):

| Task                              | Notebook Name                 |
|----------------------------------|-------------------------------|
| Baseline training                | `1_basemodel.ipynb`           |
| Random Insertion Augmentation    | `2_random_insertion.ipynb`    |
| Masked Language Model Augmentation | `3_masking.ipynb`            |
| Back Translation Augmentation    | `4_back_translation.ipynb`    |


---

## 🎥 Presentation & Slides

- 📽️ [Watch our project video](https://drive.google.com/file/d/1yj14bI5OBzuBR2CyhExOL2UMzjpDok8R/view?usp=drive_link)  
- 📑 [View our final slides](https://example.com/slides)

---

## 📈 Results Summary

### 📊 Table 1: Baseline Results

| Language  | Micro F1-Score | Macro F1-Score | Hamming Loss | Subset Accuracy |
|-----------|----------------|----------------|---------------|------------------|
| Afrikaans | 0.7609         | 0.6169         | 0.0816        | 0.6901           |
| Hausa     | 0.7690         | 0.7624         | 0.0865        | 0.6175           |
| Swahili   | 0.4353         | 0.0879         | 0.1647        | 0.4443           |


### 📊 Table 2: Random Insertion Results

| Language  | Micro F1 Score (Δ) | Macro F1 Score (Δ) | Hamming Loss (Δ) | Subset Accuracy (Δ) |
|-----------|--------------------|---------------------|-------------------|----------------------|
| Afrikaans | 0.7937 (+0.03)     | 0.6655 (+0.05)      | 0.0684 (–0.013)   | 0.7380 (+0.05)       |
| Hausa     | 0.7779 (+0.01)     | 0.7689 (+0.01)      | 0.0833 (–0.003)   | 0.6494 (+0.03)       |
| Swahili   | 0.6883 (+0.25)     | 0.6360 (+0.55)      | 0.0959 (–0.069)   | 0.6477 (+0.20)       |


### 📊 Table 3: Masking Results

| Language  | Micro F1 Score (Δ) | Macro F1 Score (Δ) | Hamming Loss (Δ) | Subset Accuracy (Δ) |
|-----------|--------------------|---------------------|-------------------|----------------------|
| Afrikaans | 0.8273 (+0.07)     | 0.6821 (+0.07)      | 0.0571 (–0.025)   | 0.7775 (+0.09)       |
| Hausa     | 0.7496 (–0.01)     | 0.7434 (–0.02)      | 0.0939 (+0.007)   | 0.6076 (–0.01)       |
| Swahili   | 0.6221 (+0.19)     | 0.4878 (+0.40)      | 0.1201 (–0.045)   | 0.5330 (+0.09)       |


### 📊 Table 4: Back Translation Results

| Language  | Micro F1 Score (Δ) | Macro F1 Score (Δ) | Hamming Loss (Δ) | Subset Accuracy (Δ) |
|-----------|--------------------|---------------------|-------------------|----------------------|
| Afrikaans | 0.7912 (+0.03)     | 0.6667 (+0.05)      | 0.0688 (–0.013)   | 0.7408 (+0.05)       |
| Hausa     | 0.7566 (–0.01)     | 0.7513 (–0.01)      | 0.0913 (+0.005)   | 0.5996 (–0.02)       |
| Swahili   | 0.6726 (+0.23)     | 0.6006 (+0.51)      | 0.1027 (–0.062)   | 0.6049 (+0.16)       |

---

## 🤝 Acknowledgements


This project was developed as part of a research initiative at the **University of Pretoria** and contributes toward inclusive NLP for African languages.

We gratefully acknowledge the following resources:

- The **[BRIGHTER dataset](https://arxiv.org/abs/2502.11926)** for providing emotion-annotated multilingual data.
- The [**`Davlan/afro-xlmr-small`**](https://huggingface.co/Davlan/afro-xlmr-small) model for multilingual transformer support on African languages.
- **[Helsinki-NLP’s Opus-MT](https://huggingface.co/Helsinki-NLP)** models for back translation for Afrikaans and Hausa.
- **[Meta’s NLLB-200](https://huggingface.co/facebook/nllb-200-distilled-600M)** for high-quality translation support for Swahili.
- **[LaBSE (Language-Agnostic BERT Sentence Embedding)](https://huggingface.co/sentence-transformers/LaBSE)** model for measuring semantic similarity across multilingual sentences.
- **[fastText word embeddings](https://fasttext.cc/docs/en/pretrained-vectors.html)** by Grave et al. (2018) for providing pre-trained word vectors used in our Random Insertion and semantic similarity filtering steps.
Citation: Grave, E., Bojanowski, P., Gupta, P., Joulin, A., & Mikolov, T. (2018). Learning Word Vectors for 157 Languages. arXiv:1802.06893 [The Paper](https://arxiv.org/pdf/1802.06893)

The BRIGHTER dataset is used under **CC-BY 4.0**, and the models listed above are used under their respective licenses provided by the HuggingFace Model Hub.
