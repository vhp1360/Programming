<div dir=rtl>بنام خدا</div>

###### top

- [Exception](#exception)


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
  
  
