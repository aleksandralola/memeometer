# 🧠 Meme-o-Meter: Multimodal Meme Sentiment Classifier

**Can AI read memes? I built Meme-o-Meter to find out.**

This project is a multimodal deep learning model designed to classify internet memes across emotional dimensions like humour, sarcasm, offence, motivation, and overall sentiment. It was developed as part of my final project for the AllWomen Applied AI Bootcamp.

---

## 🚀 Project Overview

Meme-o-Meter analyzes both **image** and **text** data using a dual-input architecture:

| Input Type  | Model Used           | Output                        |
|-------------|----------------------|-------------------------------|
| Text (OCR)  | `TFDistilBertModel`  | Encodes meme captions         |
| Image       | `EfficientNetB0`     | Encodes visual features       |

Outputs are passed through **five parallel heads** for emotion classification.

---

## 📊 Dataset

**Memotion 7k** dataset from Kaggle  
- ~7,000 memes  
- Each annotated for different emotional classes  
- Multi-label, multi-class setup  
- OCR-extracted text + images

> ⚠️ Note: This dataset contains imbalanced labels and noisy OCR outputs — preprocessing is crucial.

---

## 🛠 Features

- Multimodal model (text + image)
- Five-label emotional classification
- Data cleaning, augmentation, and rebalancing
- Trained in Google Colab (TPU)
- Output visualizations for predictions with Gradio

---

## 📦 Project Structure

meme-o-meter/
├── data/                    # Dataset & preprocessing scripts  
├── models/                  # Model architecture + training  
├── notebooks/               # Development notebooks  
├── utils/                   # Helper functions  
├── assets/                  # Visuals (diagrams, samples, etc.)  
├── README.md                # This file  
└── requirements.txt         # Python dependencies 

---

## 💡 Lessons Learned

- **Multimodal fusion is tricky.** Aligning text and image embeddings took lots of trial and error.
- **Model checkpoints matter.** Version mismatches stopped me from saving — a costly mistake.
- **Overfitting happens fast.** Dropout, batch norm, and tuning were critical.
- **Data balance is key.** Augmenting underrepresented classes helped, but had trade-offs.

---

## 🌍 Future Vision

The current project is an MVP. The long-term goal is to:
- Scrape memes in real-time
- Apply topic modelling + emotion classification
- Display trends in a live dashboard to track public mood

---

## 📚 Requirements

- **Python 3.10+**
- Libraries listed in `requirements.txt`, including:
  - TensorFlow 2.15.0
  - Transformers 4.39.3
  - Scikit-learn, OpenCV, Matplotlib, Pandas
  - Gradio, Pillow, Pytesseract (for OCR + interface)
  - Albumentations (for image augmentation)

Install all dependencies with:

```bash
pip install -r requirements.txt
```

> ⚠️ Make sure Tesseract OCR is installed on your system. For example:

```bash
sudo apt-get update
sudo apt-get install -y tesseract-ocr
```
