# Exploratory Data Analysis (EDA) for Time Series Prediction

---

## Load and Inspect Data

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

# Load data
data = pd.read_csv('data/raw/energydata_complete.csv')

# Basic Info
print('Shape of Data:', data.shape)
print('Column Names:', data.columns)
print('Data Types:\n', data.dtypes)

# Display first few rows
data.head()
```

---

## Handle Missing Values

Identify and handle missing values.

```python
# Check missing values
missing_values = data.isnull().sum()
print('Missing Values:\n', missing_values)

# Drop or Fill Missing Values (modify based on data)
data = data.dropna()  # Example of dropping missing rows
```

---

## Summary Statistics

```python
print('Summary Statistics:\n', data.describe())
```

---

## Date/Time Column

Ensure the dataset has a time-indexed column, convert to datetime format, and sort data.

```python
# Replace 'timestamp_column' with the actual name of your time column
data['date'] = pd.to_datetime(data['date'])
data = data.sort_values(by='date')
data.set_index('date', inplace=True)
```

---

## Visualize Target Variable

```python
target_column = 'Appliances'
plt.figure(figsize=(12, 6))
plt.plot(data[target_column], label='Target Variable')
plt.title('Target Variable Over Time')
plt.xlabel('Time')
plt.ylabel('Value')
plt.legend()
plt.show()
```

---

## Correlation Analysis

```python
correlation_matrix = data.corr()
plt.figure(figsize=(10, 8))
sns.heatmap(correlation_matrix, annot=True, cmap='coolwarm')
plt.title('Correlation Matrix')
plt.show()
```

---

## Check Stationarity

Evaluate stationarity using rolling mean and variance.

```python
rolling_mean = data[target_column].rolling(window=12).mean()
rolling_std = data[target_column].rolling(window=12).std()

plt.figure(figsize=(12, 6))
plt.plot(data[target_column], label='Original')
plt.plot(rolling_mean, label='Rolling Mean')
plt.plot(rolling_std, label='Rolling Std Dev')
plt.title('Rolling Mean & Standard Deviation')
plt.legend()
plt.show()
```

---

## AutoCorrelation

Analyze autocorrelations and partial autocorrelations to detect dependencies.

```python
from statsmodels.graphics.tsaplots import plot_acf, plot_pacf

plot_acf(data[target_column], lags=50)
plt.title('Autocorrelation Function')
plt.show()

plot_pacf(data[target_column], lags=50)
plt.title('Partial Autocorrelation Function')
plt.show()
```

---

## Feature Engineering

Create additional features like hour, day, month, and weekday for modeling.

```python
# Example: Creating time-based features
data['hour'] = data.index.hour
data['day'] = data.index.day
data['month'] = data.index.month
data['weekday'] = data.index.weekday

# Display processed data
print(data.head())
```
