# Kafka Cheatsheet

## List Topics
```sh
/opt/kafka/bin/kafka-topics.sh --bootstrap-server=localhost:9092 --list
```

## Describe all groups
```sh
/opt/kafka/bin/kafka-consumer-groups.sh --bootstrap-server=localhost:9092 --describe --all-groups
```