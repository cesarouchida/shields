SERVER=broker:29092
TOPIC=topico_teste

create:
	bin/kafka-topics.sh --create --bootstrap-server $(SERVER) --topic $(TOPIC) --partitions 1 --replication-factor 1

consumer: create schema
	sleep 3
	bin/kafka-console-consumer.sh --bootstrap-server $(SERVER) --topic $(TOPIC) --from-beginning

producer:
	bin/kafka-console-producer.sh --broker-list $(SERVER) --topic $(TOPIC)

schema: 
	curl -X POST -H "Content-Type: application/vnd.schemaregistry.v1+json" \
    --data '{"schema": "{\"type\":\"record\",\"name\":\"User\",\"fields\":[{\"name\":\"name\",\"type\":\"string\"},{\"name\":\"age\",\"type\":\"int\"}]}"}' \
    http://localhost:8081/subjects/my-topic-value/versions