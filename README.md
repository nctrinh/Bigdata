## Upload dữ liệu lên HDFS  
Thực hiện theo các bước sau:

```bash
docker exec -it namenode hdfs dfsadmin -safemode leave

docker exec -it namenode mkdir -p /opt/bigdata/data/

docker cp ./data/loan.csv namenode:/opt/bigdata/data/

docker exec -it namenode hdfs dfs -mkdir -p /bigdata/data
docker exec -it namenode hdfs dfs -mkdir -p /bigdata/notebooks
docker exec -it namenode hdfs dfs -mkdir -p /bigdata/data/splitted_data
docker exec -it namenode hdfs dfs -mkdir -p /bigdata/data/processed_data

docker exec -it namenode hdfs dfs -put /opt/bigdata/data/loan.csv /bigdata/data/
```

