# Getting-and-Cleaning-Data
#The run-analysis.R script has 3 main parts

#Part 1
* The dplyr package is loaded so that grouping and summarise-each functions can be used later.
* The script starts by reading in several files from the <i>test</i> folder.
* The subject-test.txt file is read in. This files tells which subject a particular row in X-test.txt
* The names of the features (or variables) is read in from features.txt
* The activity numbers are read in from y-test.txt
* The activity names are read in from activity-labels.txt
* Since activity-lables.txt has 2 columns, both a number and a string, we can use as.factor to replace the activity numbers with their actual names.
* cbind is then used to combine the subject numbers, activities and the feature data into one dataframe called <i>test.data</i>

#Part 2
* Part 2 is very similar to part 1, except that the <i>train</i> folder is used instead of the <i>test</i> folder.

#Part 3 
* Part 3 consists of several lines of code to combine the data and create the tidy dataset.
* rbind is used to combine test.data and train.data into all.data.
* The columns with either <i>mean</i> or <i>std</i> in the feature name are found using grep.
* The results of grep are used to determine which columns to keep.
* Subsetting is used to create all.std.mean.data.
* The data is grouped by Subject and Activity 
* The data is then summarized by computing the mean of each feature by Subject and Activity

#The Tidy Data Set
+ The resulting data set is tidy because there is only one column for each variable and there is only one row for each combination of Subject and Activity.
+ There are 180 rows to the tidy dataset, which is one for for each Subject/Activity combination (30*6=180)