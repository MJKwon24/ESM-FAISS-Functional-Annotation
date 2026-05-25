# ESM2-FAISS Protein Annotation

ESM2-FAISS Protein Annotation is a protein functional annotation pipeline based on **ESM-2 protein embeddings** and **FAISS nearest-neighbor search**.

This pipeline embeds query protein sequences using ESM-2 and compares them against a precomputed reference protein embedding database. The nearest reference proteins are retrieved using FAISS, and functional annotation candidates are reported based on cosine similarity.

---

## Overview

Functional annotation of protein-coding genes is a critical step in microbial genome analysis. However, conventional sequence similarity-based annotation tools may leave many proteins as hypothetical proteins, especially when close homologs are absent from reference databases.

This pipeline provides an embedding-based annotation approach using:

- **ESM-2** for protein sequence embedding
- **FAISS** for efficient nearest-neighbor search
- **Cosine similarity** for comparing query and reference protein embeddings
- A precomputed reference embedding database with corresponding metadata

---

## Workflow

```text
Query protein FASTA
        |
        v
ESM-2 embedding
        |
        v
L2 normalization
        |
        v
FAISS nearest-neighbor search
        |
        v
Top-k reference protein hits
        |
        v
Predicted functional annotation
