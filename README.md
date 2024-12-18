# What Drives Performance in Multilingual Language Models?

This repository contains the code and resources for the paper:

**[What Drives Performance in Multilingual Language Models?](https://arxiv.org/abs/2404.19159)**  
*Sina Bagheri Nezhad, Ameeta Agrawal*  
Presented in the **Eleventh Workshop on NLP for Similar Languages, Varieties, and Dialects (VarDial 2024)**  
*NAACL 2024, Mexico City, Mexico.*  

**Link to the paper**: [ACL Anthology](https://aclanthology.org/2024.vardial-1.2) | [arXiv](https://arxiv.org/abs/2404.19159)

---

## Overview

Multilingual large language models (MLLMs) are critical for enabling natural language processing across diverse languages. However, understanding **what factors influence their performance** remains an open challenge. This paper investigates the key drivers of performance across **6 MLLMs** (masked, autoregressive, and instruction-tuned models) on the **SIB-200** dataset, which spans **204 languages**.

### Key Focus:
- **SEEN languages**: Present in the model's pretraining data.
- **UNSEEN languages**: Absent from the pretraining data.
- **ALL languages**: Full evaluation set.

We analyze the impact of:
- **Pretraining Data Size**
- **Resource Availability**
- **Language Family**
- **Script Type**

Our experiments reveal **pretraining data** as the most influential factor for SEEN languages, while **script type** and **language family** play a pivotal role for UNSEEN languages. 

---

## Key Contributions

1. **Comprehensive Analysis**: Examined **6 MLLMs** under multiple scenarios (SEEN, UNSEEN, ALL) for text classification.
2. **Feature Importance**: Identified pretraining data size, resource availability, script type, and language family as significant factors using **decision tree analysis**.
3. **Insights for UNSEEN Languages**: Highlighted the importance of cross-lingual transfer learning via script and linguistic features.
4. **Evaluation with SIB-200**: Utilized a benchmark dataset encompassing 204 languages, ensuring diversity and coverage.

---

## Datasets

### SIB-200 Dataset
- **Description**: A topic classification dataset for **204 languages**.
- **Categories**: Text samples categorized into 7 classes (e.g., science, politics, sports).
- **Resource Levels**: Emphasizes low-resource languages.
- **Scripts**: Includes 29 script types with a focus on diversity.
- **Source**: [SIB-200 Dataset](https://github.com/dadelani/sib-200).

---

## Models Evaluated

We study **6 multilingual models** across different architectures and sizes:

- **Masked Language Models (MLMs)**:
  - mBERT (Devlin et al., 2019)
  - XLM-R (Conneau et al., 2020)
- **Autoregressive Models**:
  - GPT-3.5 (Brown et al., 2020)
  - BLOOM (Scao et al., 2022) in 5 sizes (560M to 7.1B parameters).
  - XGLM (Lin et al., 2022) in 4 sizes (564M to 7.5B parameters).
- **Instruction-tuned Models**:
  - BloomZ (Muennighoff et al., 2023) in 5 sizes (560M to 7.1B parameters).

### Scenarios:
- **Zero-shot**: Models evaluated without any fine-tuning.
- **Two-shot ICL**: Models evaluated with 2 labeled examples per class.
- **Full-shot**: Fine-tuned models (mBERT, XLM-R) on SIB-200 training set.

---

## Methodology

1. **Feature Analysis**: Analyzed the impact of:
   - Pretraining Data Size
   - Resource Availability (low to high-resource levels)
   - Language Family (e.g., Indo-European, Niger-Congo)
   - Script Type (e.g., Latin, Devanagari, Cyrillic)
2. **Decision Tree Analysis**: Used decision trees to identify significant features affecting performance across SEEN and UNSEEN languages.
3. **Validation**: Applied the Mann-Whitney U test to confirm the significance of identified features.

---

## Results

### Key Findings:
1. **SEEN Languages**:
   - **Pretraining Data Size** is the dominant factor.
   - Resource availability also influences performance.
2. **UNSEEN Languages**:
   - **Script Type** and **Language Family** emerge as the most critical features.
   - Cross-lingual transfer learning plays a pivotal role.
3. **Model Size**: Larger models show overall better performance, but size does not alter the most important features.

---

## Citation

If you use this work, please cite:

```bibtex
@inproceedings{bagheri-nezhad-agrawal-2024-drives,
    title = "What Drives Performance in Multilingual Language Models?",
    author = "Bagheri Nezhad, Sina  and
      Agrawal, Ameeta",
    editor = {Scherrer, Yves  and
      Jauhiainen, Tommi  and
      Ljube{\v{s}}i{\'c}, Nikola  and
      Zampieri, Marcos  and
      Nakov, Preslav  and
      Tiedemann, J{\"o}rg},
    booktitle = "Proceedings of the Eleventh Workshop on NLP for Similar Languages, Varieties, and Dialects (VarDial 2024)",
    month = jun,
    year = "2024",
    address = "Mexico City, Mexico",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/2024.vardial-1.2",
    doi = "10.18653/v1/2024.vardial-1.2",
    pages = "16--27",
}
```
## Authors
- **[Sina Bagheri Nezhad](https://sinaai.github.io/)**
- **[Ameeta Agrawal](https://web.cecs.pdx.edu/~ameeta/)**

---

## Acknowledgments
This work was supported by the National Science Foundation under Grants CRII:RI 2246174 and SAI-P 2228783.
