# Intro to Spark and Parquet
iPython notebooks containing introductory examples of Spark and Parquet

# Setup
* Checkout this repo.
```
git clone https://github.com/LogBaseInc/spark-parquet-intro-talk.git
```
* Download the data sets.
```
cd spark-parquet-intro
curl -L https://storage.googleapis.com/logbase-public/data-sets/server.log.gz -o server.log.gz
curl -L https://storage.googleapis.com/logbase-public/data-sets/tweets.json.gz -o tweets.json.gz
```
* Extract the files, keeping the source files.
```
gzip --keep -d tweets.json.gz server.log.gz
```
* Get spark-anaconda container for running these notebooks.
```
docker pull logbase/spark-anaconda
```
* Start the container with the spark-parquet-intro dir mounted.
```
export SPARK_INTRO_DIR=$(pwd)
docker run -it -p 4040:4040 -p 8888:8888 -v $SPARK_INTRO_DIR:/spark-parquet-intro-talk spark-anaconda
```
* Checkout iPython app in http://localhost:8888 or http://<linux-vm-ip>:8888 depending on how you run your docker service.
