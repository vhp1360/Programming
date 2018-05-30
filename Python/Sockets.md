<div dir=rtl>بنام خدا</div>

###### top
- [Send Data](#send-data)
- [Receive Data](##receive-data)



### Send Data
- to port:
```python
  import socket
  s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
  s.connect(('IP', 2110))
  for i in Df:
    s.send(','.join(i.asDict().values()).encode('utf-8')+'\n'.encode('utf-8'))
    print(i)
  s.close()
```

### Receive Data
- from Port:
```python
  import socket
  with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.bind((socket.gethostname(), 2110))
    s.listen(1)
    conn, addr = s.accept()
    with conn:
      print('Connected by', addr)
      while True:
        data = conn.recv(1001)
        if not data: break
        print(data.decode('utf-8'))
```
