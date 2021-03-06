# Getting and Cleaaning Data - Course Project
##Introduction
The script run_analysis.R performs the following steps:
*Download the raw data 
*Read in the files and assign columns names
*Merge the data into one dataset
*Create a second dataset with only variables containing means and standard deviation
*Make the variables names more understandable 
*Calculate a mean for each variable for each activity and each subject
*Write all the mean values to a file

More information about the source data can be found [here][http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones]

##Step 1: Download the raw data
The raw data is download from [here][https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip] and then unzipped

##Step 2: Read in the files and assign columns names
The following files a red and column names are added. 
*features.txt
*activity_labels.txt
*subject_train.txt
*x_train.txt
*y_train.txt
*subject_test.txt
*x_test.txt
*y_test.txt

##Step 3: Merge the data into one dataset
All information in the files from step 2 is merged into one big matrix called allData


##Step 4: Create a second dataset with only variables containing means and standard deviation
A filter is created with all columns with mean or std in their name. A second dataset, wantedData, is created by subsetting allData with the filter. 

##Step 5: Make the variables names more understandable
some text strings are replaced with longer names to make it easier to understand the variable names. 
*t->time
*f->frequency
*Acc->Accelerometer
*Gyro->Gyroscope
*Mag->Magnitude
*BodyBody->Body

##Step 6: Calculate a mean for each variable for each activity and each subject
A mean i calculcated for ecah variable for each activity and subject with dplyrs aggregate function. 

##Step 7: Write all the mean values to a file
Before all the mean values are written to a file some columns are removed. These columns are just id vectors hence not containing any useful information

The resulting file with calculated means contains the follwing information: 
*An activity label named "activity": LAYING; SITTING, STANDING, WALKING, WALKING_DOWNSTAIRS, WALKING_UPSTAIRS]
*An identifier of the subject who did the experiment (subject): [1:30]
*180 rows with calculated means and 66 variables
