This repo includes the following:

- 'README.md'

- 'CODEBOOK.md'

- run_analysis.R which is the code used to obtain the required tidy dataset
-----------------------------------------------------

HOW DOES THE SCRIPT (run_analysis.R) WORK?

First, we obtain the relevant datasets from the URL provided to us. Download the file, unzip and the datasets get automatically saved into your directory.

Second, install the relevant R packages. For this project, 'reshape2' is needed as functions like 'melt' and 'dcast' will be used later.

Third, read in the relevant textfiles. To reduce the hassle of merging, we may first remove the headers of each individual dataset when reading them in and can insert column names later.

After reading in the datasets, merge them (i.e. data_combined).

Read also the 'features.txt' and 'activity_labels.txt' as they will come in handy when we do the data extraction and labelling.

Insert the appropriate column names to the combined dataset, something like names(data_combined)<-c("",""). Be sure to convert the feature_names to characters, else they turn out as numeric.

After inserting the column names, use the 'grep' function to extract feature_names which consist of the words "mean" or "std". Remove all missing cases. Then, combine the new columns and merge the newly extracted data with the activity labels.

After which, use the function 'melt' into a form suitable for casting. 'Cast' the dataset into the form you desire. In this case, we would like the average of each variable for each activity and each subject.

Finally, write the 'casted' dataset to a .txt file which is stored in your directory.
