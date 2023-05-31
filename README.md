# Demographic Data Analyser
This is a project from FreeCodeCamp that aims to analyze a certain demographic to obtain crucial information about the demographic. The project involves the use of various Python libraries for data analysis.

## Prerequisites
Before running the project, ensure that the following libraries are installed:

- pandas
- numpy

## Usage
- Import the required libraries:
```
import pandas as pd
import numpy as np
```
- Load the dataset:
```
df = pd.read_csv('adult.data.csv')
```
Explore the dataset:
```
# Display the dataset
print(df)

# Check general information about the dataset
df.info()

# Check for duplicates
duplicates = df[df.duplicated()]
print(duplicates)

# Check for wrong data types
value_types = {
    'int64': int,
    'object': str,
    'float64': float
}
wrong_data_types = {}
for column in df.columns:
    wrong_data_types[column] = [x for x in df[column] if type(x) != value_types[str(df[column].dtypes)]]
print(wrong_data_types)
```
## Perform Exploratory Data Analysis:
```
# Question 1: How many people of each race are represented in this dataset?
race_counts = df['race'].value_counts()
print(race_counts)

# Question 2: What is the average age of men in our database?
average_age_men = df.loc[df['sex'] == 'Male', 'age'].mean()
print(average_age_men)
```
## Conclusion
This project provides a basic framework for analyzing demographic data. It demonstrates how to load the data, check for duplicates and wrong data types, and perform exploratory data analysis to answer specific questions. Feel free to modify and extend the code to suit your specific needs.