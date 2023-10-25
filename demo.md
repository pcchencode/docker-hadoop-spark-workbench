## Demo Notes
1. `docker-compose up -d`
2. `docker-compose -f docker-compose-hive.yml up -d`
(因為是cluster，要拉一段時間)

## 流程：
1. 示範 docker ps
* 進入 hue Web 頁面
2. 進入 hadoop master node
* 進入 hive-server
* 隨便創建一張表
```
CREATE TABLE IF NOT EXISTS employee ( eid int, name String,
salary String, destination String);
```
*. 上傳 dataset.csv
*. 進入 spark master , 啟動 pyspark 讀取 dataset.csv




### 啟動 spark 流程, 我們使用 pyspark：
#### 前置步驟，要先把 `dataset.csv` 丟到 hdfs 上，可以用hue丟；也可以丟到container裡用 hdfs put
1. 進到 spark-master container(spark-master) -> 下指令 /spark/bin/pyspark
2. 讀取檔案 df = spark.read.csv("hdfs:///user/admin/test/dataset.csv").limit(5)