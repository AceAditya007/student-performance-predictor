# Student Performance Predictor

A machine learning web application that predicts a student's final mathematics performance category using academic, demographic, and lifestyle factors.

**GitHub Repository:** [AceAditya007/student-performance-predictor](https://github.com/AceAditya007/student-performance-predictor)

This project was developed by **Aditya Sharma** to demonstrate practical skills in Python, data preprocessing, machine learning, model evaluation, and interactive web application development.

## Project Overview

The Student Performance Predictor classifies a student's expected performance into one of three categories:

- **Low**: Final grade from 0 to 9
- **Medium**: Final grade from 10 to 13
- **High**: Final grade from 14 to 20

The application collects student-related inputs through a Streamlit interface and uses a trained Scikit-learn pipeline to generate a prediction with confidence scores.

## Key Features

- Interactive and easy-to-use Streamlit interface
- Prediction based on 30 student-related features
- Automated preprocessing for numerical and categorical data
- Comparison of Logistic Regression and Random Forest models
- Model selection using macro F1-score
- Confidence scores for each performance category
- Clear separation between model training and prediction code

## Technologies Used

- **Python**
- **Pandas** for data handling and analysis
- **Scikit-learn** for preprocessing, model training, and evaluation
- **Streamlit** for the web interface
- **Joblib** for saving and loading the trained model
- **Jupyter Notebook / Google Colab** for experimentation and analysis

## Machine Learning Workflow

1. Loaded and explored the student performance dataset.
2. Created Low, Medium, and High performance categories from the final grade.
3. Removed `G1` and `G2` to reduce data leakage because they are earlier-period grades closely related to the final grade.
4. Split the dataset into stratified training and testing sets.
5. Applied median imputation to numerical features.
6. Applied most-frequent imputation and one-hot encoding to categorical features.
7. Trained Logistic Regression and Random Forest classifiers.
8. Compared both models using accuracy and macro F1-score.
9. Saved the selected pipeline and connected it to the Streamlit application.

## Model Results

| Model | Accuracy | Macro F1-score |
|---|---:|---:|
| Logistic Regression | 48.1% | 48.1% |
| Random Forest | 49.4% | 48.4% |

The **Random Forest** model was selected because it achieved the higher macro F1-score. The modest results also demonstrate a realistic machine learning challenge: predicting final academic performance without using earlier-period grades.

## Dataset

The project uses the mathematics-course data from the [UCI Student Performance Dataset](https://archive.ics.uci.edu/dataset/320/student+performance). The dataset is distributed under the [Creative Commons Attribution 4.0 International license](https://creativecommons.org/licenses/by/4.0/).

## Project Structure

```text
student-performance-predictor/
|-- app.py
|-- data/
|   |-- README.md
|   `-- student-mat.csv
|-- notebooks/
|   |-- student_performance_analysis.ipynb
|   `-- student_performance_colab.ipynb
|-- src/
|   |-- __init__.py
|   |-- predict.py
|   |-- preprocessing.py
|   `-- train.py
|-- requirements.txt
`-- README.md
```

## Run the Project Locally

### 1. Clone the repository

```bash
git clone https://github.com/AceAditya007/student-performance-predictor.git
cd student-performance-predictor
```

### 2. Create and activate a virtual environment

```bash
python -m venv .venv
```

On Windows:

```bash
.venv\Scripts\activate
```

On macOS or Linux:

```bash
source .venv/bin/activate
```

### 3. Install the dependencies

```bash
pip install -r requirements.txt
```

### 4. Train and save the model

```bash
python -m src.train
```

### 5. Start the Streamlit application

```bash
streamlit run app.py
```

Open `http://localhost:8501` in a browser if Streamlit does not open automatically.

## Skills Demonstrated

- Exploratory data analysis
- Data preprocessing and feature engineering
- Classification model development
- Model comparison and evaluation
- Prevention of data leakage
- Python project organization
- Interactive machine learning application development

## Future Improvements

- Tune model hyperparameters using cross-validation
- Compare additional models such as Gradient Boosting and XGBoost
- Add model explainability using feature importance or SHAP
- Improve the user interface and mobile responsiveness
- Deploy the application online and add a live-demo link
- Explore regression to predict the final grade directly

## Important Note

This project is an educational machine learning demonstration. Its predictions should not be treated as a definitive assessment of a student's academic ability.

## Developer

**Aditya Sharma**  

---

If you find this project useful, consider giving the repository a star.
