# Localized Low-resource Language AI Development: Small Data Efficiency

> An independent research into language model development for Mongolian, a low-resource language, using small data approaches and mixture of experts techniques.

---

## Overview

Low-resource languages like Mongolian face significant barriers in AI development due to:

- Limited digital environments and online native language data availability
- Structural linguistic differences that foreign models are not designed to handle
- Over-reliance on models trained predominantly on high-resource languages like English

This project builds and evaluates a **Mongolian verb classification model** that identifies verb tense (past, future, habitual, etc.) from raw sentence input using small, curated datasets.

---

## Research Goals

- Test and compare different small data approaches for low-resource NLP
- Utilize a **Mixture of Experts (MoE)** strategy to focus on verb recognition and apply it broadly
- Demonstrate measurable improvement in verb tense classification for Mongolian

---

## Methodology

### 1. Data Collection
- Gathered text from real-world Mongolian articles and literature
- Collaborated with a linguistics professor on language morphology and labeling

### 2. Data Cleaning & Preparation
- Cleaned and systematically generated structured training data
- Labeled and prepped datasets for model training

### 3. Model: Verb Classification
The model takes a Mongolian sentence as input and classifies each token and identifies the verb tense.

---

## Dataset Arrangement

Two datasets were used for training and evaluation:

| Dataset | Description | Characteristics |
|---|---|---|
| **Unstructured** | Real-life naturalistic text from articles and literature | Authentic language use, high variance, noisy |
| **Structured** | Manually constructed sentences covering tense ending variety | Controlled, consistent, low noise |

### Structured Dataset Sample

| Sentence | Label 1 | Label 2 | Label 3 |
|---|---|---|---|
| Тэр ном уншсан. | OTHER | OTHER | PAST |
| Тэд боломж ашиглана. | OTHER | OTHER | FUTURE |
| Хүмүүс хамтдаа хөгждөг. | OTHER | OTHER | HABITUAL |
| Соёл хүмүүжлийг бий болгодог. | OTHER | OTHER | OTHER | HABITUAL |

---

## Evaluation Results

Model performance was assessed using **Accuracy, Precision, and F1 Score** across **10 random seeds** to ensure robustness.

### Unstructured Dataset

| Metric | Seed 1 | Seed 2 | Seed 3 | Seed 4 | Seed 5 | Seed 6 | Seed 7 | Seed 8 | Seed 9 | Seed 10 | **Average** |
|---|---|---|---|---|---|---|---|---|---|---|---|
| Accuracy % | 0.9091 | 0.7386 | 0.8636 | 0.8409 | 0.8523 | 0.7727 | 0.8864 | 0.8636 | 0.8068 | 0.7500 | **0.8284** |
| Precision % | 0.9258 | 0.8204 | 0.8512 | 0.8601 | 0.8512 | 0.7774 | 0.8898 | 0.8872 | 0.8028 | 0.7560 | **0.8422** |
| F1 Score % | 0.9084 | 0.7487 | 0.8477 | 0.8345 | 0.8445 | 0.7694 | 0.8808 | 0.8663 | 0.7962 | 0.7299 | **0.8226** |

### Structured Dataset

| Metric | Seed 1 | Seed 2 | Seed 3 | Seed 4 | Seed 5 | Seed 6 | Seed 7 | Seed 8 | Seed 9 | Seed 10 | **Average** |
|---|---|---|---|---|---|---|---|---|---|---|---|
| Accuracy % | 0.8021 | 0.8854 | 0.9062 | 0.8958 | 0.8854 | 0.9062 | 0.9062 | 0.8854 | 0.8854 | 0.9479 | **0.8906** |
| Precision % | 0.8609 | 0.9014 | 0.9091 | 0.9058 | 0.8882 | 0.9061 | 0.9065 | 0.8995 | 0.8934 | 0.9498 | **0.9021** |
| F1 Score % | 0.8085 | 0.8862 | 0.9067 | 0.8942 | 0.8858 | 0.9060 | 0.9059 | 0.8848 | 0.8856 | 0.9483 | **0.8912** |

### Average Performance Difference (Structured vs. Unstructured)

| Metric | Avg. Difference |
|---|---|
| Accuracy | +0.0622 |
| Precision | +0.0599 |
| F1 Score | +0.0686 |

> The **structured dataset consistently outperformed** the unstructured dataset across all metrics, demonstrating that controlled, tense-focused data leads to more reliable model performance.

---

## Conclusions

- Collected, analyzed, labeled, and refined training data in collaboration with linguistics professors on Mongolian language morphology
- Dataset size and composition directly shape what a model can reliably do in practice
- Testing and feedback loops with professors and peers were critical to shaping effective model creation
- Further testing and refinement is needed for effective modeling and improved evaluation


## References

1. Natsagdorj, D. (2024). *Unseen things: Based on a true story; The rebellion of Buddhist lamas in Mongolia in 1932* (N. Bayarmaa, Trans.; D. Verburg, Ed.).
2. Stanford HAI. (2025). Mind the language gap: Mapping the challenges of LLM development in low-resource language contexts. https://hai.stanford.edu/policy/mind-the-language-gap
3. DataCamp. (2024). Mixture of experts (MoE) explained. https://www.datacamp.com/blog/mixture-of-experts-moe
4. Unread Today. (n.d.). Various articles. https://unread.today/
