# TripAdvisor Sentiment Analysis Backend

This is a FastAPI-based backend service that predicts sentiment (Positive/Negative) for TripAdvisor reviews using a trained Machine Learning model.

## Features

- **Sentiment Prediction**: Classifies text reviews as "Positive" or "Negative".
- **Confidence Score**: Returns the confidence level of the prediction.
- **Health Check**: Simple endpoint to verify the API is running.

## Tech Stack

- **Python 3**
- **FastAPI**: High-performance web framework for building APIs.
- **Scikit-learn / Joblib**: For loading and using the pre-trained ML models.
- **Uvicorn**: ASGI server for running the application.

## Setup & Installation

1.  **Clone the repository**:
    ```bash
    git clone <repository-url>
    cd backend-TripAdvisor
    ```

2.  **Install dependencies**:
    ```bash
    pip install -r requirements.txt
    ```

3.  **Run the application**:
    ```bash
    python main.py
    ```
    Or using uvicorn directly:
    ```bash
    uvicorn main:app --reload
    ```

The API will be available at `http://localhost:8000`.

## API Endpoints

### 1. Health Check
- **URL**: `/`
- **Method**: `GET`
- **Response**:
  ```json
  {"message": "API is running"}
  ```

### 2. Predict Sentiment
- **URL**: `/predict`
- **Method**: `POST`
- **Body**:
  ```json
  {
    "text": "This hotel was amazing! Great service and clean rooms."
  }
  ```
- **Response**:
  ```json
  {
    "sentiment": "Positive",
    "confidence": 0.9854
  }
  ```

## Model Details
The application loads two artifacts at startup:
- `sentiment_model.pkl`: The trained classifier.
- `tfidf_vectorizer.pkl`: The TF-IDF vectorizer for text preprocessing.
