# Basic Multimodal Image Captioning using CLIP

This repository contains a basic multimodal system for image captioning using OpenAI's **CLIP** (Contrastive Language-Image Pretraining) model. 

## 📝 How it Works
Unlike autoregressive vision-language models (like BLIP or LLaVA) that generate sentences word-by-word, CLIP uses **Zero-Shot Image Classification** to perform captioning. It evaluates a given image against a list of predefined text descriptions and calculates a similarity score to find the best match.

## 🛠️ Prerequisites

Ensure you have Python 3.8+ installed. You will need to install PyTorch and the CLIP library.

### Installation

1. Install PyTorch (Modify the command based on your OS and compute platform at [pytorch.org](https://pytorch.org/get-started/locally/)):
   ```bash
   pip install torch torchvision