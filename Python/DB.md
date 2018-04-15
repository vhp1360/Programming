<div dir="rtl">بنام خدا</div>

- [Couchbase](#couchbase)
  - [Connection](#connection)
  - [Data Insertion](#data-insertion)
  - [Query](#query)
- [Oracle](#oracle)
  - [Oracle-Connection](#oracle-connection)
  - [Oracle-Data Insertion](#oracle-data-insertion)
  - [Oracle-Query](#oracle-query)
- [Access DB](#access-db)
  - [Convert 2 Csv](#convert-2-csv)
  

[top](#top)

# Couchbase
### Connection
1. First:
```python
  from couchbase.bucket import Bucket
  ShomaraBucket = Bucket('couchbases://IP/BucketName?certpath=/Path to cert.pem',password='Pass')
  ShomaraBucket = Bucket('couchbase://IP/BucketName',password='Pass')
  if ShomaraBucket.connected:
     print ('True')
  else:
     print('False')
```


[top](#top)

##### Data Insertion
1.First:
```python
  import gzip
  import json

  FieldName=("ID", ...)
  bachs = {}
  i=0
  print("Start of Transaction")
  with gzip.open('/Path To Json.gz Data/Data.json.gz','r') as FileData:
      for Line in FileData:
          Json=json.loads(Line)
          Key=str(Json.pop('ID'))
          bachs[Key]={str(key):str(value) for key,value in Json.iteritems()}
          i+=1
          if i>=110000:
              BucketName.upsert_multi(bachs)
              bachs = {}
              print(str(i) + ' Elems Inserted' )
- [Access DB](#access-db)
  - [Convert 2 Csv](#convert2csv)
      BucketName.upsert(LRow[0],{FieldName[1]:LRow[1],FieldName[2]:LRow[2],FieldName[3]:LRow[3],FieldName[4]:LRow[4],
                     FieldName[5]:LRow[5],FieldName[6]:LRow[6],FieldName[7]:LRow[7],FieldName[8]:LRow[8],
                     FieldName[9]:LRow[9],FieldName[10]:LRow[10],FieldName[11]:LRow[11],FieldName[12]:LRow[12],
                     FieldName[13]:LRow[13],FieldName[14]:LRow[14],FieldName[15]:LRow[15],FieldName[16]:LRow[16],
                     "Tag":"Account_detail"})
    BucketName.upsert("2154346975888900",{'Deposite': 553000})

```

[top](#top)

##### Query
1.First:
```python
  from couchbase.views.params import Query
  q = Query()
  q.limit = 100 # Limit to 5 results
  q.group_level=1
  BucketName = Bucket('couchbase://IP/BucketName',password='Pass') 
  rows = BucketName.query('Accounts', 'Account_Days',group_level=2,limit=5)
  for row in rows: print row
```

[top](#top)
# Oracle
##### Oracle-Connection
1. with cx_Oracle:
```python
  import cx_Oracle
  import os
  import csv
  ip = 'SomeThing'
  port = 1521
  SID = 'SomeThing'
  dsn_tns = cx_Oracle.makedsn(ip, port, SID)
  db = cx_Oracle.connect('UserName', 'Password', dsn_tns[, encoding = "UTF-8", nencoding = "UTF-8"])
```

##### Oracle-Data Insertion
##### Oracle-Query
1. with cx_Oracle:
```python
  curs = db.cursor()
  curs.execute("SELECT * FROM  ....")
  print (curs.description)
  i=0
  for row in curs:
      print (row)
      i+=1 {P
      if i>=10: break
```
[top](#top)

# Access DB
### Convert 2 Csv
1- you need [mbtools](https://github.com/brianb/mdbtools) on OS
2- `process.run` Package on Python
3- below code extract all Tables's of MDB Database:
```python
  import os, sys, subprocess # the subprocess module is new in python v 2.4
  DATABASE = sys.argv[1]
  table_names = subprocess.Popen(["mdb-tables", "-1", DATABASE],stdout=subprocess.PIPE).communicate()[0]
  tables = table_names.splitlines()
  for table in tables:
    if table != '':
      filename = DATABASE + table.replace(" ","_") + ".csv"
      file = open(filename, 'w')
      print("Dumping " + table)
      contents = subprocess.Popen(["mdb-export", DATABASE, table],stdout=subprocess.PIPE).communicate()[0]
      file.write(contents)
      file.close()
```
4- if you have multiple mdb file, could use this code:
```vala
  find . -name \*.mdb -exec python ./YourScript.py {} \;
```

[top](#top)
