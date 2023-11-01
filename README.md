# credit-risk-classification

<div style="display: inline_block"><br/>
  <img align="center" alt="python" src="http://ForTheBadge.com/images/badges/made-with-python.svg" />

<div style="display: inline_block"><br/>
  <img align="center" alt="jupyter" src="https://img.shields.io/badge/Made%20with-Jupyter-orange?style=for-the-badge&logo=Jupyter" />

## Introduction

This data science challenge will use machine learning techniques to investigate the field of credit risk analysis. The main goal is to create and assess a model that, using past loan data from a peer-to-peer lending services provider, can reliably determine borrowers' creditworthiness. By using this research to guide decision-making, the organization will be able to minimize default risk and optimize the health of its lending portfolio.

A logistic regression model with oversampling is used in this project to account for class imbalance and produce accurate predictions.

## Libraries

The following Python libraries are needed by the project to complete its tasks:

- `Pandas` and `numpy`: These libraries are necessary for working with data. They enable us to access, modify, and examine the loan information.

- `pathlib`: The `pathlib` library facilitates file path manipulation. It's employed to indicate the dataset's location.

- `sklearn.metrics`: This library offers metrics to assess the machine learning model's performance. We utilize it to produce confusion matrices, classification reports, and the balanced accuracy score.

The `sklearn.model_selection` package is utilized to divide the data into sets for testing and training. In order to evaluate the model's generalization performance, it makes sure that it is tested on data that it has never seen before.

The `sklearn.linear_model` module is utilized to construct a Logistic Regression model.

## How the Code Works

The project performs the following detailed steps:

1. **Data Loading:** The project begins by reading a CSV file named `lending_data.csv` from the 'Resources' folder into a Pandas DataFrame. This dataset contains information about loan applicants and their loan status.

2. **Data Splitting:** After loading the data, it's split into two main components:
   - The labels (y): This represents the 'loan_status' column, which is what we aim to predict.
   - The features (X): This includes all other columns except 'loan_status'.

3. **Class Imbalance Check:** The project checks the balance of the target values (loan_status) to determine whether class imbalance exists.

4. **Data Splitting for Modeling:** The data is divided into training and testing sets using the `train_test_split` function from `sklearn.model_selection`. This ensures that the model is trained on one subset of the data and tested on another.

5. **Model Training:** A Logistic Regression model is instantiated and trained using the training data. The `LogisticRegression` model is configured with a `max_iter` parameter and a `random_state` parameter to control the randomness.

6. **Model Prediction:** The trained model makes predictions on the testing data, and the results are stored in a DataFrame, which is then displayed. This step helps evaluate how well the model performs.

7. **Model Evaluation:** The project calculates the balanced accuracy score for the model and displays it. The balanced accuracy score takes class imbalance into account.

8. **Confusion Matrix:** A confusion matrix is generated to provide a detailed breakdown of model performance. The confusion matrix helps visualize true positives, true negatives, false positives, and false negatives.

9. **Classification Report:** The classification report is printed, offering a more comprehensive evaluation of the model's performance, including precision, recall, and F1-score for each class.

10. **Class Imbalance Mitigation:** To address class imbalance, the project uses the Random OverSampler from the `imbalanced-learn` library. The resampled training data is used to retrain the Logistic Regression model.

11. **Model Evaluation with Oversampling:** The project calculates the balanced accuracy score for the model trained on the resampled data and displays it.

12. **Confusion Matrix with Oversampling:** A confusion matrix is generated for the model with oversampling to provide a detailed performance breakdown.

13. **Classification Report with Oversampling:** The classification report is printed for the model with oversampling, offering a comprehensive evaluation of its performance.

## Conclusion

With 100% precision, 99% accuracy, and 99% recall, this model performs very well in predicting healthy loans `0`; however, it performs somewhat worse when predicting high-risk loans `1`. With 102 false positives in this sample and an accuracy score of just 85%, it appears to be relatively prone to false positives in certain situations. At 91%, the recall score is also somewhat lower than for healthy loans, where the algorithm also discovered 56 erroneous negatives.

The second model now has considerably improved metrics with high-risk loans and performs as well with healthy loans as the original model did. The balanced accuracy score has improved generally from 95% to 99%, with the recall rising most noticeably from 91% to 99%. since a result, the accuracy dropped somewhat, from 85% to 84%, since our model in the test sample produced more false positives than our first model did. It discovered considerably fewer false negatives, which is partially expected when oversampling, but it is most likely the result of overfitting the minority class.

## Developer

[<img src="https://avatars.githubusercontent.com/u/133066908?v=4" width=115><br><sub>Ricardo De Los Rios</sub>](https://github.com/ricardodelosrios) 
