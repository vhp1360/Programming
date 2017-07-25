<div dir="rtl">بنام خدا</div>

###### Top
- [CSV Files](#csv-files)
- [Standalone Cluster](#standalone-cluster)


###### [Top](#top)
#### CSV Files
1. write
```scala
  import org.apache.spark.sql.functions._
  import spark.implicits._
  val Rdd = spark.read.csv("/Path to *.csv")
  Rdd.withColumn("NewCol",substring(datacdr("ColName"),9,2))
  Rdd.sort("NewCol")
  Rdd.select("ColName1",...).partitionBy("NewCol").write("/media/SSD/MCI0")
  Rdd.write.partitionBy("NewCol").parquet("/Path To Save")
```
2. Showing
```scala
  Rdd=spark.read.parquet("/Path/*/*/...")
  Rdd.select("FieldName").show
  Rdd.groupBy("Fields").count().show
```


###### [Top](#top)
#### Standalone Cluster
*__Note__*: it's better to config it for each user.

1. [config ssh to paswordless](https://github.com/vhp1360/Linux/blob/master/Linux/AdminSecurityActivity.md#ssh)
2. config spark-env.sh file:
  - export SPARK_HOME=Path
  - export JAVA_HOME=Path
  - export SPARK_WORKER_CORE=No.
3. config config slaves
  - Slaves Name Or May IP per line
4. ~/.profile:
```go
  export SPARK_HOME=/home/shomara/spark
  export PATH=$PATH:$SPARK_HOME/bin
```

 
 
 

###### [Top](#top)






