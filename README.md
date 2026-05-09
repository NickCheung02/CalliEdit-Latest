# CalliEdit: Dual-Stream Flow Matching with Feature Osmosis for Topologically-Preserved Image-Text Generation and Editing

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT) [![Paper Status](https://img.shields.io/badge/Paper-Under_Review-orange.svg)]() [![Framework: PyTorch](https://img.shields.io/badge/Framework-PyTorch-ee4c2c.svg)](https://pytorch.org/)

## 📖 Introduction

**CalliEdit** proposes a novel Dual-Stream Flow Matching architecture, integrated with a Feature Osmosis mechanism and differentiable sequence-level reward feedback based on CTC topology correction. The proposed method enables high-fidelity text rendering under extreme artistic deformations and seamless image-text editing in complex backgrounds. It achieves strict orthogonal disentanglement among global layout, topological skeleton, and calligraphic style, while providing a highly robust unified paradigm for topology-preserving generation in open-domain scenarios.

## 📢 Open Source Status

⚠️ **Important Notice: The paper of this project is currently under review.**

To comply with academic submission policies, all specific quantitative comparison results, such as accuracy, FID, and other evaluation metrics, have been hidden in this document.

* 🔓 **Inference and training code**: The code has been fully open-sourced. You can reproduce our model architecture and data pipeline through this repository.
* 🔒 **Pre-trained model weights**: Pre-trained weights such as Calliscape-S, together with part of the datasets, will be released immediately after the paper is officially accepted.

## 🌟 Qualitative Results

> Note: The following images demonstrate the qualitative generation and editing results of CalliEdit across various complex scenarios.

### 1. Comparative Experiments

We compare CalliEdit with current state-of-the-art visual text generation models, such as AnyText, under diverse artistic styles, complex layouts, and scene editing tasks.

![Comparative Results](assets/Comparison_with_SOTA.png)

*Figure 1: CalliEdit significantly outperforms existing methods in preserving calligraphic artistic style and achieving background consistency.*

### 2. Ablation Studies

Ablation studies are conducted to verify the contributions of the proposed mechanisms to background consistency and the completeness of text topological structures.

![Ablation Study Results](./assets/AblationStudy.png)

*Figure 2: Generated results before and after ablation, demonstrating the effectiveness of the proposed components.*

### 3. Feature Map Evolution Analysis

To further investigate the internal mechanism of the model, we visualize the evolution of feature maps in the denoising trajectory of the dual-stream architecture. This analysis reveals how textual features are progressively integrated into the background domain through the Feature Osmosis mechanism.

![Feature Map Evolution](./assets/shanshui_newv_101_evolution.png)

*Figure 3: Responses of the Feature Osmosis layers at different timesteps, illustrating the progressive disentanglement and reconstruction of layout and fine-grained details.*

## ⚙️ Installation

This project is built upon core libraries such as PyTorch and Diffusers. We recommend using Conda to configure the virtual environment.

```bash
# 1. Create and activate the Conda environment
conda create -n calliedit python=3.10 -y
conda activate calliedit

# 2. Install PyTorch
# The following example uses CUDA 11.7. Please ensure consistency with requirements.txt.
pip install torch==2.0.0+cu117 torchvision==0.15.0 -f https://download.pytorch.org/whl/cu117/torch_stable.html

# 3. Install the remaining dependencies
pip install -r requirements.txt
