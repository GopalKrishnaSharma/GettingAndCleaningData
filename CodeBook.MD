#Raw Data taken from https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip 
#Data information at http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones
#Details of run_analysis.R
<li> Lines 2-8 -> Get all relevant files into dataframes/tables</li>
<li> Lines 11-12 -> Fix Columnnames using transformation of Features</li>
<li> Lines 15-18 -> Fill activities and participants for both test and train</li>
<li> Lines 21-22 ->Merge the two datasets by rowbind and removing duplicate columns</li>
<li> Lines 25-26 -> Storing Means</li>
<li> Lines 29-30 -> Storing STDs</li>
<li> Lines 33-38 -> Rename Activities</li>
<li> Lines 41-45 -> Meaningful Renames for all columns</li>
<li> Lines 48-77 -> Rename Participants</li>
<li> Lines 80-83 -> Create the Tidy DataSet required</li>
