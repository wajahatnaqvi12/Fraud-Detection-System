# Fraud Detection System

## Overview
This project implements a machine learning-based fraud detection system using the Credit Card Fraud Detection dataset. The system is designed to identify potentially fraudulent transactions with high accuracy while handling the severe class imbalance inherent in financial fraud data.

## Features
- Data preprocessing and exploratory analysis
- Handling of class imbalance through undersampling
- Random Forest classification model
- Model evaluation with precision, recall, and F1-score metrics
- Interactive prediction interface
- Model persistence for future use

## Dataset
The dataset contains anonymized credit card transactions labeled as fraudulent (1) or legitimate (0). Features include:
- Time: Seconds elapsed between transaction and first transaction
- V1-V28: Principal components obtained through PCA
- Amount: Transaction amount
- Class: Target variable (0=legitimate, 1=fraud)

Dataset characteristics:
- Total transactions: 284,807
- Fraudulent transactions: 492 (0.172%)
- Legitimate transactions: 284,315 (99.828%)

## Installation
1. Clone this repository:
   ```bash
   git clone https://github.com/yourusername/credit-card-fraud-detection.git
   cd credit-card-fraud-detection
   ```

2. Install required packages:
   ```bash
   pip install -r requirements.txt
   ```

## Usage
1. Run the Jupyter notebook to train the model:
   ```bash
   jupyter notebook Task03.ipynb
   ```

2. For interactive predictions:
   - The notebook includes a cell that prompts for transaction details
   - Enter values for each feature when prompted
   - The system will output whether the transaction is predicted as legitimate or fraudulent

## Model Performance
The Random Forest classifier achieved the following performance metrics:

| Class   | Precision | Recall | F1-score | Support |
|---------|-----------|--------|----------|---------|
| Legitimate (0) | 0.88      | 1.00   | 0.94     | 99      |
| Fraudulent (1) | 1.00      | 0.87   | 0.93     | 98      |
| **Accuracy**   |           |        | 0.93     | 197     |
| **Macro Avg**  | 0.94      | 0.93   | 0.93     | 197     |

## Key Considerations
- **Class Imbalance**: The original dataset is highly imbalanced (492 frauds vs 284,315 legitimate transactions)
- **Undersampling**: Used to balance classes by randomly selecting 492 legitimate transactions
- **Evaluation Metrics**: Focus on recall (identifying all frauds) is crucial in fraud detection
- **Scalability**: For production use, consider deploying as a web service with automated pipelines

## Future Improvements
- Experiment with other sampling techniques (SMOTE, ADASYN)
- Try alternative models (XGBoost, Neural Networks)
- Implement feature engineering
- Develop a web-based interface
- Add model monitoring and retraining capabilities

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments
- Dataset from [Kaggle](https://www.kaggle.com/mlg-ulb/creditcardfraud)
- Scikit-learn and imbalanced-learn libraries
