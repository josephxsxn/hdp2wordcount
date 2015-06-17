#A working wordcount with oozie wrappers

##Sample Dataset: MusixMatch (~13.5mb)
http://labrosa.ee.columbia.edu/millionsong/sites/default/files/AdditionalFiles/mxm_dataset_test.txt.zip
http://labrosa.ee.columbia.edu/millionsong/musixmatch



##Instructions For Standalone MR Usage:

######1) Make directory for user if not already exists

> hdfs dfs -mkdir /user/$USERNAME

######2) Make raw data folder for musixmatch dataset

> hdfs dfs -mkdir rawmusixmatch

######3) Upload raw dataset to HDFS

> hdfs dfs -put mxm_dataset_test.txt rawmusixmatch/

######4) Execute MR Job

> yarn jar hdp2wordcount-0.0.1-SNAPSHOT.jar hdp2wordcount.WordCount rawmusixmatch $OUTPUTDIR




##Instructions For Oozie  Usage:

######1) Make directory for user if not already exists

> hdfs dfs -mkdir /user/$USERNAME

######2) Make raw data folder for musixmatch dataset

> hdfs dfs -mkdir rawmusixmatch

######3) Upload raw dataset to HDFS

> hdfs dfs -put mxm_dataset_test.txt rawmusixmatch/

######4) Upload ooziewc folder to HDFS

> hdfs dfs -put ooziewc/ .

######5) Execute the Oozie Workflow!

> oozie job -oozie http://sandbox.hortonworks.com:11000/oozie -config job.properties  -run
