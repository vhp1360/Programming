<div dir=rtl>بنام خدا</div>

###### top

- [Oracle](#oracle)
- [Query](#query)
- [Save](#save)
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
  require(ROracle)
  Q=dbSendQuery(Con,"Select * From Table Where  ")
  Fa=fetch(Q)
```

[top](#top)
##### Save
1. Frist
```R
  require(ROracle)
  library(readr)
  write_csv(Fa,path = "sample.csv")
```


##### Complete Path Code
1. Frist
```R
  require(ROracle)
  library(readr)
  Con=dbConnect(dbDriver("Oracle"),"IP/SID",username="UserName",password="Pass")
  Q=dbSendQuery(Con,"Select * From Table Where ")
  Faa=fetch(Q)
  str(Faa)
  write_csv(Faa,path = "sample.csv")
```
