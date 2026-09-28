# ROME Environment Setup and Reproduction Log

This document records the environment preparation and compatibility checks performed while reproducing the original ROME implementation.

The objective is to first reproduce the original software environment as closely as possible before running the causal tracing and model editing experiments.

---

## 1. Clone the Official ROME Repository

The official ROME repository was cloned into the Google Colab environment:

```bash
!git clone https://github.com/kmeng01/rome.git
```


## 2. Inspect the Initial Colab Environment
Before modifying the environment, the existing Google Colab
configuration was checked.
The purpose was to determine whether the default Colab environment
already satisfied the requirements of the original ROME implementation.
The following components were checked:
- Python version
- PyTorch version
- Transformers version
- CUDA availability
- GPU type

```bash
import sys
import torch
import transformers

print("Python:", sys.version)
print("PyTorch:", torch.__version__)
print("Transformers:", transformers.__version__)
print("CUDA available:", torch.cuda.is_available())

if torch.cuda.is_available():
    print("GPU:", torch.cuda.get_device_name(0))
```

```bash
Python: 3.13.15 (main, Aug  6 2026, 11:06:22) [GCC 13.3.0]
PyTorch: 2.11.0+cu128
Transformers: 5.16.1
CUDA available: True
GPU: Tesla T4
```
The initial environment was substantially newer than the environment specified by the original ROME repository.
Therefore, instead of modifying the default Colab Python environment, a separate Conda environment was planned for ROME.

## 3. Inspect the Original ROME Environment Configuration
Before installing dependencies, the repository's environment configuration was inspected. 
Two important files were examined:
```bash
scripts/rome.yml
scripts/setup_conda.sh
```
**rome.yml**, the files specifies the software versions expected by the original ROME implementation. 

Important core dependencies include:
```bash
Python      3.9.7
pip         21.2.4
PyTorch     1.10.2
CUDA Toolkit 11.3.1
```
This file also contains a large list of Python packages installed through pip. 

