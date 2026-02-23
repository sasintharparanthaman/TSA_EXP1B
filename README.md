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
<img width="1666" height="285" alt="Screenshot 2026-02-23 134651" src="https://github.com/user-attachments/assets/c27d2355-934f-4ae9-956a-99d53802b021" />


REGULAR DIFFERENCING:

<img width="749" height="138" alt="Screenshot 2026-02-23 134700" src="https://github.com/user-attachments/assets/4cb2df83-a273-4049-bf83-88fb91a00b7e" />


SEASONAL ADJUSTMENT:

<img width="777" height="135" alt="Screenshot 2026-02-23 134802" src="https://github.com/user-attachments/assets/deca82ef-1084-4c7d-bfbd-3a4708a3eae0" />


LOG TRANSFORMATION:

<img width="764" height="144" alt="Screenshot 2026-02-23 134810" src="https://github.com/user-attachments/assets/cbbffba0-a8e1-4f51-b611-ee85aa9c6b6e" />


LOG AND REGULAR:

<img width="693" height="127" alt="Screenshot 2026-02-23 134816" src="https://github.com/user-attachments/assets/6a63a7f1-8627-4848-a00f-295280be97dd" />

LOG+REGULAR+SEASONAL:


<img width="830" height="135" alt="Screenshot 2026-02-23 134824" src="https://github.com/user-attachments/assets/eb0259b2-5c02-4f69-8114-cc8bdf4a0887" />



### RESULT:
Thus we have created the python code for the conversion of non stationary to stationary data on international airline passenger
data.
