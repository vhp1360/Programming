<div dir=rtl>بنام خدا</div>

###### top

- [Oracle](#oracle)
- [Query](#query)
- [Save](#save)
- [Preserve Charset](#preserve-charset)
- [Complete Path Code](#complete-path-code)




### Oracle
##### Connection
1. thin Connection(only OCI installaion need):
```R
  require(ROracle)
  Con=dbConnect(dbDriver("Oracle"),"IP/mdw",username="UserName",password="Pass")
```

[top](#top)
##### Query
1. First:
```R
  Q=dbSendQuery(Con,"Select * From Table Where  ")
  Fa=fetch(Q)
```

[top](#top)
##### Save
1. Frist
```R
  write_csv(Fa,path = "sample.csv")
```

[top](#top)
##### Preserve Charset
```R
  Sys.setenv(NLS_LANG="AMERICAN_AMERICA.AL32UTF8")
```


[top](#top)
##### Complete Path Code
1. Frist
```R
  Sys.setenv(NLS_LANG="AMERICAN_AMERICA.AL32UTF8")
  library(ROracle)
  library(readr)
  Con=dbConnect(dbDriver("Oracle"),"Port:1521/DBName",username="UserName",password="Password")
  Q=dbSendQuery(Con,"Select * From ... ")
  Fa=fetch(Q,n=No.)
  write_csv(Fa,path = paste0("/media/Windows1/New",i,".csv"))
```
