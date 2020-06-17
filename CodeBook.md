run_analysis.R prepares and follows the steps required by the final project guidelines of Johns Hopkins Courera Course: Getting and Cleaning Data.

1. Loading dplyr and downloading the data set and extracting it to a folder called UCI HAR Dataset.

2. Assigning each data to variables
      features <- features.txt : 561 rows, 2 cols
            Features come from the acceleromter and gyroscope 3-axial raw signals tAcc-XYZ and tGyro-XYZ.
      activities <- activity_labels.txt : 6 rows, 2 cols
            Activities performed when the  measurements were taken and its labels.
      subject_test <- test/subject_test.txt : 2947 rows, 1 col
            Test data of 9/30 volunteer test subjects being observed.
      x_test <- test/X_test.txt : 2947 rows, 561 cols
            Contains recorded features test data.
      y_test <- test/y_test.txt : 2947 rows, 1 col
            Contains test data of activity code labels.
      subject_train <- test/subject_train.txt : 7352 rows, 1 col
            Contains training data of 21/30 volunteer subjects being observed.
      x_train <- test/X_train.txt : 7352 rows, 561 cols
            Contains recorded features training data.
      y_train <- test/y_train.txt : 7352 rows, 1 cols
            Contains training data of activity code labels.
             
3. Merging the training and test sets into one dataset (Merged_Data)
      X: 10299 rows, 561 cols 
            Created by merging x_train and x_test using rbind() function.
      Y: 10299 rows, 1 col 
            Created by merging y_train and y_test using rbind() function.
      Subject: 10299 rows, 1 cols
            Created by merging subject_train and subject_test using rbind() function.
      Merged_Data: 10299 rows, 563 cols
            Created by merging Subject, Y and X using cbind() function.
             
4. Extracting the measurements on the mean and standard deviation for the measurements.
      Tidy_Data: 10299 rows, 88 cols
            Created by subsetting Merged_data, selecting the columns subject, code, mean, and std.
            
5. Replacing activity names in the dataset with more descriptive ones.
      Numbers in code column of Tidy_Data replaced with representative activity from the second column of activities variable (created step 2).
      
6. Labeling the data set with descriptive variable names.
      code column in TidyData renamed into activities.
      All Acc in column’s name replaced by Accelerometer.
      All Gyro in column’s name replaced by Gyroscope.
      All BodyBody in column’s name replaced by Body.
      All Mag in column’s name replaced by Magnitude.
      All start with character f in column’s name replaced by Frequency.
      All start with character t in column’s name replaced by Time.
      
7. Creating a final, independent, and tidy data set that contains the average of each variable for each activity and each subject.
      Final_Data: 180 rows, 88 cols
              Created by sumarizing Tidy_Data taking the means of each variable for each activity and each subject, after grouped by subject and activity.
      Export Final_Data into FinalData.txt file.
             
