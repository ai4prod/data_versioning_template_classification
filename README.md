# data_versioning_template_classification
Template for Dataset versioning for classification task. This repository is the base template in order to integrate data versioning for classification task using ai4prod_python.


# How it works

See data_versioning_template repository


# Change in this repository

We adapt dataset folder path in order to be integrated in ai4prod_python


# How to Connect to a remote Dataset on Local Machine

This code will setup a remote folder for dataset version. It is working as a git remote repository but for large dataset file

0) git init

1) dvc init {ONLY IF THE FIRST TIME}

2) dvc remote add -d dvc-remote {PATH TO LOCAL REMOTE. Usually path is  /path/to/Local/NameDatasetRemote}

3) git rm -r --cached 'Data/Dataset'
   git commit -m "stop tracking Data/Dataset init dataset_name"
   dvc add Data/Dataset  {Add Dataset folder inside Data/Dataset. Inside Dataset folder you need to add your data. This will be tracked by version} 

4) git add Data/Dataset.dvc ./gitignore

5) git commit -am "add dataset version 1"

6) git tag -a 'v1' -m 'raw data' {Used to retrive Dataset with version without Tag}

7) dvc push {Push dataset to remote localtion /path/to/Local/NameDatasetRemote }



# How to Add new Data and Version

1) Add new Data to Data/Dataset folder  

2) Repeat step 3-7 WARNING Change git tag v1 with incremental number

# How to retrive a dataset

1) Download a git repository contain Dataset.dvc

2) Inside repository execute dvc pull {This will download latest dataset version}



# How to retrieve a specific dataset version

1) Download a git repository contain Dataset.dvc

2) git checkout v{SPECIFY DATASET VERSION} Example git checkout v1

3) Inside repository execute dvc pull {This will download the selected dataset version}
