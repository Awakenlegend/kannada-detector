# Kannada Fake News Detector

An AI-powered **Fake News Detection System for Kannada language** built using **FastAPI and Streamlit**.

This project focuses on **fine-tuning the IndicBERT model** to classify Kannada news articles as **Real or Fake**.
Instead of training a model from scratch, we adapt a powerful **pre-trained Indic language model** and fine-tune it using Kannada news datasets.

The system provides a **web interface and API** where users can input Kannada text and receive a prediction indicating whether the news is **fake or real**.

---

# Live Demo

Try the deployed application:

https://kannadadetector-igbkcjph.manus.space/

---

# Features

* Fake news detection for Kannada text
* Fine-tuned **IndicBERT model for Kannada NLP tasks**
* FastAPI backend for prediction APIs
* Streamlit frontend for user interaction
* Real-time classification of news content
* Supports Kannada news articles and social media text

---

# Project Contribution

This project does not build a language model from scratch.
Instead, the key contribution is **fine-tuning a state-of-the-art Indic language model (IndicBERT)** specifically for **Kannada fake news classification**.

Our work focuses on:

* Fine-tuning **IndicBERT** for Kannada fake news detection
* Building a **machine learning pipeline** for text classification
* Creating a **FastAPI-based backend for model inference**
* Developing a **Streamlit-based interactive frontend**
* Integrating the model into a **real-world web application**

---

# System Architecture

```
User Input (Kannada News Text)
        ↓
Streamlit Web Interface
        ↓
FastAPI Backend
        ↓
Text Preprocessing
        ↓
Fine-tuned IndicBERT Model
        ↓
Fake News Classification
        ↓
Prediction Output (Fake / Real)
```

---

# Tech Stack

## Backend

* Python
* FastAPI
* HuggingFace Transformers
* PyTorch

## Frontend

* Streamlit

## Model

* **IndicBERT (AI4Bharat)** – Fine-tuned for Kannada fake news classification

## Libraries

* transformers
* torch
* scikit-learn
* pandas
* numpy

---

# Project Structure

```
kannada-detector/
│
├── backend/
│   ├── main.py
│   ├── model.py
│   ├── predict.py
│   └── requirements.txt
│
├── frontend/
│   └── app.py
│
├── datasets/
│   └── kannada_fake_news_dataset.csv
│
├── models/
│   └── finetuned_indicbert/
│
├── screenshots/
│
└── README.md
```

---

# Installation

## Clone the Repository

```
git clone https://github.com/Awakenlegend/kannada-detector.git
cd kannada-detector
```

---

## Create Environment (Conda)

```
conda create -n kannada-ai python=3.11 -y
conda activate kannada-ai
```

---

## Alternative (Without Conda)

```
python -m venv venv
source venv/bin/activate
```

For Windows:

```
venv\Scripts\activate
```

---

## Install Dependencies

```
pip install -r requirements.txt
```

---

# Run the Backend (FastAPI)

```
cd backend
uvicorn main:app --reload
```

Backend will run at:

```
http://127.0.0.1:8000
```

API documentation:

```
http://127.0.0.1:8000/docs
```

---

# Run the Frontend (Streamlit)

```
cd frontend
streamlit run app.py
```

The web application will open in your browser.

---

# API Endpoint

## Fake News Detection

```
POST /predict
```

Example Request

```
{
"text": "ಈ ಸುದ್ದಿ ನಿಜವಲ್ಲ ಎಂದು ಹೇಳಲಾಗುತ್ತಿದೆ"
}
```

Example Response

```
{
"prediction": "Fake News"
}
```

---

# Example Use Cases

* Detecting fake news in Kannada social media
* Fact-checking Kannada news articles
* News verification tools for journalists
* Government misinformation monitoring systems
* AI-powered Kannada media analysis

---

# Screenshots

Add screenshots of the application interface.

Example:

```
screenshots/homepage.png
screenshots/prediction.png
```

---

# Future Improvements

* Larger Kannada fake news dataset
* Multi-language fake news detection
* Integration with social media platforms
* Real-time news monitoring system
* Mobile application support

---

# Contributors

Mohammed Farhan
BTech AI & ML Engineering Student

---

# License

This project is licensed under the **MIT License**.
