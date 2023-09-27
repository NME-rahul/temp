# Outlier detection methods

## Statisitcal approach
1. Z-score
The Z-score is the number of deviations by which a data point is determined above or below the mean value. It is also used as an "outlier detection method" of finding out if a data point is too far or too close to the mean value.

		z = \frac{x_i - mean}{\sigma}

2. Modified Z-score
This is a modififed version of z score, it uses MAD(mean absolute deviation) inseat of standard deviation and median instead mean.

		z = \frac{x_i - median}{MAD}
		where MAD = median( |x_1 - median|, |x_2 - median|, |x_3 - median|,....., |x_n - median| )

3. Inter Quartile Range(IQR)
IQR is a measure of spread of the middle half of a data set, it its calculated as the difference between third quartile and the first qurtile. The IQR is used to access the variability of middle 50% of a sample.

		lower fance = Q1 - K.IQR
		upper fance = Q3 - K.IQR
		
		Q1 = median of series
		Q3 = median of right series of median
		IQR = Q3 - Q1



## Proximity based
1. K-nearest neighbour(KNN)
KNN identifies outliers as the data points that have the K samllest distance to their nearest neighbours.

**Algorithm**

Data Points:
(2, 3), (4, 5), (3, 4), (10, 12), (11, 11)

* Deifine the value of K, let k=3.
*  Calculate Euclidean distance for each data point.

		(2, 3) to (4, 5) = \sqrt{(4 - 2)^2 + (5 - 3)^2} = 2.82842712475
		(2, 3) to (3, 4) = \sqrt{(3 - 2)^2 + (4 - 3)^2} = 1.4142
		(2, 3) to (10, 12) = \sqrt{(10 - 2)^2 + (12 - 3)^2} = 12.0416
		(2, 3) to (11, 11) = \sqrt{(11 - 2)^2 + (11 - 3)^2} = 12.0416

		(4, 5) to (3, 4) = \sqrt{(3 - 4)^2 + (4 - 5)^2} = 1.4121
		(4, 5) to (10, 12) = \sqrt{(10 - 4)^2 + (12 - 5)^2} = 9.2195
		(4, 5) to (11, 11) = \sqrt{(11 - 4)^2 + (11 - 5)^2} = 9.2195

		(3, 4) to (10, 12) = \sqrt{(10 - 3)^2 + (12 - 4)^2} = 10.6301
		(3, 4) to (11, 11) = \sqrt{(11 - 3)^2 + (11 - 4)^2} = 10.6301

		(10, 12) to (11, 11) = \sqrt{(11 - 10)^2 + (11 - 12)^2} = 1.4121


* set the threshold value, the distance which is greater then threshold value is treated as outlier. let threshold value is 5.

here (10, 12) and (11, 11) are outlier for the (2, 3), (4, 5), (3, 4).
last caluclation is showing less then threshold because they are the point which are close to each other but not with others.


2. Local Outlier Factor(LOF)
LOF measures the local density deviation of a data point with respect to its neighbours to determine whether it is an outlier.

## Density based
1. DBSCAN
