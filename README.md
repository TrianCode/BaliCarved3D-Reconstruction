# BaliCarved3D-Reconstruction

# Disentangling Shape and Ornament: A Coarse-to-Fine Framework for Single-Image 3D Reconstruction of Balinese Carvings

[![License: CC BY-NC 4.0](https://img.shields.io/badge/License-CC%20BY--NC%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc/4.0/)
[![PyTorch](https://img.shields.io/badge/PyTorch-2.1-EE4C2C.svg)](https://pytorch.org/)

Official repository for the paper **"Disentangling Shape and Ornament: A Coarse-to-Fine Framework for Single-Image 3D Reconstruction of Balinese Carvings"**. 

This repository contains the inference code, model architecture, and evaluation scripts for our hybrid reconstruction framework, which combines a Transformer-based global spatial prior (TripoSR) with a probabilistic Signed Distance Function (SDF) Diffusion refinement. This approach explicitly resolves the "Thin Object Paradox" in reconstructing non-convex and highly perforated architectural elements (e.g., Balinese *krawangan*).

## 🗂️ Repository Structure

* `models/`: Core architecture scripts (`triposr_prior.py`, `sdf_diffusion.py`).
* `scripts/`: Evaluation scripts to compute CD, IoU, UHD, and TMD metrics.
* `inference.py`: Main script for single-image to 3D mesh reconstruction.
* `requirements.txt`: List of dependencies.

## 💾 Data Availability (BaliCarved3D)

Due to file size limits, the **BaliCarved3D dataset** (consisting of 52 classes of architectural carvings) and the **pre-trained model weights** are hosted externally. 

* **Dataset & Pre-trained Weights:** [Insert Link to Figshare/Zenodo/Drive Here]
* Please download the files from the link above and extract the dataset into the `data/` directory before running the evaluation scripts.

## ⚙️ Installation

The framework is built using PyTorch 2.1 and CUDA 12.1. To set up the environment, run:

```bash
git clone [https://github.com/YOUR_USERNAME/BaliCarved3D.git](https://github.com/YOUR_USERNAME/BaliCarved3D.git)
cd BaliCarved3D
pip install -r requirements.txt

python inference.py --image test_images/sample_saka.png --output_dir ./output --use_refinement True
