# Ethereum Phishing Scam Detection

## Overview

This repository contains work done as part of a research project at **IIT Patna** aimed at detecting phishing scams on the Ethereum blockchain using graph-based machine learning. The work was shared between co-interns; this repo includes those parts contributed by me.

---

## Dataset

- We used the **Ethereum Phishing Scams Dataset (Eth-PSD)** — a verified dataset of Ethereum blockchain records, containing officially reported phishing scam addresses and benign addresses. :contentReference[oaicite:0]{index=0}  
- Alternatively, another dataset explored is the *Ethereum Phishing Transaction Network*. :contentReference[oaicite:1]{index=1}  
- *Note:* Exact subset / split used, and any modifications, are described in this repo.

---

## Methodology

1. **Preprocessing**  
   - Data cleaning: removing invalid, missing, or corrupt entries; normalization of transaction values and timestamps.  
   - Data augmentation using **SMOTE** to balance the classes, since phishing cases are much fewer than benign ones.  
   - Transforming raw data into features / attributes per user node in a graph. This involved computing structural, transaction-based, and behavioral attributes (e.g. degree measures, temporal transaction counts, amounts sent/received, etc.).

2. **Graph Model**  
   - Built a Graph Convolutional Network (GCN) over the user-interaction graph (nodes = users, edges = transactions).  
   - Fed in the computed node-attributes as features to the GCN.

---

## Results

- Achieved **~98% accuracy** on detecting phishing samples on the test set.  
- Experiments show strong performance in separating phishing vs benign accounts, based on the chosen node features + graph structure.

---

## Limitations and Notes

- The computation of attributes was **computationally expensive**, especially for large transaction history, temporal aggregation, and graph construction.  
- Because the work was split between interns, **some code pieces (particularly for attribute computation)** are **not available** in this repo. Only the parts I contributed (model training, evaluation, etc.) are present.

---
