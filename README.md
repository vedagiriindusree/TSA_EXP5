# Ex.No: 05  IMPLEMENTATION OF TIME SERIES ANALYSIS AND DECOMPOSITION
### Date: 30.09.2025
### Name:Vedagiri Indu Sree
### Reg No:212223230236
### AIM:
To Illustrates how to perform time series analysis and decomposition on the monthly average temperature of a city/country and for airline passengers.

### ALGORITHM:
1. Import the required packages like pandas and numpy
2. Read the data using the pandas
3. Perform the decomposition process for the required data.
4. Plot the data according to need, either seasonal_decomposition or trend plot.
5. Display the overall results.

### PROGRAM:
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from statsmodels.tsa.seasonal import seasonal_decompose

# Step 1: Load the dataset,Convert 'date' column to datetime format,Set it as index
data = pd.read_csv('tsla_2014_2023.csv', parse_dates=['date'], index_col='date')

# Step 2: Perform seasonal decomposition using the 'close' column
# Using period=5 for weekly seasonality (5 trading days)
decomposition = seasonal_decompose(data['close'], model='additive', period=5)

# Step 3: Plot the decomposition
plt.figure(figsize=(10, 12))

# Original Data
plt.subplot(411)
plt.plot(data['close'], label='TSLA Close Price')
plt.legend(loc='upper left')
plt.title('Original Time series data: TSLA Close Price')

# Trend Plot
plt.subplot(412)
plt.plot(decomposition.trend, label='Trend', color='orange')
plt.legend(loc='upper left')
plt.title('Linear Trend plot')

# Seasonal Plot
plt.subplot(413)
plt.plot(decomposition.seasonal, label='Seasonal', color='green')
plt.legend(loc='upper left')
plt.title('Seasonality plot')

# Residual Plot
plt.subplot(414)
plt.plot(decomposition.resid, label='Residual', color='red')
plt.legend(loc='upper left')
plt.title('Residual plot')

plt.tight_layout()
plt.show()
```

### OUTPUT:
FIRST FIVE ROWS:
<img width="2585" height="780" alt="image" src="https://github.com/user-attachments/assets/2876ad76-5fa5-4c21-919e-4a918eea2a5d" />

PLOTTING THE DATA:
ORIGINAL TIME SERIES DATA:
<img width="1978" height="594" alt="image" src="https://github.com/user-attachments/assets/f373720f-077a-4aac-b662-6d72a3b53d73" />

SEASONAL PLOT REPRESENTATION :
<img width="1974" height="601" alt="image" src="https://github.com/user-attachments/assets/69c62014-7a8c-41c1-b44f-14cc52d8c471" />


LINEAR TREND PLOT REPRESENTATION :
<img width="1962" height="594" alt="image" src="https://github.com/user-attachments/assets/7b60f50b-32a8-4044-8128-ec9c99b1ac29" />

RESIDUAL PLOT REPRESENTATION:
<img width="1974" height="590" alt="image" src="https://github.com/user-attachments/assets/825caeb1-ee0c-4d28-a59c-701ea51fe38c" />


### RESULT:
Thus we have created the python code for the time series analysis and decomposition.
