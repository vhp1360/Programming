<div dir="rtl">بنام خدا</div>

- [Csv](#csv)







### Csv
1. csv to json:
```python
  import csv

  import json

  CsvFile=open("FileName.csv",'r')

  JsonFile=open("JsonName.json",'w')

  FiledName=("ID",...)

  ReaderFile=csv.DictReader(CsvFile,FiledName)

  for Row in ReaderFile:

      json.dump(Row,JsonFile)

      JsonFile.write("\n")
```
2. Query to csv:
```python
  import csv
  with open('Sample.csv','w') as f:
    writer=csv.writer(f)
    writer.writerow([i[0] for i in curs.description])
    writer.writerows(curs.fetchall())
```
