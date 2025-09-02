# Whisper Fine-Tuning for Technical Terms

## 📖 Problem Statement
OpenAI's Whisper models (including Whisper Large v3 and Whisper Large v3 Turbo) often fail to recognize **technical terms** such as:
mvn , maven , github , git , portkey , openai , chatgpt , llm , groq , Grok


This project focuses on **fine-tuning Whisper** so that i,t correctly transcribes these terms in speech.

---

## 🚀 Approach
Due to resource and GPU limitations, this project fine-tunes **Whisper Small** instead of Whisper Large v3/v3 Turbo.  
The approach includes:
- Preparing a dataset with audio samples of technical terms.
- Fine-tuning Whisper Small on the dataset.
- Comparing transcription performance **before vs after fine-tuning**.

---

## 📂 Folder Structure
```
│── data/
│ ├── audio/
│ │ ├── train/ # Training audio files
│ │ └── test/ # Test audio files
│ └── transcripts/
│ ├── train.jsonl # Training transcripts
│ └── test.jsonl # Test transcripts
│
│── Whisper_fine_tuning.ipynb # Training notebook
│── finetuned-small/ # Saved fine-tuned model
│── results/ # Baseline vs fine-tuned comparison
```
# Install dependencies
pip install transformers datasets jiwer torchaudio

📊 Dataset Format
Each transcript file (train.jsonl, test.jsonl) contains JSON lines:
```
{"audio": "data/audio/train/sample1.mp3", "sentence": "github is a version control platform"}
{"audio": "data/audio/train/sample2.mp3", "sentence": "maven is used for build automation"}
```
