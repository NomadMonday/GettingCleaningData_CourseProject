# GettingCleaningData_CourseProject
Course project for the Coursera Getting and Cleaning Data course.

This project contains run_analysis.R and run_analysis_codebook.md. The run_analysis.R script should be run from within the "UCI HAR Dataset" folder so that relative pathing aligns for access to the test and train data. The analysis will combine the test and train data, extract the mean and standard deviation values, and then create two tidy data sets: selectdata and meandata. The selectdata data set contains the full set of mean and standard deviation values. The meandata data set contains the mean of mean and mean of standard deviation values, grouped by each unique combination of variables.

Details regarding the script workflow are as follows:
- Read in the features.txt file in order to get the header values for the X_test/X_train data.
- Read in test\subject_test.txt and test\y_test.txt. Combine them into a two column data set, and assign the headers "subject" and "activity".
- Read in test\X_test.txt and assign the header values captured from features.txt.
- Combine these all into one test data set.
- Repeat the same process for the train data set.
- Combine the test data and train data into one single data set.
- Extract into a subset, just the subject and activity columns, and any columns that contain mean() or std() in the header. Note that there are other "mean" values, but these are derived values and not direct mean values of the raw data, so we are not interested in these.
- Normalize the header names, so that we can split them into their various parts. Here, I used a regular expression to separate the various parts, using an underscore as a separator. Note that "Mag" values were moved to the end of the header so as to be grouped with X/Y/Z values, since these values were mutually exclusive and could be grouped as a part of the same variable.
- Data was then "gathered" (via tidyr) based on mean values, then also "gathered" based on standard deviation values.
- Once gathered, we could then use our normalized former header values to "separate" the variables. Note that gathering on both mean and standard deviation produced two redundant variables, which were removed (see comments within the script for details).
- After separating, our tidy data set is created. We can then group by each of the variables and use the summarize() function to produce another tidy data set with the overall mean of means and mean of standard deviations.
