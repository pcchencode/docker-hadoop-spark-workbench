## Demo Notes

1. `docker-compose up -d`
2. `docker-compose -f docker-compose-hive.yml up -d`
(因為是cluster，要拉一段時間)



### 啟動 spark 流程, 我們使用 pyspark：
#### 前置步驟，要先把 `dataset.csv` 丟到 hdfs 上，可以用hue丟；也可以丟到container裡用 hdfs put
1. 進到 spark container -> 下指令 /spark/bin/pyspark
2. 讀取檔案 spark.read.csv("hdfs:///user/admin/test/dataset.csv")