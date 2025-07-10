# Enhancing Cross-Lingual Transfer using Manifold Mixup 🧠🌍

## 📝 Overview
This project explores the use of **Manifold Mixup (X-Mixup)** to enhance cross-lingual transfer in Natural Language Processing (NLP). Traditional models often struggle when trained in one language and tested in another, especially in **low-resource scenarios**. By applying X-Mixup, we aim to help models generalize better by **mixing internal representations** (not just raw inputs), allowing more effective knowledge transfer across languages.

> ✨ This work was conducted as part of an NLP internship under the guidance of Dr. Karthick Seshadri sir and Dr. Sastry sir at **NIT Andhra Pradesh**.

---

## 🔍 Problem Statement
- Multilingual models like mBERT can struggle to perform consistently across languages due to data scarcity or domain differences.
- How can we improve performance in low-resource or unseen languages using **representation-level regularization**?

---

## 💡 Why Manifold Mixup?
- **Traditional Mixup** mixes inputs or labels.
- **Manifold Mixup (X-Mixup)** interpolates within hidden layers of the model — like mixing internal thoughts 🧠.
- Encourages the model to learn **smoother decision boundaries** and **generalize better** across tasks and languages.

---

## ⚙️ Methodology
- **Model Used**: Multilingual DistilBERT (or similar)
- **Task**: Cross-lingual classification (trained in English, tested on other languages like Hindi/Telugu)
- **Technique**: Apply manifold mixup at intermediate layers during fine-tuning
- **Evaluation**: Accuracy, F1-Score across languages (with vs. without mixup)

---

Implementation of ICLR 2022 paper "[Enhancing Cross-lingual Transfer by Manifold Mixup](https://openreview.net/pdf?id=OjPmfr9GkVv)".

This project was made by taking above research paper as reference under the faculty guidance of Dept of CSE, NIT AndhraPradesh as a part of Summer Research Internship.


## Structure
```text
.
├── data                              # XTREME data and translation data
│   ├── xnli
│      ├── XNLI-MT-1.0
│      ├── XNLI-1.0          
│      ├── translate-test
│      ├── translate-dev
│      ├── translate-train-en  # back-translation data  
├── scripts
├── xmixup
├── README.md
└── requirements.txt
```

## Environment
```bash
pip install -r requirements.txt
```

## Data
Prepare data before the training phrase: 
* Step 1: Download XTREME data from [XTREME repo](https://github.com/google-research/xtreme) (Note that we should keep the label of test set for evaluation).
* Step 2: Download other translation data from [here](https://drive.google.com/drive/folders/1UysSbPfkMBzQb6m2x7aO2WyWQehW38F3?usp=sharing).
* Step 3: Organize data following the Structure part.

## Training & Evaluation
```bash
bash ./scripts/train.sh [pretrained_model] [task_name] [data_dir] [output_dir]
```
where the options are described as follows:
- `[pretrained_model]`: `xlmr` or `mbert`
- `[task_name]`: `xnli`
- `[data_dir]`: data directory
- `[output_dir]`: output directory

## 🌐 Real-World Applications
- **Multilingual chatbots**
- **AI-powered translators** (e.g., English to regional languages)
- **Voice assistants in code-mixed speech**
- **News or social media analysis in low-resource languages**

---

## 🤝 Acknowledgements
- Guided by **Dr. Karthick Seshadri** and **Dr. Sastry**, Department of CSE, NIT Andhra Pradesh.
- Inspired by research in **representation learning**, **transfer learning**, and **low-resource NLP**.

---
## ⭐ If you found this helpful, don't forget to star the repo!
