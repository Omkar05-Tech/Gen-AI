# 📖 Fine-Tuning GPT-2 for Creative Story Generation

Welcome to this project! This repository contains a simple, beginner-friendly implementation of **fine-tuning** a Large Language Model (LLM). 

We are taking a base AI model (**GPT-2**) and teaching it how to write creative short stories by feeding it a specific dataset of stories.

## 🤔 What is Fine-Tuning?
Imagine GPT-2 as a student who has read the entire internet and knows a lot of general information. **Fine-tuning** is like sending that student to a specialized creative writing class. By showing it thousands of examples of short stories, the model learns the specific style, tone, and structure we want it to produce.

## 🛠️ Technologies & Libraries Used
* **Python 3**
* **Google Colab:** A free, cloud-based coding environment.
* **Hugging Face `transformers`:** The industry-standard library for downloading and using AI models.
* **Hugging Face `datasets`:** A library to easily download and process training data.
* **PyTorch (`torch`):** The underlying math engine that powers the AI's learning process.

## 🗂️ The Dataset
This project uses a small piece of the **[TinyStories](https://huggingface.co/datasets/roneneldan/TinyStories)** dataset. TinyStories contains short, simple stories generated with a limited vocabulary. It is perfect for teaching a smaller model like GPT-2 how to construct a coherent narrative without overwhelming your computer's memory.

## 🚀 How to Run This Code

### 1. Set Up Google Colab
You need a GPU (Graphics Processing Unit) to train AI models in a reasonable amount of time.
1. Open a new notebook in [Google Colab](https://colab.research.google.com/).
2. In the top menu, go to **Runtime** > **Change runtime type**.
3. Under "Hardware accelerator", select **T4 GPU** and click Save.

### 2. Copy the Code
Copy the code provided in this repository cell-by-cell into your Colab notebook.

### 3. Run the Steps
Here is what the code does when you run it:
1. **Install Dependencies:** Downloads the necessary Hugging Face tools.
2. **Load Model & Tokenizer:** Downloads the "brain" (GPT-2) and the "dictionary" (Tokenizer) the AI uses to read words.
3. **Prepare the Data:** Downloads 5,000 stories and chops the text up into numbers (tokens) that the AI can understand.
4. **Train (The Magic Happens here):** The model practices writing the stories. It guesses the next word, checks the actual story, corrects itself, and learns. This takes a few minutes.
5. **Generate:** We give the newly trained model a starting prompt (like *"Once upon a time"*), and it writes a brand new story for us!

## 🧪 Experimenting
Once you get it running, try changing these generation parameters at the very bottom of the code to see how it affects the story:
* `temperature`: Make it higher (e.g., `1.2`) for crazier, more random stories. Make it lower (e.g., `0.3`) for safer, more predictable text.
* `max_length`: Change how long the story is.

---
*Built as a practical assignment for exploring generative AI and model fine-tuning.*