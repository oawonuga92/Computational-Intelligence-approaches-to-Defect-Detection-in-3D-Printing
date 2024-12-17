# Computational-Intelligence-approaches-to-Defect-Detection-in-3D-Printing
In this work, a unique computational intelligence (CI) approach is used for defect defection in a multi-sensor FDM 3D printer. We decompose temperature and humidity data into residual components using STL decomposition. A subtraction technique is then used to reduce two series into one, by focusing directly on a "deviation from correlated behavior".
***********************
# Project Summary
Since 3D printing involves the use of sensors to monitor environmental conditions, the reliable detection of defects in the sensors is of great benefit in printing environments where stability in temperature and humidity conditions are crucial in getting good print outcomes. In this study, we develop a defect detection system using a CI approach based on the correlated behaviour of temperature and humidity sensor.
************************
# Dataset Acquisition and Description
The dataset used in this study is a privately acquired industry data from a company specializing in 3D printing and additive manufacturing. The dataset contains time-series data acquired by two sensor devices monitoring the ambient temperature and relative humidity. These sensors were installed on a FDM 3D printer. The data acquired by the humidity sensor device are clean and free from missing values, while the data acquired by the temperature sensor had missing values. 
- Linear interpolation was applied to generate missing temperature values.
- The total number of samples for each acquired sensor data was 600,000 which covers 35 days and 840 hours.
- Since the major challenge of anomaly detection is the availability of normal samples, we investigated the Numenta Anomaly Benchmark (NAB) real-world machine temperature sensor data to observe how genuine anomalies manifest in real-world streaming applications.
- Mimicing artificial labelling of anomalous dataset in NAB, constant values of varying intensities were injected into our temperature and humidity raw sensor data on random dates to simulate anomalies for defect detection.
- These synthetic anomalies injected into the dataset for this study are deviations from the normal sequence of temperature and humidity
******************
# Methodology
1. Time Series Decomposition using STL : The time series was decomposed using the Seasonal-Trend with Loess (STL) algorithm which applies Locally Estimated Scatterplot Smoothing (LOESS) to remove the trend and seasonality components, leaving out the residual components as the extracted feature for anomaly detection. The large spikes in residual components deviating from the normal behavioural pattern of the time series are obvious anomalies. However, the amplitude weight of the residual components was used as the basis for separating normal conditions from anomalous events using a subtraction technique.
2. Subtraction of Residual Components: we created a new feature representing the joint correlated feature of temperature and humidity.  This Z feature effectively reduces two time series into one, by focusing directly on the relationship between the temperature and relative humidity.
*************************
# Results
We conduct performance comparisons of Five selected unsupervised methods in detecting anomalies using our proposed CI approach for the feature extraction. The input data is the Z feature (i.e., the joint correlated feature of the residual components of temperature and humidity). Reference labels were generated for Z feature to determine how accurately the model predicted a defect in comparison to the reference label.
- 5 unsupervised anomaly detection models are : OneClass SVM, Isolation Forest, Kmeans, ARIMA, and LSTM Auto Encoder.
- In comparing machine learning methods with conventional ARIMA methods, there was over 30% improvement in recall for machine learning models – kmeans, Isolation Forest, and OneClass SVM.
- There was 50% improvement in recall for deep neural networks.
- Overall, there was an average precision and F1-score of 80% when applying machine learning and deep learning models with our proposed CI approach
********************
# Conclusion
This research is funded by Innovate UK under the Smart Manufacturing Data Hub project. The data is a privately acquired and hence it cannot be shared due to data provacy and confidentiality. Howvever, the source codes for each model can be used on any public data



