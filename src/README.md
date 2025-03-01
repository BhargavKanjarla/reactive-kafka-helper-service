# reactive-kafka-helper-service - Kafka consumer and producer Spring Boot


Sample project to show how to implement Reactive kafka consumer and producer in Spring Boot. With Spring Kafka.

Spring Boot version 2.3.9

## Config
- [ReactiveKafkaConsumerConfig](src/main/java/com/example/reactivekafkaconsumerandproducer/config/ReactiveKafkaConsumerConfig.java)
- [ReactiveKafkaProducerConfig](src/main/java/com/example/reactivekafkaconsumerandproducer/config/ReactiveKafkaProducerConfig.java)
- [application.properties](src/main/resources/application.properties)
- [pom.xml](pom.xml)

```properties
spring.kafka.bootstrap-servers=localhost:9200
# producer
spring.kafka.producer.key-serializer=org.apache.kafka.common.serialization.StringSerializer
spring.kafka.producer.value-serializer=org.springframework.kafka.support.serializer.JsonDeserializer
# consumer
spring.kafka.consumer.group-id=reactivekafkaconsumerandproducer

spring.kafka.consumer.auto-offset-reset=earliest
spring.kafka.consumer.key-deserializer=org.apache.kafka.common.serialization.StringDeserializer
spring.kafka.consumer.value-deserializer=org.springframework.kafka.support.serializer.JsonDeserializer
# json deserializer config
spring.kafka.properties.spring.json.trusted.packages=*
spring.kafka.consumer.properties.spring.json.use.type.headers=false
spring.kafka.consumer.properties.spring.json.value.default.type=com.example.reactivekafkaconsumerandproducer.dto.FakeConsumerDTO

# topic
FAKE_PRODUCER_DTO_TOPIC=fake_producer_dto_topic
FAKE_CONSUMER_DTO_TOPIC=fake_consumer_dto_topic
```

## Integration test
- [ReactiveConsumerServiceIntegrationTest](src/test/java/com/example/reactivekafkaconsumerandproducer/ReactiveConsumerServiceIntegrationTest.java)
- [ReactiveProducerServiceIntegrationTest](src/test/java/com/example/reactivekafkaconsumerandproducer/ReactiveProducerServiceIntegrationTest.java)