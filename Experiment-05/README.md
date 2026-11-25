# Experiment 5: IoT Sensor Data Analysis Using NumPy

## Aim
To analyze IoT sensor readings using NumPy arrays and perform mathematical and statistical operations such as mean, median, minimum, maximum, standard deviation, and threshold analysis.

## Algorithm
1. Start the program.
2. Create a NumPy array containing IoT sensor readings.
3. Calculate the mean, median, minimum, and maximum values.
4. Calculate the standard deviation.
5. Apply a threshold to identify high sensor readings.
6. Display all statistical results.
7. Stop the program.

## Program
See [iot_sensor_analysis.py](iot_sensor_analysis.py)

```python
# IoT Sensor Data Analysis using NumPy
import numpy as np

sensor_data = np.array([24.5, 25.1, 26.3, 27.0, 28.2,
                        29.1, 27.8, 26.5, 25.7, 30.2])

print("Sensor Data:", sensor_data)
print("Mean :", round(np.mean(sensor_data), 2))
print("Median :", round(np.median(sensor_data), 2))
print("Minimum :", np.min(sensor_data))
print("Maximum :", np.max(sensor_data))
print("Std. Dev. :", round(np.std(sensor_data), 2))

threshold = 28.0
high_values = sensor_data[sensor_data > threshold]
print("Values above", threshold, ":", high_values)
```

## Output
See [output.txt](output.txt)

```
Sensor Data: [24.5 25.1 26.3 27.  28.2 29.1 27.8 26.5 25.7 30.2]
Mean : 27.04
Median : 26.75
Minimum : 24.5
Maximum : 30.2
Std. Dev. : 1.77
Values above 28.0 : [28.2 29.1 30.2]
```

## Result
Thus, IoT sensor data was represented using NumPy arrays and mathematical and statistical operations were performed successfully.
