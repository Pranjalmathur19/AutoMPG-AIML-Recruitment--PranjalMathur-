[README(1).md](https://github.com/user-attachments/files/32699500/README.1.md)
# Auto MPG — EDA, Cleaning & Linear Regression

Coding Ninjas 10X — AI/ML Recruitment Task (First Years)

## Candidate Details
- Name: [Pranjal Mathur]
- Year / Branch: [CSE CORE]

## Tasks Completed
- Task 1: Exploratory Data Analysis & Preprocessing
- Task 2: Linear Regression

## Problem Statement
The goal was to understand and clean the Auto MPG dataset, explore what actually drives a car's fuel efficiency, and then build a Linear Regression model that predicts `mpg` from a car's characteristics (weight, horsepower, displacement, cylinders, acceleration, model year, and origin).

## Approach
1. Loaded the Auto MPG dataset and checked its structure, data types, and missing values.
2. Found 6 missing `horsepower` values and imputed them using the median horsepower within each cylinder group, since horsepower correlates strongly with cylinder count — more accurate than a flat median.
3. Explored the distribution of `mpg` and other numeric features, and looked at how `mpg` relates to weight, horsepower, displacement, cylinders, origin, and model year using scatter plots, box plots, and a correlation heatmap.
4. Investigated a high-horsepower outlier and confirmed it was a legitimate data point rather than an error, so kept it in.
5. Asked an additional question — whether fuel efficiency improved over the years in the dataset — and confirmed a clear upward trend, likely tied to the 1973 oil crisis pushing efficiency standards.
6. Cleaned and exported the dataset, then used it to train a Linear Regression model: first a single-feature model (weight only), then a multi-feature model using all relevant variables.
7. Evaluated both models using MAE, MSE, RMSE, and R², compared train vs test performance to check for overfitting/underfitting, and visualized actual vs predicted mpg.

## Technologies Used
- Python
- pandas, numpy
- matplotlib, seaborn
- scikit-learn (LinearRegression, train_test_split, metrics)
- Google Colab

## Results
- Multi-feature Linear Regression model achieved an R² of roughly 0.8+ on the test set (see notebook for exact values).
- `weight` was the single strongest predictor of `mpg`.
- Train and test performance were close, indicating the model wasn't significantly overfitting — though the linear model shows some underfitting since the true mpg-vs-weight/horsepower relationship is curved, not linear.

## Key Learnings
1. Imputing missing values thoughtfully (e.g. grouped by a related feature) can be more meaningful than a blanket median or mean fill.
2. Multicollinearity between features like weight, displacement, and horsepower makes individual regression coefficients harder to interpret — they aren't fully independent effects.
3. A model's train vs test metrics being close is what actually tells you whether it's overfitting, not just how good the test score looks in isolation.

## Challenges
The relationship between `mpg` and features like weight/horsepower turned out to be curved rather than linear, which capped how well a plain Linear Regression model could fit the data. I addressed this by acknowledging it directly in the analysis (rather than ignoring it) and suggesting polynomial regression or a tree-based model as a next step to better capture the non-linearity.
