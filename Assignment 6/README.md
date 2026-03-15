# 🖼️ Text-to-Image Generation Pipeline via REST API

This repository demonstrates the integration of a cloud-hosted, state-of-the-art generative AI model into a Python application using a standard REST API pipeline.

## 📌 Overview
While deploying models locally offers maximum control, modern AI applications often rely on cloud infrastructure via API endpoints for scalability. This project showcases an API-first pipeline that takes a text prompt, interfaces securely with Hugging Face's Serverless Inference API, handles the asynchronous HTTP response, and processes the returned byte data natively within the application.

*Note: This pipeline uses FLUX.1-schnell, a state-of-the-art open-source model, serving as a highly capable, cost-effective alternative to proprietary paid APIs like OpenAI's DALL-E 3.*

## 🛠️ Technology Stack
* **Language:** Python 3
* **Environment:** Google Colab / Jupyter Notebook
* **API Provider:** Hugging Face Inference Router
* **Model:** `black-forest-labs/FLUX.1-schnell`
* **Data Handling:** `requests`, `io`, `Pillow` (PIL)

## 🚀 How to Run

1. Open the Jupyter Notebook (`API_Image_Generator.ipynb`).
2. Obtain a free Access Token from [Hugging Face](https://huggingface.co/settings/tokens).
3. Add your token to your environment variables or Colab Secrets manager as `HF_TOKEN`. 
4. Run the pipeline cell. The script will:
   * Securely authorize the request using Bearer tokens.
   * Pass the JSON payload (your prompt) to the model endpoint.
   * Retrieve the raw byte stream from the server.
   * Render the `.png` image directly in the notebook output.

## 🧠 Architectural Insights
* **API Resiliency:** This pipeline mimics the exact architecture used to interface with commercial APIs, demonstrating how to handle HTTP status codes, authorization headers, and payload serialization.
* **Cost Efficiency:** By leveraging Serverless Inference for powerful open-source models, developers can achieve commercial-grade text-to-image synthesis without incurring the strict billing limits of proprietary APIs.

---
*Developed as a practical implementation of cloud-based multimodal AI integration and RESTful pipeline design.*