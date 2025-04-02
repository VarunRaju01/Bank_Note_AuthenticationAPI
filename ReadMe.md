Bank Note Authentication API

Overview

This project provides a FastAPI-based web application that predicts whether a banknote is real or fake using a trained machine learning model. The model is trained using the RandomForestClassifier and is saved as a pickle file (classifier.pkl).

Project Structure

├── app.py                # FastAPI application for prediction
├── BankNotes.py          # (If any) Data model for request validation
├── trainer.py            # Script to train and save the model
├── BankNote_Authentication.csv  # Dataset used for training
├── classifier.pkl        # Saved ML model (Generated after running trainer.py)
├── README.md             # Project documentation

Requirements

Ensure you have the required dependencies installed before running the application.

Install the required libraries using:

pip install -r requirements.txt

If you do not have a requirements.txt, manually install the required packages:

pip install fastapi uvicorn numpy pandas scikit-learn

Training the Model

To train the model and generate classifier.pkl, run:

python trainer.py

Running the API

Once the model is trained, run the FastAPI application using:

python app.py

Alternatively, use:

uvicorn app:app --reload

API Endpoints

1. Home Route

URL: /

Method: GET

Response:

{
  "message": "Hello, World"
}

2. Prediction Route

URL: /predict

Method: GET

Parameters:

variance: float

skewness: float

curtosis: float

entropy: float

Response:

{
  "prediction": "Fake note" or "Its a Bank note"
}

Example Request:

http://127.0.0.1:8000/predict?variance=2.3&skewness=1.2&curtosis=0.8&entropy=-1.1

Testing the API

Once the FastAPI server is running, open a browser and visit:

http://127.0.0.1:8000/docs

This will open an interactive API documentation where you can test the endpoints.

License

This project is licensed under the MIT License.

Feel free to contribute and improve this project!

