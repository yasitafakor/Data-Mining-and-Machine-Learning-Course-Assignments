# Employee Absence Analysis

This project focuses on analyzing employee absence data to identify key trends and insights. The analysis involves data cleaning, transformation, and exploratory data analysis (EDA) using Python and popular libraries such as pandas, matplotlib, and seaborn.

## Overview

The project aims to analyze and visualize employee absence data to identify the most common reasons for absence and to categorize employees based on various factors, such as age, smoking and drinking habits, transportation expenses, and more.

## Data Preprocessing

1. **Load the Dataset**: Load the dataset from an Excel file using `pandas`.
2. **Data Cleaning**:
   - Remove duplicate records.
   - Drop unnecessary columns (e.g., `Employee_ID`).
   - Convert the `Date` column to datetime format and extract year, month, and weekday.
   - Encode categorical data into readable labels for better understanding.
3. **Categorical Conversion**: Convert several numeric columns into categorical labels, such as:
   - Education levels (e.g., high school, graduate, etc.)
   - Binary columns (e.g., Yes/No fields like `Disciplinary_Incident`).

## Exploratory Data Analysis (EDA)

1. **Percentage Analysis**:
   - Calculate the percentage of absences from alcohol consumers and smokers.
   - Determine the most frequent absence reasons among alcohol consumers and non-alcohol consumers.

2. **Distribution Analysis**:
   - Visualize the distribution of absent hours among different groups (alcohol consumers, non-alcohol consumers, smokers, and non-smokers).
   - Analyze the impact of distance to work and transportation expenses on absence duration.

3. **Correlation Analysis**:
   - Generate a correlation matrix to identify relationships between numeric features.

4. **Age Analysis**:
   - Study the distribution, skewness, mean, median, and mode of employee ages.
   - Investigate the relationship between age, disease occurrence, and absence duration.

5. **Impact of Other Factors**:
   - Analyze how factors such as education level, weekday, and month affect absence duration.

## Dependencies

To run the analysis, the following Python libraries are required:

- pandas
- matplotlib
- seaborn
- scipy

### Results

- **Top Reasons for Absences**: Most frequent reasons are "medical consultation", "dental consultation", and "physiotherapy".

- **Alcohol and Smoking Effects**:
  - Alcohol consumers and smokers generally have longer absences compared to non-consumers.
  - Certain absence reasons (e.g., dental consultation) are significantly more common among alcohol consumers.

- **Distance and Transportation**:
  - No significant link between "Distance to Work" and absences.
  - Higher "Transportation Expense" correlates with longer absences.

- **Correlation Insights**:
  - Strong links between age, BMI, disease, and absence duration.

- **Age and Education**:
  - Older employees (50-60) have the most absences.
  - Higher education levels correspond to fewer absences.

- **Other Factors**:
  - Most absences occur on Mondays, Saturdays, and in specific months (March, April, June, July, December).
  - More children generally lead to more absences.

