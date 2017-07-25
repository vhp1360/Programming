<div dir=rtl>بنام خدا</div>

###### top

- [Load Session](#load-session)
- [Read](#read)
- [Write](#write)


### Load Session
- 0ne:
```python
  import findspark
  findspark.init("/Path/2/spark")
  import pyspark
  from pyspark.sql import SparkSession
  spark = SparkSession.builder.master("local[5]").appName("AppName").getOrCreate()
  sc = spark.sql
  # spark.stop()
```
- Two:


### Read
- One:
```python
  df= spark.read.parquet("/Path/2/ParquetFile")
  df.head()
```

- Two:
