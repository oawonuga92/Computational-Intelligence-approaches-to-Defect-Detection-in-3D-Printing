# Computational-Intelligence-approaches-to-Defect-Detection-in-3D-Printing
In this work, a unique computational intelligence approach is used for defect defection in a multi-sensor FDM 3D printer. We decompose temperature and humidity data into residual components using STL decomposition. A subtraction technique is then used to reduce two series into one, by focusing directly on a "deviation from correlated behavior".
***********************
# Project Summary
Since 3D printing involves the use of sensors to monitor environmental conditions, the reliable detection of defects in the sensors is of great benefit in printing environments where stability in temperature and humidity conditions are crucial in getting good print outcomes. In this study, we develop a defect detection system using a CI approach based on the correlated behaviour of temperature and humidity sensor.
************************
# Dataset Acquisition and Description
The dataset used in this study is a privately acquired industry data from a company specializing in 3D printing and additive manufacturing. The dataset contains time-series data acquired by two sensor devices monitoring the ambient temperature and relative humidity. These sensors were installed on a FDM 3D printer. The data acquired by the humidity sensor device are clean and free from missing values, while the data acquired by the temperature sensor had missing values. 
- Linear interpolation was applied to generate missing temperature values.
- The total number of samples for each acquired sensor data was 600,000 which covers 35 days and 840 hours.
- Since the major challenge of anomaly detection is the availability of normal samples, we investigated the Numenta Anomaly Benchmark (NAB) real-world machine temperature sensor data to observe how genuine anomalies manifest in real-world streaming applications.
- In this work, constant values of varying intensities were injected into our temperature and humidity raw sensor data on random dates to simulate anomalies for defect detection. These anomalies are deviations from the normal sequence of temperature and humidity

