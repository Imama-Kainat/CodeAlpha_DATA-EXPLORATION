# CodeAlpha_DATA-EXPLORATION
2nd Task of data Science Internship codealpha


# Exploring the Iris Dataset: A Python Data Visualization Example
![image](https://github.com/Imama-Kainat/CodeAlpha_DATA-EXPLORATION/assets/140218008/68babf38-32e4-4817-975f-4db77a2dd15f)


## Introduction:

In this example, I will walk through a Python code snippet that explores the famous Iris dataset using data visualization techniques. The Iris dataset contains measurements of iris flowers, and our goal is to gain insights into the relationships between different features and the distribution of these features across different species of iris flowers.

## Code Overview:

```python
# Import necessary libraries
from sklearn.datasets import load_iris
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

# Load Iris dataset
iris = load_iris()

# Convert to DataFrame for better exploration
iris_df = pd.DataFrame(data=iris.data, columns=iris.feature_names)
iris_df['target'] = iris.target  # Adding target column

# Display the first few rows of the dataset
print(iris_df.head())

# Check for missing values
print(iris_df.isnull().sum())

# Pairplot to visualize relationships between features
sns.pairplot(iris_df, hue='target', palette='viridis')
plt.show()

# Boxplot to visualize the distribution of each feature
plt.figure(figsize=(12, 6))
for i, feature in enumerate(iris.feature_names):
    plt.subplot(2, 2, i+1)
    sns.boxplot(x='target', y=feature, data=iris_df, hue='target', palette='viridis', legend=False)
plt.show()
```

## Explanation:

### 1. Loading and Structuring the Data:

- **Importing Libraries:** We start by importing necessary libraries including scikit-learn for dataset access, Pandas for data manipulation, Seaborn for statistical data visualization, and Matplotlib for additional plotting capabilities.

- **Loading Dataset:** The Iris dataset is loaded using `load_iris()` from scikit-learn.

- **Data Structure:** The dataset is converted into a Pandas DataFrame (`iris_df`) for better exploration. The 'target' column is added to represent the species of each iris flower.

### 2. Data Exploration:

- **Checking Missing Values:** We use `print(iris_df.isnull().sum())` to check for missing values in the dataset.

### 3. Visualizing Relationships:

- **Pairplot:** The relationships between pairs of features are visualized using `sns.pairplot()`. Each point in the scatterplots is color-coded based on the species (target).

### 4. Visualizing Feature Distributions:

- **Boxplots:** Boxplots are created to visualize the distribution of each feature for different species. The code utilizes subplots to organize the boxplots in a 2x2 grid.

## Conclusion:

This Python code provides a comprehensive exploration of the Iris dataset, offering insights into feature relationships and distributions. The visualizations aid in understanding patterns and differences between iris species.


