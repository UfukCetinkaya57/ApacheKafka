# Kafka Producer/Consumer Konsol Uygulaması - Detaylı Dokümantasyon

Bu doküman, **.NET Core** kullanarak Kafka tabanlı Producer/Consumer sisteminin mimarisi ve işlevselliği hakkında daha derinlemesine bilgi sağlar.

## Proje Özeti

Bu proje, **Kafka** kullanarak gerçek zamanlı mesajlaşma sistemleri nasıl oluşturulacağını gösterir. Kafka üreticileri, Kafka konularına mesaj gönderirken, tüketiciler bu mesajları işler.

### Kafka'nın Kullanım Alanları

1. **Mesaj Üretimi:**
   - **Producer** çeşitli türde mesajlar gönderir. Basit mesajlar, başlıklı karmaşık mesajlar ve zaman damgalı mesajlar gibi farklı mesaj türlerini Kafka'ya gönderir.

2. **Mesaj Tüketimi:**
   - **Consumer** Kafka konularını dinler ve gelen mesajları işler. Basit ve karmaşık mesajları, belirli başlıklarla veya belirli bölümlerden gelen mesajları işleyebilir.

### Kullanılan Teknolojiler

- **Kafka**: Mesaj gönderimi ve tüketimi için kullanılan dağıtık mesajlaşma sistemi.
- **.NET Core**: API ve mesajlaşma mantığı **.NET Core** ile geliştirilmiştir.
- **Docker & Docker Compose**: Kafka, Zookeeper ve Kafka UI gibi servislerin container'lar ile yönetimi.
- **Confluent Kafka .NET**: Kafka üretici ve tüketici oluşturmak için kullanılan .NET kütüphanesi.

### Sistem Mimarisi

- **Olay Tabanlı Mimari (EDA):** Sistem olay tabanlı mimariye dayanır. Olaylar (mesajlar) producer tarafından üretilir ve consumer tarafından işlenir.
- **Modüler Tasarım:** Proje, producer ve consumer mantığını farklı servislerde ayırarak modüler bir yapı sunar.
- **Kafka Kümesi:** Tek broker veya çoklu broker Kafka kümesiyle çalıştırılabilir, bu da yüksek kullanılabilirlik ve hata toleransı sağlar.

## Temel Bileşenler

### Kafka Producer

- **Basit Mesajlar:** Kafka konularına düz metin mesajları gönderir.
- **Başlıklı Karmaşık Mesajlar:** Ek meta verilerle (başlıklar) ve karmaşık nesnelerle mesaj gönderir.

### Kafka Consumer

- **Basit Mesaj Tüketimi:** Düz metin mesajlarını tüketir.
- **Karmaşık Mesaj İşleme:** Karmaşık nesneleri ve mesaj başlıklarındaki meta verileri işler.

## Docker ile Kafka'yı Çalıştırma

Projede Kafka'yı çalıştırmak için Docker Compose dosyaları bulunmaktadır:

- **Tek Broker**:
    ```
    docker-compose up -d
    ```

- **Çoklu Broker Kümesi**:
    ```
    docker-compose -f docker-compose-cluster.yml up -d
    ```

## Proje Akışı

1. **Mesaj Üretimi**:
   - Producer, `order.created.event` gibi Kafka konularına mesaj gönderir.
   
2. **Mesaj Tüketimi**:
   - Consumer, Kafka konularını dinler ve gelen mesajları asenkron olarak işler.
