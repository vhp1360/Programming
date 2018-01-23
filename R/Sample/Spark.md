<div dir=rtl>بنام خدا</div>


1. One:
```R
  if (nchar(Sys.getenv("SPARK_HOME"))<1){
    Sys.setenv(SPARK_HOME="/Path/2/Spark")
  }
  require(SparkR,lib.loc=c(file.path(Sys.getenv("SPARK_HOME"),"R","lib")))
  require(ROracle)
  require(readr)
  
  sparkR.session(master="loacal[*]",sparkConfig=list(spark.driver.memory="1g"))
  oraCon=dbConnect(dbDriver("Oracle"),Server:Pport/SID",username="Name",password="Pass")
  Qry=dbSendQuery(oraCon,"Select ....")
  Df=fetch(Qry,No.)
  while(NROW(Df)>0){
    tryCatch({write.parquet(as.DataFrame(Df),"/Path/2/Parquet")
    write_csv(Df,paste0("/Path/2/Dest",i,".csv")
    Df=fetch(Qry,No.)}),
    warning=function(war){print(paste0("warinig:",war))},
    error=function(err){print(paste0(error:",err))})
  }
  gc()
  sparkR.session(master="local[No.]",sparkConfig=list(spark.driver.memory="No.g"))
  dF=read.df("/Path/2/","com/databricks.spark....",header="true",inferSchema="true")
  write.parquet(dF,"/Path/2/Dest")
```
