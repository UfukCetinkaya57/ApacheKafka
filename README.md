# Kafka Producer/Consumer Console Uygulaması

Bu proje, **.NET Core** kullanarak bir Kafka Producer ve Consumer uygulamasını göstermektedir. Proje, Docker ve Kafka kullanılarak oluşturulmuştur ve çoklu broker desteği ile Kafka UI entegrasyonunu içermektedir.

## Gereksinimler

- **Docker** ve **Docker Compose** bilgisayarınıza yüklü olmalıdır.
- **.NET Core SDK** (>= 8.0) yüklü olmalıdır.
- Kafka hakkında temel bilgilere (Producer, Consumer, Topic, Partition gibi) sahip olmalısınız.

## Başlarken

### 1. Repozitory'yi Klonlayın

İlk olarak projeyi yerel bilgisayarınıza klonlayın.

```bash
git clone <repository-url>
cd <repository-folder>
```

### 2. Docker Compose Yapılandırması

Bu proje, Kafka broker'larını, Zookeeper'ı ve Kafka UI'yi kurmak için Docker Compose kullanır. İki farklı Docker Compose dosyası bulunmaktadır:

- **docker-compose.yml** (Tek broker kurulumu)
- **docker-compose-cluster.yml** (Çoklu broker'lı küme kurulumu)

#### Tek Broker Kurulumu

Kafka'yı tek bir broker ile başlatmak için:

```bash
docker-compose up -d
```

#### Çoklu Broker Kümesi Kurulumu

Üç broker ile bir Kafka kümesi başlatmak için:

```bash
docker-compose -f docker-compose-cluster.yml up -d
```

Bu komut, farklı portlarda üç Kafka broker'ı oluşturacaktır:
- **Broker 1**: `localhost:7000`
- **Broker 2**: `localhost:7001`
- **Broker 3**: `localhost:7002`

### 3. Kafka UI Kurulumu

Projede Kafka UI ile Kafka konularını yönetmek ve gözlemlemek için bir arayüz bulunmaktadır. Kafka UI, `http://localhost:8080` adresinden erişilebilir olacak şekilde yapılandırılmıştır.

### 4. Kafka Üretici ve Tüketici Çalıştırma

#### Kafka Producer (Üretici)

Producer, Kafka'ya mesaj göndermek için kullanılır. Aşağıdaki adımları izleyerek Kafka Producer'ı çalıştırabilirsiniz:
```bash
dotnet run --project Kafka.Producer
```

Bu komut, Kafka Producer'ı çalıştıracak ve tanımlı konulara mesaj gönderecektir.

#### Kafka Consumer (Tüketici)

Consumer, Kafka'daki mesajları dinleyip işlemek için kullanılır. Aşağıdaki komut ile Kafka Consumer'ı çalıştırabilirsiniz:

```bash
dotnet run --project Kafka.Consumer
```


Bu komut, tanımlı Kafka konularından mesajları dinleyecektir.

### 5. Örnek Mesaj Gönderme ve Alma

Projede hem basit hem de karmaşık mesajlar Kafka'ya gönderilebilir ve tüketilebilir. Mesajlar Kafka'ya `topicName` değişkeni ile tanımlanan konuya gönderilecek ve Consumer tarafından bu konu dinlenerek mesajlar işlenecektir.

- **Basit Mesaj**: `KafkaService.SendSimpleMessageWithNullKey`
- **Karmaşık Mesaj (Header ile)**: `KafkaService.SendComplexMessageWithIntKeyAndHeader`

### 6. Çoklu Broker Kurulumu ve Kafka UI Entegrasyonu

Çoklu broker kurulumunda Kafka'nın üç broker'lı bir kümede nasıl çalıştığını gözlemleyebilirsiniz. Ayrıca Kafka UI üzerinden broker'ları ve mesajları izleyebilirsiniz. Kafka UI ile şu işlemleri yapabilirsiniz:

- **Konu Yönetimi**: Konu oluşturma, silme, güncelleme.
- **Mesaj İzleme**: Gönderilen ve alınan mesajları gözlemleme.
- **Küme Yönetimi**: Broker durumlarını gözlemleme ve yönlendirme.

Kafka UI'ye erişmek için tarayıcınızda şu URL'yi kullanın:
 `http://localhost:8080`


