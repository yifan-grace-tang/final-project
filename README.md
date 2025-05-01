# Protein Function Prediction  
> **Leveraging Sequence & Structure with Graph Neural Networks + `ProtBert`**  

[![Python](https://img.shields.io/badge/python-3.8%2B-blue)](https://www.python.org/)  [![PyTorch](https://img.shields.io/badge/pytorch-1.12%2B-red)](https://pytorch.org/)  [![Torch-Geometric](https://img.shields.io/badge/torch--geometric-2.0%2B-orange)](https://pytorch-geometric.readthedocs.io)

---
## Final Notebook submission:
 - The final notebook is in this directory, and it is titled 'Group_6_protein_function_prediction.ipynb'. We have also included most of the data we used under 'All data files' directory.

##  Overview  
Predicting protein functions—here in the form of **EC numbers**—is critical for understanding metabolic pathways and drug design. This project combines:

- **Sequence information** via [ProtBert](https://huggingface.co/Rostlab/prot_bert) embeddings  
- **Structural data** from AlphaFold‐predicted Cα graphs  
- A **Graph Convolutional Network** (GCN) fused with a sequence‐based MLP  
- A simplified task: **first‐three EC-snippet** classification, single‐label multiclass  

---

## Features  
- **ProteinDataset**:  
  - Fetches/frees caches mmCIF files  
  - Builds residue‐level graphs (8 Å cutoff)  
  - One–hot residue features + ProtBert pooled embeddings  
- **ConvClassifier**:  
  - Two GCN layers + global mean pool  
  - MLP on ProtBert embedding  
  - Fusion head → predicting three‐level EC classes  
- **Notebook**: End‐to‐end demo (`mlcb_project.ipynb`)

---

## Getting Started  

_All details are included within the attached notebook_

<details>
<summary><strong>Prerequisites</strong></summary>

- Python 3.8+  
- CUDA 11.3+ (optional, for GPU)  
- Install via `pip`:
  ```bash
  pip install torch torch-geometric transformers biopython scipy scikit-learn
  ```
