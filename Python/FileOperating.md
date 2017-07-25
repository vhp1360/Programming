<div dir="rtl">بنام خدا</div>

- [Csv](#csv)







### Csv
- csv to json:
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
