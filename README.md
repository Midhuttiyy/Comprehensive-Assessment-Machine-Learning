# Comprehensive-Assessment-Machine-Learning


## Data set : 

https://drive.google.com/file/d/1FHmYNLs9v0Enc-UExEMpitOFGsWvB2dP/view?usp=drive_link


## 1. Data Loading and Preprocessing:

Dataset: The dataset contains various car attributes and their prices. We load this dataset using pd.read_csv().

Preprocessing:

CarName: The CarName column includes both the brand and model. We extract the brand name by splitting the string at the first space.
Missing Data: We check for and remove any missing values.
Categorical Variables: For variables like fueltype, carbody, and drivewheel, we apply one-hot encoding using pd.get_dummies() to convert categorical data into numerical form.

## 2. Splitting the Data:

We split the data into features (X) and target (y), where the target is the car's price, and the features include other attributes.
The data is then split into training (80%) and testing (20%) sets using train_test_split().

## 3. Feature Scaling:

Many models (like SVR, Gradient Boosting) perform better when the features are on the same scale.
We use StandardScaler() to scale the features so that they have a mean of 0 and a standard deviation of 1.
Scaling is applied to both the training and testing sets.
## 4. Model Implementation:

Five regression models are implemented:
Linear Regression
Decision Tree Regressor
Random Forest Regressor
Gradient Boosting Regressor
Support Vector Regressor (SVR)
Each model is trained on the scaled training data.

## 5. Model Evaluation:

Performance Metrics: We evaluate the models on the test set using:
R² (R-squared): Measures how well the model explains the variability of the target variable.
Mean Squared Error (MSE): Measures the average squared difference between predicted and actual values.
Mean Absolute Error (MAE): Measures the average absolute difference between predicted and actual values.
A function evaluate_model() is used to compute these metrics for each model, and the results are printed out.
## 6. Feature Importance (Random Forest):

Random Forest Feature Importance: We extract and visualize the most important features that influence the car price, using RandomForestRegressor's feature_importances_ attribute. A bar plot is created to show which features are most impactful on car prices.
## 7. Hyperparameter Tuning (Random Forest):

GridSearchCV: To improve the Random Forest model's performance, we use Grid Search to optimize hyperparameters such as:
Number of trees (n_estimators)
Maximum depth of the trees (max_depth)
Minimum samples required to split a node (min_samples_split)
After finding the best hyperparameters, we evaluate the tuned Random Forest model on the test set to see if performance has improved.

Final Output:

The code provides clear output for:

The evaluation metrics (R², MSE, MAE) for all five models.
A plot showing the most important features from the Random Forest model.
The best hyperparameters for the Random Forest model and its updated performance after tuning.
