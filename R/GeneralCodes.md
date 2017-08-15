<div dir=rtl>بنام خدا</div>

###### top

- [Exception](#exception)
- [Memory](#memory)

# Exception
1. Handling it:
```R
  tryCatch({
      Codes
  }, warning = function(war) {
      print(paste("warning:  ",war))
  }, error = function(err) {
      print(paste("error:  ",err))
  })
```
  
[top](#top)
# Memory
1. Clear Ram:
```r
  rm(list=ls()) 
```
2. Clean Garbage:
```r
  cleanMem <- function(n=10) { for (i in 1:n) gc() }
```
