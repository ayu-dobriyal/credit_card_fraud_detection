# Credit Card Fraud Detection System

A comprehensive machine learning-powered web application for detecting fraudulent credit card transactions using advanced algorithms including Logistic Regression, Random Forest, XGBoost, and Hybrid Models with SMOTE for handling class imbalance.

## Features

- **Multiple ML Models**: Logistic Regression, Random Forest, XGBoost, and Hybrid ensemble
- **SMOTE Integration**: Handles class imbalance using Synthetic Minority Oversampling
- **Web Interface**: User-friendly Flask web application with responsive design
- **Dual Input Methods**: Manual entry and CSV file upload for batch processing
- **Real-time Predictions**: Instant fraud detection with confidence scores
- **Comprehensive Analytics**: Detailed performance reports and visualizations
- **Professional UI**: Modern, mobile-responsive interface with interactive charts

## Model Performance

| Model | Accuracy | Precision | Recall | F1-Score | AUC |
|-------|----------|-----------|--------|----------|-----|
| Logistic Regression | 99.95% | 88.46% | 61.22% | 72.48% | 98.67% |
| Random Forest | 99.96% | 90.32% | 75.51% | 82.26% | 99.23% |
| XGBoost | 99.96% | 91.67% | 73.47% | 81.58% | 99.18% |
| **Hybrid Model** | **99.97%** | **92.86%** | **78.57%** | **85.11%** | **99.34%** |


## Installation & Setup

### Prerequisites
- Python 3.8 or higher
- pip package manager

### Local Development Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/SagarRawat0607/Credit_Card_Fraud_Detection_Model
   cd credit-card-fraud-detection
   ```

2. **Create virtual environment**

   ```bash
   python -m venv fraud_detection_env
   source fraud_detection_env/bin/activate 
   ```
   
   ```bash
   On Windows: fraud_detection_env\Scripts\activate
   ```

3. **Install dependencies**

   ```bash
   pip install -r requirements.txt
   ```

4. **Download dataset** (Optional - for training new models)

   * Download the credit card fraud dataset from [Kaggle](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud)
   * Place `creditcard.csv` in the project root directory

5. **Train models** (Optional - pre-trained models included)

   ```bash
   python fraud_detection_ml.py
   ```

6. **Run the application**

   ```bash
   python app.py
   ```

7. **Access the application**

   * Open your browser and go to `http://localhost:5000`

## Project Structure

```
project/
├── static/             # Frontend static files (JS, CSS)
│ ├── script.js         # JavaScript functionality for UI
│ └── style.css         # Stylesheet for UI design
│
├── templates/          # HTML templates for Flask
│ └── index.html        # Main web interface
│
├── .gitignore          # Git ignore rules for unnecessary files
├── app.py              # Flask application entry point
├── bigger_test.csv     # Larger CSV dataset for testing
├── creditcard.csv      # Original dataset (from Kaggle)
├── Model.ipynb         # Jupyter Notebook for experiments/training
├── model.pkl           # Trained ML model (serialized with pickle)
├── README.md           # Project documentation
├── requirements.txt    # Python dependencies
├── scaler.pkl          # Feature scaler object (for preprocessing)
└── test.csv            # Sample CSV dataset for predictions
```

## Usage

### Manual Transaction Prediction

1. Navigate to the **"Manual Entry"** tab
2. Enter transaction details:

   * **Time**: Transaction time in seconds
   * **V1-V28**: PCA-transformed features
   * **Amount**: Transaction amount in currency units
3. Click **"Predict Transaction"**
4. View results with confidence scores and interpretation

### CSV Batch Prediction

1. Navigate to the **"CSV Upload"** tab
2. Upload a CSV file with required columns: `Time, V1, V2, ..., V28, Amount, Class`
3. Click **"Analyze CSV"**
4. View comprehensive results including:

   * Individual transaction predictions
   * Summary statistics
   * Fraud detection rate
   * Downloadable results

### Required CSV Format

```
Time,V1,V2,V3,...,V28,Amount,Class
0,-1.3598071336,-0.0727811732,2.536346738,...,-0.021053053,149.62
86400,1.1918571934,0.2661507134,-1.609233891,...,0.133558377,25.00
```

## Machine Learning Pipeline

### 1. Data Preprocessing

* **Feature Scaling**: StandardScaler for normalization
* **Class Balancing**: SMOTE (Synthetic Minority Oversampling Technique)
* **Feature Engineering**: Handling of PCA-transformed features V1-V28

### 2. Model Training

* **Logistic Regression**: Linear classification baseline
* **Random Forest**: Ensemble method with 100 estimators
* **XGBoost**: Gradient boosting with hyperparameter optimization
* **Hybrid Model**: Voting classifier combining Random Forest and XGBoost

### 3. Evaluation Metrics

* **Classification Metrics**: Accuracy, Precision, Recall, F1-Score
* **Probability Metrics**: ROC-AUC curves and probability distributions
* **Business Metrics**: Cost-benefit analysis and fraud detection rate

## Visualizations

The application includes comprehensive visualizations:

* **Class Distribution Analysis**: Before and after SMOTE
* **Feature Importance Plots**: Top contributing features
* **ROC Curves Comparison**: Model performance comparison
* **Confusion Matrices**: Detailed classification results
* **Performance Metrics Dashboard**: Interactive charts

## Future Enhancements

* [ ] Real-time transaction monitoring
* [ ] Advanced ensemble methods
* [ ] Deep learning model integration
* [ ] API rate limiting and authentication
* [ ] Database integration for transaction history
* [ ] Advanced data visualization dashboard
* [ ] Mobile application development
* [ ] Multi-language support

**Developed for fraud detection and financial security**