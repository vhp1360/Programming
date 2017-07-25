<div dir="rtl">بنام خدا</div>
#### top

- [Couchbase](#couchbase)
  - [Connection](#connection)
  - [Data Insertion](#data-insertion)
  - [Query](#query)


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
