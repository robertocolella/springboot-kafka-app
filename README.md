# Spring Boot Kafka Application

This is a Spring Boot application with Kafka integration.

## Description

The Spring Boot Kafka application allows sending and receiving messages via Apache Kafka. It includes a REST controller to send messages to a Kafka topic and a service to produce messages. The application demonstrates how to integrate Spring Boot with Kafka to build a messaging system. It provides endpoints to publish messages to a Kafka topic and consumes messages from the same topic, logging them to the console.

## Prerequisites

- Java 17
- Apache Maven
- Apache Kafka

## Getting Started

1. Clone the repository:
    ```sh
    git clone https://github.com/your-repo/springboot-kafka-app.git
    cd springboot-kafka-app
    ```

2. Build the project:
    ```sh
    mvn clean install
    ```

3. Run the application:
    ```sh
    mvn spring-boot:run
    ```

## Configuration

The application can be configured using the `application.properties` file located in the `src/main/resources` directory.

## Project Structure

- `src/main/java`: Contains the main application code.
- `src/main/resources`: Contains configuration files.
- `src/test/java`: Contains test cases.

## Usage

1. Start Kafka server:
    ```sh
    kafka-server-start.sh /usr/local/etc/kafka/server.properties
    ```

2. Produce messages to a topic:
    ```sh
    kafka-console-producer.sh --broker-list localhost:9092 --topic test
    ```

3. Consume messages from a topic:
    ```sh
    kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic test --from-beginning
    ```

## Docker Compose

To start Kafka and Zookeeper using Docker Compose:
1. Ensure Docker and Docker Compose are installed.
2. Run the following command:
    ```sh
    docker-compose up
    ```

## Testing

To run the tests:
1. Execute the following command:
    ```sh
    mvn test
    ```

## Testing with Curl

To test the application endpoints using `curl`:

1. Send a message to Kafka:
    ```sh
    curl -X POST -H "Content-Type: application/json" -d '{"message":"Hello, Kafka!"}' http://localhost:8080/api/v1/messages
    ```

2. Check the application logs to verify the message was sent successfully.

## Verifying Messages on Kafka

To verify the messages on Kafka, you can use the following commands:

1. Start the Kafka consumer to read messages from the topic:
    ```sh
    kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic test --from-beginning
    ```

2. Produce a message to the topic using the Kafka producer:
    ```sh
    kafka-console-producer.sh --broker-list localhost:9092 --topic test
    ```

3. Type your message and press Enter. The message should appear in the consumer console.

## Dependencies

- Spring Boot Starter
- Spring Boot Starter Web
- Spring Kafka
- Spring Boot Starter Test

## Contributing

1. Fork the repository.
2. Create a new branch (`git checkout -b feature-branch`).
3. Make your changes.
4. Commit your changes (`git commit -am 'Add new feature'`).
5. Push to the branch (`git push origin feature-branch`).
6. Create a new Pull Request.

## License

This project is licensed under the MIT License.