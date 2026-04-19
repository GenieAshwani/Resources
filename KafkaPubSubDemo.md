# Kafka Pub/Sub Demo

This demo contains two simple Spring Boot apps:

- `kafka-publisher-demo`: publishes messages to Kafka using a REST API
- `kafka-subscriber-demo`: listens to the same topic and prints messages in the console

## Topic Used

Both apps use this topic:

```text
demo-messages
```

## Kafka Setup

Start Kafka first from the `KafkaProjects` folder:

```bash
docker-compose up -d
```

This starts:

- Zookeeper
- Kafka broker on `localhost:9092`

## App 1: Run Subscriber

Open a terminal in:

```text
KafkaProjects/kafka-subscriber-demo
```

Run:

```bash
mvn spring-boot:run
```

This app listens to the Kafka topic and logs received messages.

## App 2: Run Publisher

Open another terminal in:

```text
KafkaProjects/kafka-publisher-demo
```

Run:

```bash
mvn spring-boot:run
```

Publisher app runs on:

```text
http://localhost:8081
```

## Publish a Message

Use this request:

```bash
curl -X POST http://localhost:8081/api/messages -H "Content-Type: application/json" -d "{\"message\":\"Hello from publisher app\"}"
```

Expected result:

- publisher app sends the message to Kafka
- subscriber app prints the same message in its console

## Check Topic from Kafka Container

```bash
docker exec --interactive --tty kafka1 kafka-topics --bootstrap-server kafka1:19092 --list
docker exec --interactive --tty kafka1 kafka-console-consumer --bootstrap-server kafka1:19092 --topic demo-messages --from-beginning
```

## Important Note

The publisher app creates the topic automatically using a Spring `NewTopic` bean.
