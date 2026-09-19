# Customer Churn Prediction using ANN

A machine learning web app that predicts whether a bank customer is likely to churn (leave the bank), built with an Artificial Neural Network (ANN) using TensorFlow/Keras and deployed as an interactive Streamlit app.

🔗 **Live Demo:** [churnclassificationusingann-hbtah7abtutx7bbdqbwauz.streamlit.app](https://churnclassificationusingann-hbtah7abtutx7bbdqbwauz.streamlit.app/)

## Overview

This project uses the classic `Churn_Modelling.csv` bank customer dataset to train a feed-forward neural network that predicts the probability of a customer churning, based on features like credit score, geography, gender, age, tenure, balance, number of products, and account activity. The trained model, along with its preprocessing objects (label encoder, one-hot encoder, and scaler), is loaded into a Streamlit app that takes user input and returns a real-time churn prediction.

## Features

- ANN-based binary classification model trained with TensorFlow/Keras
- Preprocessing pipeline with `LabelEncoder`, `OneHotEncoder`, and `StandardScaler`
- Interactive Streamlit UI for entering customer details
- Real-time churn probability output with a clear likely/unlikely verdict
- Deployed and publicly accessible on Streamlit Community Cloud

## Project Structure

```
churn_classification_using_ann/
├── app.py                      # Streamlit app for churn prediction
├── experiments.ipynb           # Notebook: data preprocessing & model training
├── prediction.ipynb            # Notebook: loading the model & making predictions
├── Churn_Modelling.csv          # Dataset used for training
├── model.h5                     # Trained ANN model
├── label_encoder_gender.pkl     # Fitted LabelEncoder for the Gender column
├── onehot_encoder_geo.pkl       # Fitted OneHotEncoder for the Geography column
├── scaler.pkl                   # Fitted StandardScaler for numerical features
├── requirements.txt             # Python dependencies
├── runtime.txt                  # Python runtime version for deployment
└── README.md
```

## Tech Stack

- **Python**
- **TensorFlow / Keras** – building and training the ANN
- **scikit-learn** – preprocessing (encoding & scaling)
- **Pandas / NumPy** – data handling
- **Streamlit** – web app interface and deployment
- **Matplotlib / TensorBoard** – training visualization

## Model Input Features

| Feature | Description |
|---|---|
| CreditScore | Customer's credit score |
| Geography | Customer's country (one-hot encoded) |
| Gender | Customer's gender (label encoded) |
| Age | Customer's age |
| Tenure | Number of years as a bank customer |
| Balance | Account balance |
| NumOfProducts | Number of bank products used |
| HasCrCard | Whether the customer has a credit card (0/1) |
| IsActiveMember | Whether the customer is an active member (0/1) |
| EstimatedSalary | Customer's estimated salary |

The model outputs a churn probability between 0 and 1. A probability greater than 0.5 is classified as "likely to churn."

## Getting Started

### Prerequisites

- Python 3.8+ installed

### Installation

1. Clone the repository
   ```bash
   git clone https://github.com/mayank-1584/churn_classification_using_ann.git
   cd churn_classification_using_ann
   ```

2. (Optional) Create and activate a virtual environment
   ```bash
   python -m venv venv
   source venv/bin/activate   # On Windows: venv\Scripts\activate
   ```

3. Install dependencies
   ```bash
   pip install -r requirements.txt
   ```

### Running the App Locally

```bash
streamlit run app.py
```

The app will open in your browser, typically at `http://localhost:8501`.

## How It Works

1. The user enters customer details (geography, gender, age, balance, credit score, etc.) through the Streamlit UI.
2. The input is encoded using the saved `LabelEncoder` (Gender) and `OneHotEncoder` (Geography), matching the preprocessing used during training.
3. The combined feature set is scaled with the saved `StandardScaler`.
4. The preprocessed input is passed to the trained ANN (`model.h5`) to generate a churn probability.
5. The app displays the probability and a plain-language verdict on whether the customer is likely to churn.

## Notebooks

- **`experiments.ipynb`** – Exploratory data analysis, preprocessing, and training of the ANN model on the `Churn_Modelling.csv` dataset.
- **`prediction.ipynb`** – Loading the saved model and encoders/scaler to run predictions on new/sample data.

## Deployment

The app is deployed on **Streamlit Community Cloud**:
👉 https://churnclassificationusingann-hbtah7abtutx7bbdqbwauz.streamlit.app/

## Author

**Mayank** – [GitHub Profile](https://github.com/mayank-1584)

## License

This project currently has no license specified. Feel free to reach out to the author for usage permissions.