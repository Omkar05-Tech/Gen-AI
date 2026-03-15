# 🎬 Robust AI Video Generator: Text-to-Image-to-Video Pipeline

This repository demonstrates a production-grade generative AI pipeline for creating video animations from text prompts. It utilizes a two-step architecture—cloud-based image generation coupled with local video inference—to overcome the common limitations of free public AI APIs.

## 📌 Architecture & Engineering Decisions
Generating video directly from text via public APIs often results in server crashes (HTTP 422/503), long queue times, or strict paywalls. To ensure a 100% reliable execution environment for this project, the pipeline was decoupled:

1. **Step 1: Text-to-Image (Cloud API with Fallback Loop):** The application uses the Hugging Face `InferenceClient` to generate a high-quality base frame. It implements a robust fallback mechanism that prioritizes state-of-the-art models (like FLUX.1) but gracefully degrades to high-availability models if primary servers are overloaded.
2. **Step 2: Image-to-Video (Local GPU Inference):** Once the base frame is secured, the application downloads the `I2VGen-XL` diffusion model and runs the heavy video rendering locally on the allocated GPU (e.g., Google Colab T4). This eliminates dependency on flaky third-party video servers and avoids "Insufficient Credit" errors.

## 🛠️ Technology Stack
* **Language:** Python 3
* **Environment:** Google Colab (Requires T4 GPU)
* **API Client:** `huggingface_hub`
* **Local Inference:** Hugging Face `diffusers`, `transformers`, `accelerate`
* **Models Used:** * *Image:* FLUX.1-schnell / Stable Diffusion XL (via API)
  * *Video:* `ali-vilab/i2vgen-xl` (via Local Inference)

## 🚀 How to Run

### Prerequisites
1. Open the Jupyter Notebook in an environment with a GPU (e.g., Google Colab with T4 enabled).
2. Obtain a free access token from [Hugging Face](https://huggingface.co/settings/tokens).
3. Add your token to the Colab Secrets manager as `HF_TOKEN`.

### Execution
* **Run Cell 1 (Image Generation):** This script securely connects to the Hugging Face API router. It will test the availability of several top-tier image models, generate the initial scene based on your text prompt, and save it locally as `base_frame.png`.
* **Run Cell 2 (Video Generation):** This script downloads the `I2VGen-XL` pipeline directly into your environment's VRAM (using CPU offloading to prevent Out-Of-Memory errors). It reads `base_frame.png`, applies your motion prompt, and outputs the final `true_ai_animation.mp4`.

## 🧠 Key Learnings
* **API Resiliency:** Implementing `try/except` fallback loops for third-party endpoints is critical for maintaining application uptime.
* **VRAM Management:** Using `pipeline.enable_model_cpu_offload()` allows massive, multi-gigabyte diffusion models to run on standard consumer-grade GPUs by dynamically shifting weights between RAM and VRAM.

---
*Developed as a practical exploration of multimodal generative AI and robust systems engineering.*









# 🎬 AI Video Animation Generator

This repository contains a Google Colab implementation of a Text-to-Video generation pipeline. It allows users to generate simple video animations from pure text descriptions using open-source diffusion models.

## 📌 Overview
Generative AI is rapidly expanding beyond text and images into full video generation. This project demonstrates how to use Latent Diffusion Models (LDMs) to synthesize temporal video frames from a textual prompt. The model processes the text, generates a sequence of coherent image frames, and compiles them into a playable `.mp4` video format.

## 🛠️ Technology Stack
* **Language:** Python 3
* **Environment:** Google Colab (Requires T4 GPU)
* **Libraries:** Hugging Face `diffusers`, `transformers`, `accelerate`, `imageio`
* **Model:** `damo-vilab/text-to-video-ms-1.7b` (A 1.7 billion parameter text-to-video diffusion model).

## 🚀 How to Run

1. Open the Jupyter Notebook (`AI_Video_Generator.ipynb`) in Google Colab.
2. Ensure your hardware accelerator is set to **T4 GPU** (`Runtime` > `Change runtime type`).
3. Run **Cell 1** to install the required diffusion and video-processing libraries.
4. Run **Cell 2** to download the model weights and load them into VRAM with CPU offloading enabled to prevent Out-Of-Memory (OOM) errors.
5. Run **Cell 3** to generate the video. You can change the `prompt` variable to anything you want to animate (e.g., *"A dog wearing sunglasses surfing on a wave"*).
6. The generated `.mp4` video will automatically render and play inside the notebook.

## ⚙️ How it Works
1. **Text Encoding:** The prompt is converted into embeddings.
2. **Denoising Loop:** The diffusion model starts with pure visual noise and iteratively refines it across multiple frames simultaneously, ensuring visual consistency from frame to frame.
3. **Export:** The `export_to_video` utility stitches the resulting tensor arrays into a standard 8-fps MP4 file.

---
*Developed as a practical exploration of multimodal generative AI and open-source diffusion pipelines.*