#### Overview
This project analyzes weather data to understand the factors influencing rain prediction for the next day. The analysis involves data preprocessing, visualization, and feature engineering to build a robust dataset for further machine learning modeling. The project demonstrates the implementation and evaluation of multiple machine learning classification models using different data sampling techniques. The models are trained on a dataset to predict target classes, and their performance is optimized using various hyperparameter tuning methods.


#### Requirements

- `pandas`
- `numpy`
- `matplotlib`
- `seaborn`
- `scikit-learn`

1. **Data Loading and Cleaning**
   - Remove irrelevant columns and handle missing values.
   - Separate numerical and categorical data for more efficient processing.

2. **Data Exploration and Visualization**
   - Plot histograms, KDE plots, and box plots to visualize the distribution of features.
   - Generate a correlation heatmap to identify highly correlated features.

3. **Feature Engineering**
   - Remove columns with high correlation to reduce multicollinearity.
   - Extract time-related features (year, month, day) from the `Date` column.
   - Encode categorical features into numerical representations.

5. **Outlier Detection and Removal**
   - Identify and handle outliers using interquartile range (IQR).

6. **Further Analysis and Visualization**
   - Visualize the target variable (`Rain the day after`) using a pie chart.
   - Perform PCA to visualize the distribution of the training data.

7. **Preprocessing**
- **Normalization:** Data is normalized using `MinMaxScaler` to bring all feature values to a range between 0 and 1.
- **Dimensionality Reduction:** Principal Component Analysis (PCA) is applied to reduce the dataset dimensions to 15 components.
- **Scaling:** Data is also standardized using `StandardScaler` for models that are sensitive to feature scales.

8. **Sampling Techniques**
- **Under-sampling:** Performed using `RandomUnderSampler` to handle class imbalance by reducing the size of the majority class.
- **Over-sampling:** Performed using Synthetic Minority Over-sampling Technique (SMOTE) to increase the size of the minority class.

9. **Models Implemented**
- **Decision Tree Classifier**: A tree-based model to classify data points by splitting the dataset into subsets based on the most significant attributes.
- **K-Nearest Neighbors (KNN)**: A distance-based classifier that assigns a class based on the majority class of the `k` closest neighbors.
- **Support Vector Machine (SVM)**: A powerful classifier that separates data points using hyperplanes.

10. **Hyperparameter Tuning**
- **Decision Tree Classifier**: Randomized Search with cross-validation to find the best combination of `max_depth`, `min_samples_split`, `min_samples_leaf`, `criterion`, and `ccp_alpha`.
- **K-Nearest Neighbors (KNN)**: Randomized Search with cross-validation to select the best `n_neighbors`, `weights`, and `metric`.
- **Support Vector Machine (SVM)**: Randomized Search with cross-validation for optimizing the `kernel`, `C`, and `gamma` parameters.

### Results
The models are evaluated using accuracy, precision, recall, and F1-score metrics. Below are the results for each model:

- **Decision Tree Classifier:**
  - **Without Sampling:**
    - Accuracy: 0.84
    - Precision (Class 0): 0.87, Recall (Class 0): 0.94, F1-score (Class 0): 0.90
    - Precision (Class 1): 0.70, Recall (Class 1): 0.51, F1-score (Class 1): 0.59
  - **Under-Sampling:**
    - Accuracy: 0.78
    - Precision (Class 0): 0.92, Recall (Class 0): 0.78, F1-score (Class 0): 0.84
    - Precision (Class 1): 0.50, Recall (Class 1): 0.77, F1-score (Class 1): 0.60
  - **Over-Sampling:**
    - Accuracy: 0.79
    - Precision (Class 0): 0.89, Recall (Class 0): 0.83, F1-score (Class 0): 0.86
    - Precision (Class 1): 0.52, Recall (Class 1): 0.66, F1-score (Class 1): 0.58

- **K-Nearest Neighbors (KNN):**
  - Accuracy after PCA and Hyperparameter Tuning: 0.79
  - Precision, Recall, F1-score for both classes are printed in the classification report.

- **Support Vector Machine (SVM):**
  - Accuracy after PCA and Hyperparameter Tuning: 0.84
  - Precision, Recall, F1-score for both classes are printed in the classification report.
