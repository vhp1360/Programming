<div dir=rtl>بنام خدا</div>


1. One:
```R
  if (nchar(Sys.getenv("SPARK_HOME"))<1){
    Sys.setenv(SPARK_HOME="/Path/2/Spark")
  }
  require(SparkR,lib.loc=c(file.path(Sys.getenv("SPARK_HOME"),"R","lib")))
  require(ROracle)
  
  sparkR.session(master="loacal[*]",sparkConfig=list(spark.driver.memory="1g"))
  oraCon=dbConnect(dbDriver("Oracle"),Server:Pport/SID",username="Name",password="Pass")
  Qry=dbSendQuery(oraCon,"Select ....")
  Df=fetch(Qry,No.)
  while(NROW(Df)>0){
    write.parquet(as.DataFrame(Df),"/Path/2/Parquet")
    Df=fetch(Qry,No.)
  }
```
