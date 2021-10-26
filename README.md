# Apache Hadoop distribution on Ubuntu with Spark, Pig, and Hive

## The original Dockerfile is updated in this repository to support Apple Silicone (ARM). Furthermore, archived binary URL are also updated in the Dockerfile

The docker image Apache hadoop 2.9.2 distribution on Ubuntu 18.04 with Spark 2.4.3, Pig 0.17.0, and Hive 2.3.5


Find this on Docker Hub [https://hub.docker.com/r/sahan93/hadoop-spark-pig-hive](https://hub.docker.com/r/sahan93/hadoop-spark-pig-hive)

# Build the image

```shell
docker build  -t sahan93/hadoop-spark-pig-hive:2.9.2 .
```
# Pull the image

```shell
docker pull sahan93/hadoop-spark-pig-hive:2.9.2
```

# Start a container

## Using docker cli

In order to use the Docker image you have just build or pulled use:

```shell
docker run -it -p 50070:50070 -p 8088:8088 -p 8080:8080 sahan93/hadoop-spark-pig-hive:2.9.2 bash
```

## Using Docker Compose

```shell
docker-compose up -d
```

## Testing

You can run one of the hadoop examples:

```
# run the mapreduce
yarn jar $HADOOP_HOME/share/hadoop/mapreduce/hadoop-mapreduce-examples-2.9.2.jar grep input output 'dfs[a-z.]+'

# check the output
hdfs dfs -cat output/*
```

## Run

### Hive

```
hive
```

or

```
 beeline -u jdbc:hive2://
```

### Pig

```
pig
```

### Spark

Scala

```
spark-shell
```

Python

```
pyspark
```



