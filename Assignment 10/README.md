# 🎨 AI Text-to-Image Generator
This repository contains a Google Colab implementation of a Text-to-Image generation pipeline. It allows users to generate high-quality images from pure text descriptions using open-source diffusion models.

## 📌 Overview
Generative AI is rapidly expanding, allowing for the creation of stunning visuals from simple language. This project demonstrates how to use Latent Diffusion Models (LDMs) to synthesize high-resolution images from a textual prompt. The model processes the text, generates a coherent image, and saves it in a standard .png format.

## 🛠️ Technology Stack
Language: Python 3

Environment: Google Colab (Requires T4 GPU)

Libraries: Hugging Face diffusers, transformers, accelerate, torch, safetensors

Model: runwayml/stable-diffusion-v1-5 (A latent text-to-image diffusion model).

## 🚀 How to Run
Open the Jupyter Notebook (Text-to-Image.ipynb) in Google Colab.

Ensure your hardware accelerator is set to T4 GPU (Runtime > Change runtime type).

Run Cell 1 to install the required diffusion and tensor-processing libraries.

Run Cell 2 to download the model weights and load them into the GPU (.to("cuda")).

Run Cell 3 (or the advanced cell) to generate the image. You can change the prompt variable to anything you want to visualize (e.g., "A futuristic smart city with flying cars, ultra realistic, 4K, cinematic lighting").

The generated .png image will automatically be saved and displayed inside the notebook.

## ⚙️ How it Works
Text Encoding: The prompt is converted into text embeddings using a Transformer-based text encoder.

Denoising Loop: The diffusion model starts with pure visual noise in a compressed latent space and iteratively refines it into a clear image based on the text embeddings over multiple inference steps.

Export: The resulting latent representation is decoded back into pixel space and saved as a standard PNG file.

Developed as a practical exploration of multimodal generative AI and open-source diffusion pipelines.