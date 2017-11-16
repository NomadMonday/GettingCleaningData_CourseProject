run_analysis.R will produce two data frames: selectdata and meandata. The selectdata data set contains only the mean and standard deviation values from the combined test and train data from the UCI HAR Dataset, along with the subject and activity observed. The meandata data set contains the total mean values from the selectdata data set, grouped by each unique combination of variables. Below is a description of the column variables.

activityname: Name of activity being performed while observation was recorded. Can contain values:
	WALKING
	WALKING_UPSTAIRS
	WALKING_DOWNSTAIRS
	SITTING
	STANDING
	LAYING

subject: The subject being observed. There were 30 volunteers that were monitored and this column is denoted by their number, 1-30.

domainsignal: Two types of domain signals were observed: frequency and time.

measurement: Measurements were separated into measurements of the body acceleration and that of gravity acceleration. Note that there were actually three categories: body, bodybody, and gravity.

measurementtype: The type of the acceleration signal observed.
	AccJerk: acceleration jerk
	Acc: acceleration
	GyroJerk: gyroscopic jerk
	Gyro: gyroscopic

direction: Denotes the xyz-axis or magnitude.

mean (selectdata): The mean value of the measurement.

standarddeviation (selectdata): The standard deviation of hte measurement.

meanofmean (meandata): The mean of the means grouped by subject, activityname, domainsignal, measurement, measurementtype, and direction.

meanofstandarddeviation (meandata): The mean of all the standard deviations grouped by subject, activityname, domainsignal, measurement, measurementtype, and direction.
