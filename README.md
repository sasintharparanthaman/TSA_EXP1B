# Ex.No: 1B                     CONVERSION OF NON STATIONARY TO STATIONARY DATA
# Date: 23-02-2026

### AIM:
To perform regular differncing,seasonal adjustment and log transformatio on international airline passenger data
### ALGORITHM:
1. Import the required packages like pandas and numpy
2. Read the data using the pandas
3. Perform the data preprocessing if needed and apply regular differncing,seasonal adjustment,log transformation.
4. Plot the data according to need, before and after regular differncing,seasonal adjustment,log transformation.
5. Display the overall results.
### PROGRAM:
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
df['Date'] = pd.to_datetime(df['Date'], errors='coerce')
df.set_index('Date', inplace=True)

print(type(df.index))  # Should show DatetimeIndex
df.head()
plt.figure(figsize=(12,6))
plt.plot(df['Volume'])
plt.title("Original Time Series (Volume)")
plt.xlabel("Date")
plt.ylabel("Volume")
plt.grid(True)
plt.show()
df['Diff_Volume'] = df['Volume'].diff()

plt.figure(figsize=(12,6))
plt.plot(df['Diff_Volume'])
plt.title("Regular Differencing (1st Order)")
plt.xlabel("Date")
plt.ylabel("Differenced Volume")
plt.grid(True)
plt.show()
df['Seasonal_Diff_Volume'] = df['Volume'].diff(12)

plt.figure(figsize=(12,6))
plt.plot(df['Seasonal_Diff_Volume'])
plt.title("Seasonal Differencing (Lag = 12)")
plt.xlabel("Date")
plt.ylabel("Seasonally Differenced Volume")
plt.grid(True)
plt.show()
df['Log_Volume'] = np.log(df['Volume'])

plt.figure(figsize=(12,6))
plt.plot(df['Log_Volume'])
plt.title("Log Transformed Volume")
plt.xlabel("Date")
plt.ylabel("Log(Volume)")
plt.grid(True)
plt.show()
df['Log_Diff'] = df['Log_Volume'].diff()

plt.figure(figsize=(12,6))
plt.plot(df['Log_Diff'])
plt.title("Log Transformation + Regular Differencing")
plt.xlabel("Date")
plt.ylabel("Differenced Log Volume")
plt.grid(True)
plt.show()
df['Seasonal_Diff'] = df['Log_Diff'].diff(12)

plt.figure(figsize=(12,6))
plt.plot(df['Seasonal_Diff'])
plt.title("Log + Regular + Seasonal Differencing (Lag=12)")
plt.xlabel("Date")
plt.ylabel("Seasonally Differenced")
plt.grid(True)
plt.show()
```



### OUTPUT:


ORIGINAL:
<img width="1001" height="547" alt="orig" src="https://github.com/user-attachments/assets/6588a29c-0066-4c8e-bbff-cb2a4422790d" />


REGULAR DIFFERENCING:

<img width="999" height="547" alt="regu" src="https://github.com/user-attachments/assets/bd44e7bb-e994-4276-96ef-bd740df17df8" />

SEASONAL ADJUSTMENT:

<img width="999" height="547" alt="seas" src="https://github.com/user-attachments/assets/3ff1c9f0-8081-4602-95e9-35088fde7979" />

LOG TRANSFORMATION:
<img width="997" height="547" alt="log" src="https://github.com/user-attachments/assets/a31a9a81-ae7a-4b34-93b1-f697947a9831" />


LOG AND REGULAR:
<img width="999" height="547" alt="log+reg" src="https://github.com/user-attachments/assets/a15e9162-ae9b-45c9-a2b3-ff378219888b" />


LOG+REGULAR+SEASONAL:
<img width="999" height="547" alt="log+reg+seas" src="https://github.com/user-attachments/assets/8165414b-b293-46c7-828a-26daca706f73" />





### RESULT:
Thus we have created the python code for the conversion of non stationary to stationary data on international airline passenger
data.
