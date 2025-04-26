# Netflix Movies and TV Shows Dataset — Data Cleaning & Preprocessing Process
# 📌 Objective
To clean and preprocess the Netflix Movies and TV Shows dataset, making it suitable for meaningful analysis and potential machine learning tasks by addressing missing values, duplicate records, outliers, categorical data, and feature scaling — while carefully justifying every decision taken.

# 📌 Data Cleaning & Preprocessing Steps
# 1️. Handling Missing Values
**Observation:**

The dataset contained missing values in several columns, notably in director, country, date_added, and rating.


**Actions & Justifications:**
+ For 'country': Missing values were filled with the most frequent value (mode) because 'country' is a categorical feature, and imputing with the most common value maintains consistency without introducing bias.
+ For 'director': Instead of deleting this column (to retain all possible information), missing values were filled with the label 'Unknown'. This ensures no data loss while clearly indicating unavailable information.
+ For 'date_added' and 'rating': Since these fields are essential for temporal and content rating analyses, any rows missing this information were removed. This preserves the reliability of future analyses that rely on these features.

# 2️. Removing Duplicate Records
**Observation:**

Duplicate entries were found in the dataset.

**Actions & Justifications:**

Duplicate records were removed to prevent skewed analysis and redundancy. Retaining duplicates could result in biased summary statistics and misleading insights, especially when analyzing distributions and trends.

# 3️. Detecting and Handling Outliers
**Observation:**

By examining the release_year feature, it was found that some entries had values lower than 1900 and higher than 2025, which are unrealistic for Netflix content.

**Actions & Justifications:**

Outliers were removed by eliminating rows with release years outside the valid range (1900–2025). This decision ensures the accuracy of year-based analysis and avoids distortion in statistical summaries and visualizations caused by anomalous values.

![alt img](https://github.com/Engr-Usman-Ali/Data_Cleaning_And_Preprocessing_Task/blob/a14947a5187553d3211347d11cc301e3d278b4a5/BoxPlot.png)


# 4️. Encoding Categorical Variables
**Observation:**

The dataset contained categorical variables such as type (Movie/TV Show) and rating (TV-MA, PG, etc.) that needed to be converted into numerical formats for analysis and modeling.

**Actions & Justifications:**

- For 'type': Label Encoding was applied, assigning numeric values (Movie → 0, TV Show → 1). This is appropriate for binary categorical variables.

- For 'rating': One-Hot Encoding was used, converting each unique rating category into a separate binary column. This avoids any assumption of ordinal relationship between ratings and ensures compatibility with algorithms that require numerical input.

# 5️. Normalizing / Standardizing Numerical Features
**Observation:**

The release_year feature had a wide range of values and needed to be scaled.

**Actions & Justifications:**

StandardScaler was applied to standardize release_year values, transforming them to have a mean of 0 and a standard deviation of 1. Standardization is crucial for algorithms sensitive to feature scaling, ensuring that all numerical variables contribute equally to distance-based analyses or model performance.

# 📌 Final Outcome
After completing the above steps:
+ All essential missing values were addressed without deleting any columns.
+ Duplicate records were removed.
+ Unrealistic outliers in release_year were handled.
+ Categorical variables were encoded appropriately.
+ Numerical features were scaled for better compatibility with analysis and modeling tools.

The dataset was successfully cleaned and transformed, making it reliable and ready for detailed exploratory analysis and machine learning applications.

