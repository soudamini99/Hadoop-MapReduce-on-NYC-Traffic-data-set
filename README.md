# Hadoop-MapReduce-on-NYC-Traffic-data-set
To the read the csv data file path is /data/nyc/nyc-traffic.csv

# The files mapper.py and reducer.py are cloned into Hadoop from GitHub using the below command

$ git clone https://github.uc.edu/chintasd/CloudComputing_HW4.git

# Commands to run the mapper.py and reducer.py scripts over the nyc-traffic.csv

$ hadoop fs -cat /data/nyc/nyc-traffic.csv | python mapper.py | sort | python reducer.py

# Command to run the MapReduce on hadoop cluster using Hadoop jar streaming

$ hadoop jar /usr/hdp/2.6.3.0-235/hadoop-mapreduce/hadoop-streaming-2.7.3.2.6.3.0-235.jar -file mapper.py -mapper mapper.py -file reducer.py -reducer reducer.py -input /data/nyc/nyc-traffic.csv -output HW4

# For results of the output file, use the below command

$ hadoop fs -cat /user/chintasd/HW4/*
