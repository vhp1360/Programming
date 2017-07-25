<div dir=rtl>بنام خدا</div>

###### top

- [Kafka](#kafka)



# Kafka
- [Packages](#packages)

## Packages
- kafka-python Package:
  1. Hot Send Data to consumer:
  ```python
    from kafka import KafkaProducer
    from kafka.errors import KafkaError
    producer = KafkaProducer(bootstrap_servers='ServeAdr:Port')
    # Df  is list of dict
    for i in Df:
      producer.send('hamrah', (','.join(i.asDict().values())).encode('utf-8'))
  ```
