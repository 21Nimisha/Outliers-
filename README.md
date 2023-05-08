# Outliers-
All Techniques to remove Outliers


What is "OUTLIERS"
In statistics, an outlier is an observation point that is significantly different from other observations in a dataset. An outlier may be due to variability in the measurement or it may indicate experimental error. Outliers can have a disproportionate effect on statistical analysis, such as the mean, which can be skewed by their presence. Therefore, it is important to identify and handle outliers appropriately when analyzing data.

Effect of Outliers on ML Algorithms
Outlier can impact on machine learning model like Linear, Logistic regression , Decision Tree,SVM, Adaboost, Deep learning,also on weight based algorithm effected mostly with outliers

Linear Regression: Outliers can have a big impact on the slope and intercept of the regression line. This can result in a poor fit of the model to the data.

Decision Trees: Decision Trees can be affected by outliers, as they tend to split the data based on the highest information gain. Outliers can have a large information gain and can lead to the tree splitting in an unexpected way.

SVM: SVMs are sensitive to outliers, as they try to maximize the margin between the decision boundary and the support vectors. Outliers can push the boundary away from the majority of the data points, leading to a poor classification performance.

K-Nearest Neighbors: Outliers can have a big impact on the KNN algorithm, as it relies heavily on the distance between points. Outliers can have a large distance from the other points and can result in a poor classification performance.

In general, it is always a good practice to identify and handle outliers in the data before applying machine learning algorithms. This can be done using various techniques such as Winsorization, trimming, or removing the outliers altogether.

When is outlier dangerous?
Outliers can be dangerous in certain scenarios because they can significantly impact the results of statistical analyses, leading to incorrect conclusions. In some cases, outliers may indicate errors or anomalies in the data collection process, which can affect the validity and reliability of the results. For example, in finance, outliers in stock prices could indicate a data error or a sudden event that caused a significant change in the market.

Moreover, in predictive modeling, outliers can lead to overfitting of the model, which means that the model may perform well on the training data but poorly on the test data. This can be a serious problem if the model is used to make important decisions, such as in medical diagnosis or financial forecasting. In such cases, it is important to identify and remove the outliers or use robust statistical methods that can handle the presence of outliers.

How to treat Outliers?
There are several methods to treat outliers in a dataset. Some of the common methods are:

Removing outliers/ Trimming:

completely remove the outliered data
its fast but effect on data distribution This method involves removing the data points that are identified as outliers from the dataset. However, this method should be used with caution as it can lead to loss of information and affect the overall analysis.
Trimming

Remove the outliers from the dataset before training a machine learning model. E.g., Remove the students from the dataset in the above example.
Trimming is a method of treating outliers that involves removing the extreme values from the dataset. In trimming, a certain percentage of the data is removed from both the tails of the distribution, based on a predetermined cutoff value. For example, if a 10% trim is chosen, the top and bottom 5% of the data are removed.
Trimming is a simple and quick method of outlier treatment, but it has the disadvantage of potentially losing valuable information in the removed data. It also does not change the values of the remaining data points, so the distribution and statistical properties of the remaining data may still be affected by the presence of outliers. Therefore, trimming is usually only used in situations where the outlier is clearly an error or artifact of the data collection process.

Capping

outlier can be on lower or upper side of data.

can apply capping on data upper and lower side to identify outlier.

Keep a maximum or minimum threshold and give values to the data points accordingly. E.g., if we are working on the age feature, we can keep the threshold of 85 and assign the value of 85 to all the people with age greater than 85.

Capping, also known as clipping, is a method for treating outliers by replacing extreme values with a less extreme but still plausible value. In this method, any data point that exceeds a certain threshold is replaced with the value of that threshold.

For example, if we have a dataset of house prices and we observe a few extreme values that are much higher than the rest of the data, we can use capping to replace those extreme values with a more reasonable value. If we set the cap at the 99th percentile of the data, any value above that percentile would be replaced with the value at the 99th percentile.

Capping can be done in two ways:

