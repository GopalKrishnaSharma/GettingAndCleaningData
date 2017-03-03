#Raw Data taken from https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip 
#Data information at http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones
#Details of run_analysis.R
<li> Lines 2-8 -> Get all relevant files into dataframes/tables</li>
XTest, YTest, SubjectTest, YTrain, XTrain, SubjectTrain,Features get the data from the X_test.txt, y_test.txt, subject_test.txt, X_train.txt, y_train.txt, subject_train.txt, features.txt files respectively

<li> Lines 11-12 -> Fix Columnnames using transformation of Features</li>
Features variable contains all the required variable names for XTest and XTrain hence setting the columns for XTrain and XTest using transpose of Features (2nd column)

<li> Lines 15-18 -> Fill activities and participants for both test and train</li>
YTrain and YTest contain list of activities for XTrain and XTest resp while SubjectTrain and SubjectTest contain list of participants. Filling these accordingly 

<li> Lines 21-22 ->Merge the two datasets by rowbind and removing duplicate columns</li>
Merging the datasets by using rbind and removing the duplicates by using the duplicated() method

<li> Lines 25-26 -> Storing Means</li>
Storing means in a variable by the name MeanMatrix

<li> Lines 29-30 -> Storing STDs</li>
Storing Standard Deviations in a variable by the name STDMatrix

<li> Lines 33-38 -> Rename Activities</li>
Renaming activities as they're described in the activity_labels.txt file

<li> Lines 41-45 -> Meaningful Renames for all columns</li>
Renaming the columns to make them more readable. Following changes were made:
<ui>1) Replace columns containing "Acc" with "Accelerator"</ui>
<ui>2) Replace columns containing "Mag" with "Magnitude"</ui>
<ui>3) Replace columns starting with "t" to start with "time"</ui>
 <ui>1) Replace columns starting with "f" to start with "frequency"</ui>

<li> Lines 48-77 -> Rename Participants</li>
Rename all participants based on number to make it more readable

<li> Lines 80-83 -> Create the Tidy DataSet required</li>
Dataset created using data.table and lappy. Stored as Tidy.txt in the workspace using write.table

<li>Variable Summary</li>
The features selected for this database come from the accelerometer and gyroscope 3-axial raw signals tAcc-XYZ and tGyro-XYZ. These time domain signals (prefix 't' to denote time) were captured at a constant rate of 50 Hz. Then they were filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise. Similarly, the acceleration signal was then separated into body and gravity acceleration signals (tBodyAcc-XYZ and tGravityAcc-XYZ) using another low pass Butterworth filter with a corner frequency of 0.3 Hz. 

Subsequently, the body linear acceleration and angular velocity were derived in time to obtain Jerk signals (tBodyAccJerk-XYZ and tBodyGyroJerk-XYZ). Also the magnitude of these three-dimensional signals were calculated using the Euclidean norm (tBodyAccMag, tGravityAccMag, tBodyAccJerkMag, tBodyGyroMag, tBodyGyroJerkMag). 

Finally a Fast Fourier Transform (FFT) was applied to some of these signals producing fBodyAcc-XYZ, fBodyAccJerk-XYZ, fBodyGyro-XYZ, fBodyAccJerkMag, fBodyGyroMag, fBodyGyroJerkMag. (Note the 'f' to indicate frequency domain signals). 

These signals were used to estimate variables of the feature vector for each pattern:  
'-XYZ' is used to denote 3-axial signals in the X, Y and Z directions.

tBodyAcc-XYZ changed to timeBodyAccelerator-XYZ after renaming
tGravityAcc-XYZ changed to timeGravityAccelerator-XYZ after renaming
tBodyAccJerk-XYZ changed to timeBodyAcceleratorJerk-XYZ after renaming
tBodyGyro-XYZ changed to timeBodyGyroscope-XYZ after renaming
tBodyGyroJerk-XYZ changed to timeBodyGyroscopeJerk-XYZ after renaming
tBodyAccMag changed to timeBodyAcceleratorMagnitude after renaming
tGravityAccMag changed to timeGravityAcceleratorMagnitude after renaming
tBodyAccJerkMag changed to timeBodyAcceleratorJerkMagnitude after renaming
tBodyGyroMag changed to timeBodyGyroscopeMagnitude after renaming
tBodyGyroJerkMag changed to timeBodyGyroscopeJerkMagnitude after renaming
fBodyAcc-XYZ changed to frequencyBodyAccelerator-XYZ after renaming
fBodyAccJerk-XYZ changed to frequencyBodyAcceleratorJerk-XYZ after renaming
fBodyGyro-XYZ changed to frequencyBodyGyroscope-XYZ after renaming
fBodyAccMag changed to frequencyBodyAcceleratorMagnitude after renaming
fBodyAccJerkMag changed to frequencyBodyAcceleratorJerkMagnitude after renaming
fBodyGyroMag changed to frequencyBodyGyroscopeMagnitude after renaming
fBodyGyroJerkMag changed to frequencyBodyGyroscopeJerkMagnitue after renaming

The set of variables that were estimated from these signals are: 

mean(): Mean value
std(): Standard deviation
mad(): Median absolute deviation 
max(): Largest value in array
min(): Smallest value in array
sma(): Signal magnitude area
energy(): Energy measure. Sum of the squares divided by the number of values. 
iqr(): Interquartile range 
entropy(): Signal entropy
arCoeff(): Autorregresion coefficients with Burg order equal to 4
correlation(): correlation coefficient between two signals
maxInds(): index of the frequency component with largest magnitude
meanFreq(): Weighted average of the frequency components to obtain a mean frequency
skewness(): skewness of the frequency domain signal 
kurtosis(): kurtosis of the frequency domain signal 
bandsEnergy(): Energy of a frequency interval within the 64 bins of the FFT of each window.
angle(): Angle between to vectors.

