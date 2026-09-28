### Reproducing Rank-One Model Editing (ROME) and investigating its applicability to modern language models

## Overview

This project is a research-oriented replication and extension of **ROME**, a method for editing factual knowledge stored in pretrained language models. 

The research workflow is divided into three major stages:
1. **Reproduce**
   - Study the original ROME paper and implementation.
   - Reconstruct the required software environment.
   - Reproduce the causal tracing experiments.
   - Verify the original model-editing results.
2. **Understand & Analyze**
   - Investigate how causal tracing identifies important components of a transformer.
   - Understand how ROME performs a rank-one parameter update.
   - Analyze the effects of editing on the target knowledge, generalization, and specificity.
3. **Extend**
   - Adapt the methodology to a modern language model.
   - Evaluate whether the original observations and editing
     behavior remain consistent.
   - Investigate limitations and possible improvements.
  
The project is being developed as an open research log, with experimental results, implementation notes, debugging observations, and weekly progress documented throughout the process.

## Motivation

Large language models store substantial amounts of factual knowledge in their parameters. An important research question is
whether specific pieces of knowledge can be modified without mretraining the entire model.

ROME provides an influential approach to this problem by treating knowledge editing as a targeted modification of model parameters.

## Current Status

### Environment Preparation — In Progress

- [x] Original ROME repository studied
- [x] ROME repository cloned
- [x] Google Colab T4 environment prepared
- [x] Miniconda installed
- [x] Python 3.9.7 environment created
- [x] PyTorch 1.10.2 installed
- [x] CUDA 11.3 environment verified
- [x] Tesla T4 detected by PyTorch
- [x] MKL/OpenMP compatibility issue investigated
- [x] NumPy 1.22.1 installed
- [x] SciPy 1.7.3 installed
- [x] Key historical dependencies being checked
