# Kafka Producer/Consumer Konsol Uygulaması

Bu proje, **.NET Core** kullanarak bir Kafka Producer ve Consumer uygulamasını göstermektedir. Proje, dağıtık bir ortamda gerçek zamanlı mesaj akışını Kafka ile nasıl yönetebileceğinizi gösterir.

## Hızlı Başlangıç

### Gereksinimler

- **Docker** & **Docker Compose**
- **.NET Core SDK** (>= 8.0)

### Kurulum

1. Repository'yi klonlayın:
    ```
    git clone <repository-url>
    cd <repository-folder>
    ```

2. Docker ile Kafka servislerini başlatın:
    ```
    docker-compose up -d
    ```

3. Producer ve Consumer projelerini çalıştırın:
    ```
    dotnet run --project Kafka.Producer
    dotnet run --project Kafka.Consumer
    ```

4. Kafka UI'ye erişin:
    Konuları yönetmek ve mesajları görmek için Kafka UI'ye şu adresten ulaşabilirsiniz:
    ```
    http://localhost:8080
    ```

Daha fazla teknik bilgi için [documentation.md](./documentation.md) dosyasına göz atabilirsiniz.
