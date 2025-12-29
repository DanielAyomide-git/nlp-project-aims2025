# Multilingual Online Polarization Detection (English & Swahili)

This repository contains the **code, experiments, and evaluation pipeline** for the paper:

> **A Comprehensive Computational Approach for Detecting Multilingual, Multicultural, and Multievent Online Polarization in English and Swahili**  
> **Daniel Ayomide Olanrewaju**  
> African Institute for Mathematical Sciences (AIMS), South Africa  
> 📧 dolan@aims.ac.za  

---

## 📌 Abstract

Online polarization poses a critical threat to global social cohesion; however, existing computational detection methods remain largely English-centric and insufficiently grounded in diverse cultural contexts.  
This work presents a comprehensive evaluation of transformer-based architectures for detecting **Multilingual, Multicultural, and Multievent (3M) polarization** in **English and Swahili**.

We compare:

- **Language- and domain-specific models** (e.g., Twitter-RoBERTa, SwahBERT)
- **General-purpose multilingual baselines** (e.g., XLM-RoBERTa, DeBERTa)

Experimental results demonstrate that **native-language pre-training consistently outperforms cross-lingual transfer and translation-based approaches**, highlighting the importance of language- and culture-aware modeling for robust polarization detection—especially in low-resource settings.

---

## 🧠 Tasks Overview

The study evaluates three polarization detection subtasks:

| Subtask | Description |
|-------|-------------|
| Subtask 1 | Binary detection of polarization presence |
| Subtask 2 | Multi-label classification of polarization targets |
| Subtask 3 | Multi-label classification of polarization manifestation / rhetoric |

Performance is reported using **macro-F1**, averaged across cross-validation folds.

---

## ⚙️ Models Evaluated

### Language-Specific Models
- **Twitter-RoBERTa (English)**
- **SwahBERT (Swahili)**

### Multilingual Models
- **XLM-RoBERTa**
- **DeBERTa (multilingual variants)**

---

## 📊 Key Experimental Findings

### 1. Overall Performance
- Subtask 1 (binary polarization detection) achieves the **highest macro-F1** across both languages.
- Fine-grained subtasks (Subtasks 2 & 3) show **significant performance degradation**, especially in Swahili.

### 2. Language-Specific Advantage
- **SwahBERT outperforms all multilingual models** across Swahili subtasks.
- English Twitter-adapted models consistently outperform generic multilingual baselines.

### 3. Cross-Lingual Limitations
- Increased model scale or multilingual pre-training **does not eliminate performance gaps**.
- Code-mixed and culturally grounded expressions remain challenging for shared representations.

### 4. Ensemble Robustness
- A **weighted ensemble strategy** reduces fold-level variance and improves prediction stability.
- Particularly effective in **low-resource Swahili settings**.

---

## 🧪 Training Configuration

- Transformer fine-tuning with early stopping  
- 3–4 epochs sufficient for convergence  
- Cross-validation for reliable evaluation  
- Macro-F1 as the primary metric  
- Weighted ensembling based on validation performance  

---

## 📈 Qualitative Analysis

- English polarization often relies on **explicit antagonistic language**
- Swahili discourse exhibits **greater lexical diversity and contextual specificity**
- Cultural grounding partially explains the reduced effectiveness of cross-lingual abstractions
