Description of run_analysis.R
=============================
The script run_analysis.R does the following:

1. It merges the training and test data sets.
2. Extracts only measurements on the mean and standard deviation for each measurement.
3. Name the activities with proper descriptions.
4. Adds names for the variables and finally.
5. It creates a independent tidy data set with average of each variable for each activity and each subject.

This is achieved through the following steps:

1. Read the datasets into data frames.
2. Set the Column Names for the training and testing data frames using the data frame that contains the data from features.txt.
3. Using cbind, the activity column is added to the training and testing dataframes.
4. Then the column name in each dataframe is set to "activity".
5. Similarly using cbind, the subject column is added to the two dataframes and the name of the added column is set to "subject".
6. Now the collected data (or features) have been associated with the activity and the subject.
7. After the above, the training and test dataframes are merged using rbind.
8. Using the merged dataframe, we subset the fields that are mean or std deviations are then selected.
9. Then using the plyr library we calculate the summary of each feature per user per activity.
10. Finally the "activity" codes are replaced with activity descriptions.
11. The cleaned data set is then written into a file named "tidy.txt".