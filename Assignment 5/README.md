# 🎨 Creative Artwork Generator using Stable Diffusion XL

This repository contains a local implementation of **Stable Diffusion XL (SDXL)** for generating high-resolution, highly creative digital artwork from text prompts.

## 📌 Overview
Unlike basic API wrappers, this project demonstrates how to run state-of-the-art Latent Diffusion Models locally on GPU hardware. It utilizes the Hugging Face `diffusers` library to orchestrate the denoising process, transforming random Gaussian noise into coherent, highly detailed images based on text embeddings.

## 🛠️ Technology Stack
* **Language:** Python 3
* **Environment:** Google Colab (T4 GPU)
* **Libraries:** `diffusers`, `transformers`, `accelerate`, `torch`
* **Model:** `stabilityai/stable-diffusion-xl-base-1.0`

## 🚀 How to Run

1. Open the Jupyter Notebook (`Stable_Diffusion_Art.ipynb`) in an environment with at least 15GB of GPU VRAM (e.g., Google Colab T4).
2. Run **Cell 1** to install the required deep learning libraries.
3. Run **Cell 2** to download the SDXL weights and load the pipeline. CPU offloading is enabled by default to prevent Out-Of-Memory (OOM) errors.
4. Run **Cell 3** to generate the artwork. 

## 🧠 Advanced Features Implemented
* **Negative Prompting:** Explicitly steers the model away from undesirable traits (e.g., "blurry", "watermark", "distorted") by pushing the latent vectors away from those concepts during the generation loop.
* **Guidance Scale (Classifier-Free Guidance):** Adjusted to 7.5 to strike the optimal balance between prompt adherence and raw model creativity.
* **Precision Tuning:** Operates in `fp16` (half-precision floating point) to halve memory consumption while maintaining visual fidelity.

---
*Developed as a practical exploration of Generative AI, Latent Diffusion, and VRAM management.*