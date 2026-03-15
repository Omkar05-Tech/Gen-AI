# Probabilistic Generative Models & LLM Integration

This repository contains practical implementations of text generation, multimodal analysis, and interactive user interfaces using modern, cloud-based probabilistic generative models. 

The project demonstrates how to leverage state-of-the-art Large Language Models (LLMs) via APIs to perform text generation, sentiment analysis, image reasoning, and embedding generation, alongside building interactive web UIs.

## 📁 Repository Contents

### 1. `LLM_Prompt_Cohere.ipynb`
Demonstrates text generation and classification using the **Cohere API** and **LangChain**.
* **Conversational Generation:** Implements a chat interface to generate structured, step-by-step advice (e.g., a balanced diet plan for productivity).
* **Sentiment Analysis:** Uses direct prompting to classify text sentiment (positive/negative) with constrained one-word outputs.

### 2. `LLM_Prompt_Gemini.ipynb`
Explores multimodal generative capabilities using Google's **Gemini 2.5 Flash API**.
* **Multilingual Text Generation:** Basic conversational queries in Hindi and English.
* **Error Handling:** Implements exponential backoff to handle API rate limits (`TooManyRequests`).
* **Multimodal Reasoning:** Passes both an image (e.g., an event poster) and text to the model to extract detailed, contextual information.
* **Text Embeddings:** Generates vector embeddings for text using the `text-embedding-004` model for downstream retrieval tasks.

### 3. `LLM_Prompt_Gradio.ipynb`
Focuses on building interactive, front-end web interfaces for Python functions using **Gradio**.
* **The Mirror Encoder:** A text-processing UI with checkboxes and text inputs to manipulate strings (uppercase conversion and string reversal).
* **Instant Art Studio:** An image-processing UI utilizing `numpy` for matrix math to apply visual filters (Sepia, Invert Colors, Grayscale) to user-uploaded images.

## 🛠️ Technology Stack
* **Language:** Python 3
* **LLM APIs:** Google Generative AI (`google-generativeai`), Cohere
* **Frameworks/Libraries:** LangChain (`langchain`, `langchain-cohere`), Gradio, NumPy, Pillow

## 🚀 How to Run

1. Open the desired notebook in Google Colab.
2. For the LLM notebooks, obtain the respective API keys:
   * [Cohere API Key](https://dashboard.cohere.com/)
   * [Google Gemini API Key](https://aistudio.google.com/)
3. Add your API keys to the Colab Secrets manager (key icon on the left sidebar) as `COHERE_API_KEY` and `GEMINI_API_KEY`.
4. Run the cells sequentially. Gradio applications will generate a live public URL valid for 72 hours.

---
**Author:** Omkar Shinde
