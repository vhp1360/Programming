<div dir=rtl>بنام خدا</div>

1.
```python
  import cx_Oracle
  import os
  import csv
  ip = 'SomeThing'
  port = 1521
  SID = 'SomeThing'
  dsn_tns = cx_Oracle.makedsn(ip, port, SID)

  db = cx_Oracle.connect('UserName', 'Password', dsn_tns[, encoding = "UTF-8", nencoding = "UTF-8"])
  curs = db.cursor()
  curs.execute("SELECT * FROM  ....")
  print (curs.description)
  i=0
  for row in curs:
      print (row)
      i+=1
      if i>=10: break
  # or Write to csv File
  with open('Sample.csv','w') as f:
    writer=csv.writer(f)
    writer.writerow([i[0] for i in curs.description])
    writer.writerows(curs.fetchall())

```
