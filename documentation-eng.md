# Kafka Producer/Consumer Console Application

This document provides deeper insights into the architecture and functionality of the Kafka-based Producer/Consumer system built using **.NET Core**.

## Project Overview

This project demonstrates how to build a distributed system using **Kafka** for real-time messaging. It includes Kafka Producers that send messages to Kafka topics and Consumers that process these messages.

### Kafka Use Cases

1. **Message Production:**
   - The **Producer** sends various types of messages to Kafka topics. Examples include simple messages, complex messages with headers, and timestamped messages.

2. **Message Consumption:**
   - The **Consumer** listens to the Kafka topics and processes incoming messages. The system handles simple and complex messages, as well as messages with specific headers or from designated partitions.

### Technologies Used

- **Kafka**: Distributed messaging system used for sending and consuming messages.
- **.NET Core**: Backend API and messaging logic built with .NET Core.
- **Docker & Docker Compose**: Containerization for Kafka, Zookeeper, and UI management.
- **Confluent Kafka .NET**: Kafka client for building Producer and Consumer.

### System Architecture

- **Event-Driven Architecture**: The system is based on an event-driven architecture where events (messages) are produced and consumed asynchronously.
- **Modular Design**: The project is modular, separating the Producer and Consumer logic into different services.
- **Kafka Cluster**: You can run the system with a single Kafka broker or a multi-broker Kafka cluster, allowing for high availability and fault tolerance.

## Key Components

### Kafka Producer

- **Simple Messages**: Sends plain text messages to Kafka topics.
- **Complex Messages with Headers**: Sends messages with additional metadata (headers) and complex objects as payloads.

### Kafka Consumer

- **Simple Message Consumption**: Consumes plain text messages.
- **Complex Message Processing**: Consumes complex objects and processes metadata included in message headers.

## Running Kafka with Docker

The project includes Docker Compose files for running Kafka:

- **Single Broker**:
    ```
    docker-compose up -d
    ```

- **Multi-Broker Cluster**:
    ```
    docker-compose -f docker-compose-cluster.yml up -d
    ```

## Project Flow

1. **Message Production**:
   - The Producer sends messages to Kafka topics such as `order.created.event`.
   
2. **Message Consumption**:
   - The Consumer listens to Kafka topics and processes the incoming messages asynchronously.
