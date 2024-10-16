# Ex.No: 05  IMPLEMENTATION OF TIME SERIES ANALYSIS AND DECOMPOSITION
### Date: 
# Developed by: ANUSHARON.S
# Register no.: 212222240010


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

temperature_data = pd.Series([30, 31, 32, 33, 34, 35, 34, 33, 32, 31, 30, 29, 28, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37],
                             index=pd.date_range(start='2022-01-01', periods=24, freq='M'))

airline_passenger_data = pd.Series([112, 118, 132, 129, 121, 135, 148, 148, 136, 119, 104, 118,
                                    115, 126, 141, 135, 125, 149, 170, 170, 158, 133, 114, 140],
                                    index=pd.date_range(start='2022-01-01', periods=24, freq='M'))

decomposed_temperature = seasonal_decompose(temperature_data, model='additive', period=12)
decomposed_passengers = seasonal_decompose(airline_passenger_data, model='multiplicative', period=12)

print("First five rows of Temperature Data:")
print(temperature_data.head(), "\n")

print("First five rows of Airline Passenger Data:")
print(airline_passenger_data.head(), "\n")


plt.figure(figsize=(12, 8))
plt.subplot(411)
plt.plot(temperature_data, label='Original Temperature Data')
plt.legend(loc='best')

plt.subplot(412)
plt.plot(decomposed_temperature.trend, label='Trend')
plt.legend(loc='best')

plt.subplot(413)
plt.plot(decomposed_temperature.seasonal, label='Seasonality')
plt.legend(loc='best')

plt.subplot(414)
plt.plot(decomposed_temperature.resid, label='Residuals')
plt.legend(loc='best')

plt.tight_layout()
plt.show()


plt.figure(figsize=(12, 8))
plt.subplot(411)
plt.plot(airline_passenger_data, label='Original Airline Data')
plt.legend(loc='best')

plt.subplot(412)
plt.plot(decomposed_passengers.trend, label='Trend')
plt.legend(loc='best')

plt.subplot(413)
plt.plot(decomposed_passengers.seasonal, label='Seasonality')
plt.legend(loc='best')

plt.subplot(414)
plt.plot(decomposed_passengers.resid, label='Residuals')
plt.legend(loc='best')

plt.tight_layout()
plt.show()
```

### OUTPUT:
# FIRST FIVE ROWS:


![Screenshot 2024-10-16 124141](https://github.com/user-attachments/assets/2d9641d8-cbb2-41ec-9f94-2381808a369c)



# PLOTTING THE DATA:


SEASONAL PLOT REPRESENTATION :

![Screenshot 2024-10-16 124232](https://github.com/user-attachments/assets/e769621f-1d9b-42f8-889b-97fe8071a33d)


TREND PLOT REPRESENTATION :
![Screenshot 2024-10-16 124259](https://github.com/user-attachments/assets/86cfa2ff-1150-4224-9274-ef23bd6cd665)


OVERAL REPRESENTATION:

![Screenshot 2024-10-16 124418](https://github.com/user-attachments/assets/5d4feba9-0e45-47e3-bb23-51ff0aa724bd)


### RESULT:
Thus we have created the python code for the time series analysis and decomposition.
