# 🤖 Question-Answering Chatbot using FLAN-T5

This repository contains an interactive Question-Answering (QA) chatbot built using Python and the Hugging Face `transformers` library. It leverages Google's **FLAN-T5-base**, a powerful pre-trained language model optimized for instruction-following and reading comprehension.

## 📌 Overview
The goal of this project is to demonstrate how pre-trained sequence-to-sequence models can be used to build conversational agents. The chatbot is capable of two modes of operation:
1. **Zero-Shot Question Answering:** Answering general knowledge questions based purely on its internal pre-trained weights.
2. **Context-Based Question Answering (Reading Comprehension):** Reading a specific paragraph of text provided by the user and extracting precise answers from it.

## 🛠️ Technology Stack
* **Language:** Python 3
* **Environment:** Google Colab / Jupyter Notebook
* **Libraries:** `transformers`, `torch`, `accelerate`, `sentencepiece`
* **Model:** `google/flan-t5-base` (An open-source, instruction-tuned LLM).

## ✨ Key Features
* **Interactive Chat Loop:** A continuous command-line interface allowing natural back-and-forth prompting.
* **Dynamic Context Injection:** Users can dynamically teach the bot new information during the chat by typing `context: [your text]`. The bot will then use that specific text to answer subsequent questions.
* **Parameter Tuning:** Implements text generation parameters like `num_beams` (for beam search decoding), `temperature`, and `early_stopping` to optimize the output quality.

## 🚀 How to Run

1. Open the Jupyter Notebook (`Chatbot_using_Pre_trained__Model_FLAN_T5.ipynb`) in Google Colab.
2. Ensure your runtime has adequate RAM (a GPU is recommended but not strictly required for the `base` model).
3. Run the cells sequentially to install dependencies and download the model weights.
4. Run the final cell to launch the interactive `run_chatbot()` interface.

### Chatbot Commands
* Type any standard question to test its general knowledge.
* Type `context: [paste a paragraph here]` to give the bot a temporary knowledge base.
* Type `quit`, `exit`, or `q` to shut down the chatbot.

## 📊 Key Observations & Learnings
This implementation highlights a fundamental concept in modern NLP:
When asked questions without context (e.g., complex math), smaller base models may hallucinate. However, when provided with a strict context window using the `context:` command, the FLAN-T5 model exhibits highly accurate, extractive reading comprehension, demonstrating the importance of context-grounding in AI applications.

---
*Developed as a practical assignment exploring pre-trained language models and conversational AI.*