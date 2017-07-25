<div dir="rtl">بنام خدا</div>

```R
  Sys.setenv(SPARK_HOME="/home")
  .libPaths(c(file.path(Sys.getenv("SPARK_HOME"), "R", "lib"), .libPaths()))
  library(SparkR)
```
