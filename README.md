# Kannada Detector

An AI-powered **Kannada Language Detection and Translation System** built using **FastAPI and Streamlit**.

This project focuses on **fine-tuning existing multilingual models such as IndicBERT and IndicTrans2** to improve Kannada language detection and translation performance.

Instead of training models from scratch, we adapt and fine-tune powerful **pre-trained Indic language models** using Kannada datasets and integrate them into a scalable web system.

---

## Live Demo

Try the deployed application:

https://kannadadetector-igbkcjph.manus.space/

---

## Features

* Kannada language detection
* Kannada ↔ English translation
* Support for romanized Kannada input
* AI-powered NLP system using fine-tuned models
* FastAPI backend for scalable APIs
* Interactive Streamlit web interface
* Support for Kannada text processing

---

## Project Contribution

This project does not build large language models from scratch.
Instead, the main contribution is **fine-tuning and adapting state-of-the-art multilingual models for Kannada NLP tasks**.

Our contributions include:

* Fine-tuning **IndicBERT** for better Kannada language understanding
* Fine-tuning **IndicTrans2** for improved Kannada translation
* Building a scalable **FastAPI backend**
* Developing a **Streamlit-based frontend**
* Integrating the models into a real-world Kannada NLP system

---

## System Architecture

```
User Input
↓
Streamlit Frontend
↓
FastAPI Backend
↓
Language Detection
↓
Fine-tuned NLP Models
├── IndicBERT
└── IndicTrans2
↓
Translation Output
```

---

## Tech Stack

### Backend

* Python
* FastAPI
* HuggingFace Transformers
* PyTorch

### Frontend

* Streamlit

### Models

* **IndicBERT (AI4Bharat)** – Fine-tuned for Kannada language understanding
* **IndicTrans2** – Fine-tuned for Kannada translation tasks

### Libraries

* langdetect
* indic-transliteration
* transformers
* torch

---

## Project Structure

```
kannada-detector/
│
├── backend/
│   ├── main.py
│   ├── detection.py
│   ├── translation.py
│   └── requirements.txt
│
├── frontend/
│   └── app.py
│
├── datasets/
│   └── kannada_dataset.json
│
├── models/
│
├── screenshots/
│
└── README.md
```

---

## Installation

### Clone the Repository

```
git clone https://github.com/Awakenlegend/kannada-detector.git
cd kannada-detector
```

---

### Create Environment (Conda)

```
conda create -n kannada-nlp python=3.11 -y
conda activate kannada-nlp
```

---

### Alternative (Without Conda)

```
python -m venv venv
source venv/bin/activate
```

For Windows:

```
venv\Scripts\activate
```

---

### Install Dependencies

```
pip install -r requirements.txt
```

---

## Run the Backend (FastAPI)

```
cd backend
uvicorn main:app --reload
```

Backend will run at:

```
http://127.0.0.1:8000
```

API Documentation:

```
http://127.0.0.1:8000/docs
```

---

## Run the Frontend (Streamlit)

```
cd frontend
streamlit run app.py
```

The web application will open automatically in your browser.

---

## API Endpoints

### Language Detection

```
POST /detect
```

Example Request:

```
{
"text": "ನಮಸ್ಕಾರ"
}
```

Example Response:

```
{
"language": "Kannada"
}
```

---

### Translation

```
POST /translate
```

Example Request:

```
{
"text": "ನಮಸ್ಕಾರ",
"target_language": "English"
}
```

Example Response:

```
{
"translation": "Hello"
}
```

---

## Example Use Cases

* Fake news detection systems for Kannada media
* Multilingual chatbots
* Kannada translation tools
* Educational language learning platforms
* Government service portals supporting regional languages

---

## Screenshots

Add screenshots of your application here.

Example:

```
screenshots/homepage.png
screenshots/translation.png
```

---

## Future Improvements

* Kannada speech-to-text integration
* Fake news detection for Kannada articles
* Mobile application support
* Support for more Indic languages
* Further model fine-tuning with larger datasets

---

## Contributors

Mohammed Farhan
BTech AI & ML Engineering Student

---

## License

This project is licensed under the **MIT License**.
