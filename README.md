# getting-and-cleaning-data
week 4 peer graded assignment

Prerequisites

The script will require the dplyr package
You can install those by doing `install.packages("dyplr")

Step by step
Clone this repository somewhere on your computer
Open an R session, and set the working directory to be the same as the run_analysis.R script, which should be the root of the clone project
Type source("run_analysis.R") : the script will carry out the work, and produce a result file in the same folder, called averaged_data.txt according to the process described below in Data transformation.
Be sure to check the Code book

##Data transformation

All those steps will be taken care of automatically by the script

Original data has been split into a training set and a test set : the first goal is to merge them.
All 3 tables are merged using row binding, to form 3 sets
Measurements : accelerometers measurements (features)
MeasurementsLabel : the activities undertaken during the measurements (activities)
MeasurementSubjects : the subject undertaking the activities (subjects)
all temporary data is cleanup, for memory preservation
Features are filtered to keep only the ones describing mean or standard deviation values
The measurements table is updated with the proper feature names
Feature names have been cleaned to remove useless parenthesis, as well as turned to lower case.Dash and underscores have been kept for readability, as the variable names are very long.
Measurement table receives the proper feature names
The measurementsLabel table is updated with the proper activity name
Activity names have been cleaned (lowercase). Underscores have been kept for readability (as the values are lowercase).
MeasurementLabel receives the proper activity names
Proper column names are given where missing, to describe "activity" and "subject"
all 3 tables are merged together and rearranged
column bind, with subject and activity first
all data is arranged in ascending order or subject, then activity
At this point this is a clean "wide" dataset : one variable per column, each row is a different observation
A summary dataset is produced, showing only the average for each feature per subject per activity
Dplyr package is used to produce the summary, after grouping the data by subject by activity
This results in a clean, "wide" summary dataset :
one variable per column (subject, activity, and all features measured, with one column per feature)
and each row is a different observation for each variable.
the table contains only one kind of data (accelerometer data from one specific experience)
there is a top row with the variable names in a readable way
there is a code book explaining how the data has been produced
the resulting table is exported in a an averaged_data.txt file, in the working directory.
