# Prompt Engineering Techniques Implementation 🚀

This repository contains practical implementations of advanced Prompt Engineering techniques using the **Google Gemini 2.5 Flash API** within a Google Colab environment. 

## 📌 Overview
The goal of this assignment is to compare, contrast, and analyze different methods of interacting with Large Language Models (LLMs) to optimize their outputs for various tasks, including predictive analytics, classification, and complex reasoning.

## 🛠️ Technologies Used
* **Python 3**
* **Google Generative AI SDK** (`google-generativeai`)
* **Google Colab**
* **Gemini 2.5 Flash Model**

## 🧠 Implemented Approaches

1.  **Zero-Shot Prompting:** Direct instruction without examples. Tests the model's base knowledge and zero-shot reasoning capabilities.
2.  **Few-Shot Prompting:** Guiding the model's output format and logic by providing 2-3 curated input-output examples prior to the main query.
3.  **Chain of Thought (CoT):** Enhancing logical deduction by instructing the model to "think step-by-step" and expose its intermediate reasoning before arriving at a final conclusion.
4.  **Tree of Thoughts (ToT):** Simulating a multi-path reasoning environment where the model generates multiple potential solutions, evaluates them against specific criteria, and selects the optimal path.
5.  **The Interview Approach:** Flipped interaction where the LLM is assigned an expert persona and dynamically interviews the user to gather context before providing a tailored solution. Implemented using `genai.ChatSession`.

## 🚀 How to Run

1.  Open the `Prompt_Engineering_Assignment.ipynb` notebook in Google Colab.
2.  Obtain an API key from [Google AI Studio](https://aistudio.google.com/).
3.  Add your API key to the Colab Secrets (the key icon on the left sidebar) under the name `GEMINI_API_KEY` and enable notebook access.
4.  Run the cells sequentially.

## 📊 Analysis and Comparison
A detailed comparative analysis of the applications, token efficiency, and reliability of each approach is included at the bottom of the Colab notebook.

---
**Author:** Omkar Shinde
