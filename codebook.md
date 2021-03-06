Introduction
The script run_analysis.R performs 5 steps.
Step 1: merge all similar data using the rbind() function. These are files that have the same number of columns and referring to the same entities.
Step 2: this step only uses columns with the mean and standard deviation in the dataset. After completing, they're given the correct names from features.txt.
Step 3: As activity data is addressed with values 1:6, we take the activity names and IDs from activity_labels.txt and they are substituted in the dataset.
Step 4: On the whole dataset, those columns with missing/vague column names are corrected.
Step 5: Generate a new dataset with all the average measures for each subject and activity type (30 subjects * 6 activities = 180 rows). The output file is called Tidy.txt, and uploaded to this repository.
Variables
x_train, y_train, x_test, y_test, subject_train and subject_test contain the data from the downloaded files.
x_data, y_data and subject_data merge the previous datasets to further analysis.
features contains the correct names for the x_data dataset, which are applied to the column names stored in mean_and_std_features, a numeric vector used to extract the desired data.
A similar approach is taken with activity names through the activities variable.
all_data merges x_data, y_data and subject_data in a big dataset.
Finally, averages_data contains the relevant averages which will be later stored in a Tidy.txt file. ddply() from the plyr package is used to apply colMeans() and ease the development.
