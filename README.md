# Fraud Payment Transaction Detection

A Flask-based machine learning application for identifying suspicious payment transactions. The project supports two fraud-detection workflows: a European credit card transaction model and a synthetic payment transaction model inspired by Sparkov-style transaction data.

## Features

- Web interface for fraud prediction.
- Separate prediction paths for European and synthetic payment datasets.
- User signup and signin flow backed by a local SQLite database.
- Exploratory notebooks for model training and analysis.
- Sample synthetic datasets included for quick testing and documentation.
- Large raw datasets and trained models are intentionally excluded from GitHub.

## Tech Stack

- Python
- Flask
- NumPy
- Pandas
- scikit-learn
- Joblib
- SQLite
- HTML, CSS, JavaScript

## Repository Structure

```text
.
├── app.py
├── European.ipynb
├── Sparkov.ipynb
├── sample_data/
│   ├── european_creditcard_sample.csv
│   ├── synthetic_payment_sample.csv
│   └── README.md
├── static/
├── templates/
├── requirements.txt
└── README.md
```

## Dataset Notes

The original datasets are large, so they are not committed to this repository.

Expected full dataset locations if you train locally:

- `European/creditcard.csv`
- `Sparkov/fraudTrain.csv`
- `Sparkov/fraudTest.csv`

Small synthetic examples are available in `sample_data/` so visitors can understand the expected data shape without downloading huge files.

## Model Artifacts

The app expects trained model files at:

- `Models/model_eu.sav`
- `Models/model_spark.sav`

These files are ignored because trained models can be large. To run prediction locally, train the models using the notebooks and save the artifacts to the `Models/` folder with the names above.

## Setup

```bash
python -m venv venv
venv\Scripts\activate
pip install -r requirements.txt
```

## Run the App

```bash
python app.py
```

Then open:

```text
http://127.0.0.1:5000
```

## How to Test

1. Start the Flask app.
2. Sign up with a test account.
3. Sign in and open the prediction pages.
4. Use values from `sample_data/` to understand the type of input expected.
5. Add trained model files under `Models/` before running live predictions.

## Future Improvements

- Add model evaluation reports with precision, recall, F1-score, and ROC-AUC.
- Add SHAP or feature-importance explanations for predictions.
- Replace plain-text passwords with hashed password storage.
- Add API endpoints for batch fraud scoring.
- Add Docker support for easier deployment.
