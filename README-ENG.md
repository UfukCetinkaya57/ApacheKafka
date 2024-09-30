# Kafka Producer/Consumer Console Application

This project demonstrates a Kafka Producer and Consumer implementation using **.NET Core**. It showcases how to manage real-time message streaming with Kafka in a distributed environment.

## Quick Start

### Prerequisites

- **Docker** & **Docker Compose**
- **.NET Core SDK** (>= 8.0)

### Installation

1. Clone the repository:
    ```
    git clone <repository-url>
    cd <repository-folder>
    ```

2. Start Kafka services with Docker:
    ```
    docker-compose up -d
    ```

3. Run the Producer and Consumer projects:
    ```
    dotnet run --project Kafka.Producer
    dotnet run --project Kafka.Consumer
    ```

4. Access Kafka UI:
    You can manage topics and view messages using Kafka UI at:
    ```
    http://localhost:8080
    ```

For detailed technical information, please refer to the [documentation-eng.md](./documentation-eng.md) file.
