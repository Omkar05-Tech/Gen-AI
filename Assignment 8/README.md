# 🎙️ AI Text-to-Speech (TTS) Generator
A beginner-friendly Google Colab implementation for converting text into spoken audio using the Google TTS API.

## 📌 Overview
Generative AI and speech synthesis tools make it incredibly easy to turn written text into natural-sounding audio. While this notebook is part of a broader exploration into advanced models like Tacotron and WaveNet, the current implementation focuses on the simplest and most accessible method: using Google Text-to-Speech (gTTS). The script processes a text string, generates speech, and compiles it into a playable .mp3 audio format directly inside the notebook.

## 🛠️ Technology Stack
Language: Python 3

Environment: Google Colab (Standard CPU runtime is sufficient)

Libraries: gTTS (Google Text-to-Speech), IPython.display

Core API: Google Translate's underlying Text-to-Speech API.

## 🚀 How to Run
Open the Jupyter Notebook (TTS_using_Tacotron_&_Wavenet.ipynb) in Google Colab.

Run the Install Dependencies cell (!pip install gTTS) to install the required library.

Scroll down to the TTS Implementation cell.

Modify the text variable to any sentence or paragraph you want to convert to speech (e.g., "Welcome to text to speech conversion!").

Run the cell. The generated .mp3 audio file (output_gtts.mp3) will automatically save to your working directory.

An interactive audio player will appear directly inside the notebook, allowing you to listen to the generated speech immediately.

## ⚙️ How it Works
Text Input: The user provides a target string and specifies the language (e.g., lang='en').

API Interface: The gTTS module acts as a wrapper, sending the text payload to Google's TTS API.

Audio Synthesis: The API processes the text and returns synthesized speech data.

Export & Playback: The resulting audio data is saved as a standard .mp3 file. The IPython.display.Audio utility is then called to render a playable HTML5 audio widget right in the Colab output cell.

Developed as a practical exploration of speech synthesis pipelines and accessible TTS methodologies.