Hard capping: -This method involves setting an upper and lower limit for the values. Any value above the upper limit or below the lower limit is replaced with the respective limit.

Soft capping: This method involves replacing the extreme values with a less extreme but still plausible value. For example, if we have a data point that is three standard deviations away from the mean, we can replace it with the value that is three standard deviations away from the mean but in the opposite direction.

Capping is a simple and effective method for treating outliers, but it can also result in loss of information and potential bias in the data. Therefore, it is important to carefully consider the choice of capping threshold and the impact on the data before applying this method.

Missing Value:

understand outlier as missing value"NAN" and treat in same manner.
Discretization:

give data in bracket of groups and so the last group of data will known as same number and outlier wont be there.
This is the method in which numerical features are converted to discrete using bins. E.g., if the age 80–90 is considered as a single bin, then all the ages between 80 and 90 will be treated equally.
How to Detect Outlier
Normal "Guassian Distribution" distribution
FIRST ST.DEV - 68.2 % (34.1/34.1)

SECOND ST.DEV - 95.4 % (13.6/13.6)

THIRD ST.DEV - 99.7 % (2.1/2.1)

if any observation is "mean" and "3 sigma" and "mean" and "-3 sigma" then count as outlier.

Skewed Distribution
when data is skwed use "BOX- PLOT"
minimum - q1 - 1.5 * IQR
maximun. - q3 + 1.5 * IQR
IQR - q3-q1
Other Distributions
Percentile approach
capping (2.5th percentile to 97.5 th percentile)
Techniques for Outlier Detection and Removal
1. Z score
The main assumption in this technique is that the data should be normally distributed or close to normal distribution.

If the data is normally distributed, the Empirical Rule says that 68.2% of the data points lie in between the 1st standard deviation, 95.4% of the data points lie in between the 2nd standard deviation, and 99.7% of the data points will be between the 3rd standard deviation.

Data points that lie outside the 3rd standard deviation can be treated as outliers.

As 99.7% of the data will lie within the 3 standard deviations, we can treat the rest of the data which lie outside the 3 standard deviations as outliers.

Standardization or Z-Score Normalization is one of the feature scaling techniques, here, the transformation of features is done by subtracting from the mean and dividing by standard deviation. This is often called Z-score normalization. The resulting data will have the mean as 0 and the standard deviation as 1.

2. IOR
IQR technique This method is used when the distribution of the data is skewed.

The IQR describes the middle 50% of values when ordered from lowest to highest. To find the interquartile range (IQR), ​first, find the median (middle value) of the lower and upper half of the data. These values are quartile 1 (Q1) and quartile 3 (Q3). The IQR is the difference between Q3 and Q1.

IQR = Q3-Q1

Minimum value = Q1–1.5 *IQR

Maximum value = Q3+1.5*IQR

The data points which are lesser than the minimum value and the data points which are greater than the maximum value are treated as outliers.

3. Percentile
Percentile Method In simple words, Percentile can be seen as the value below which a percentage of data falls. If my score is 90 percentile, then that means my score is better than 90 percent of the students who took the examination.

If you scored the maximum score, which happens to be 95, then it is 100 percentile, which means you scored more than the 100% of the students who took the examination.

This is one of the simplest techniques used to detect the outliers in a dataset. We need to just decide the threshold, Eg, if we decide 1 percentile, then it means we treat all the values above 99 percentile and below 1 percentile as outliers.

4. Winsorization
Winsorization is a data transformation technique that involves changing extreme values in a dataset to a less extreme value. This method is used to minimize the impact of outliers in a dataset, which can skew the results of statistical analyses.

The Winsorization process involves setting the extreme values in a dataset to a specified percentile value. For example, the top 5% of values might be set to the 95th percentile value, while the bottom 5% might be set to the 5th percentile value. This effectively limits the influence of outliers on the data analysis while still preserving some information from the original dataset.

Winsorization can be a useful technique in situations where outliers are present in a dataset but are not of particular interest to the analysis. However, it should be used with caution, as it can also result in the loss of valuable information and can potentially introduce bias into the analysis.

