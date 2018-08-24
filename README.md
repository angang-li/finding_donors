# Finding Donors

## Problem to solve

There is a fictitious charity seeking people who make more than $50,000 annually as potential donors. The goal is to build a supervised learning model to best identify potential donors and reduce overhead cost of sending mail.

## Available data

1994 U.S. Census data with 13 features and ~32,000 data points. This dataset was provided by the Nanodegree program. This dataset is a modified version of the dataset published in the paper *"Scaling Up the Accuracy of Naive-Bayes Classifiers: a Decision-Tree Hybrid",* by Ron Kohavi. Here is the paper [online](https://www.aaai.org/Papers/KDD/1996/KDD96-033.pdf), with the original dataset hosted on [UCI](https://archive.ics.uci.edu/ml/datasets/Census+Income).

## What I did

1. Data exploration and data preprocessing

    - Find that income class was skewed, 25% earning >= $50,000
    - Transform skewed continuous features
    - Normalize numerical features
    - Convert categorical features
    - Shuffle and split data into training and testing

2. Employ 3 supervised learning algorithms to classify individuals' income using census data

    - Define metrics (F0.5 score)
    - Examine naïve predictor's performance
    - Choose 3 supervised learning algorithms (AdaBoost, Random Forest, Gradient Boosting) that work well with continuous and binary dataset
    - Create training and predicting pipeline
    - Evaluate the performance if 3 algorithms by examining learning curves and time for training and prediction.

3. Choose the best algorithm based on preliminary results to further optimize this algorithm

    - Choose AdaBoost as the best candidate algorithm for its high predictive power and fast speed
    - Perform a grid search cross validation to tune hyperparameters to optimize F-score
    - Evaluate the optimized model on test set
    - Extract feature importance, i.e., top-5 most predictive features

## Results

- Trained AdaBoost model reaches 87% testing accuracy
- There is only ~1%-3% decrease in F-score when using only the top-5 most predictive features

## What I learnt

- If training time is a concern, I will consider using the reduced data as the training set, because reduced data require less training time but still perform reasonably well. 

## How to run the code

1. Clone this repository
2. In a terminal or command window, navigate to the directory `finding_donors/code/` and run the following commands:

    ```bash
    jupyter notebook finding_donors.ipynb
    ```

    This will open the iPython Notebook software and project file in the browser.
