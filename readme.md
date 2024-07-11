# Produtor e Consumidor Kafka com Go

Este repositório contém uma demonstração simples de um produtor e consumidor Kafka implementados em Go usando a biblioteca `sarama`.

### Para executar, siga os passos abaixo

```bash
git clone https://github.com/seuusuario/kafka-go-demo.git
cd kafka-go-demo
```

Instale a dependência:
```bash
go get -u github.com/IBM/sarama
```

Suba o Kafka e Zookeeper:
```bash
docker-compose up -d
```

Crie um tópico no Kafka:
```bash
docker-compose exec kafka kafka-topics.sh --create --topic meu-topico --partitions 1 --replication-factor 1 --bootstrap-server localhost:9092
```

Execute o consumidor:
```bash
go run consumer.go
```

Use o console producer do Kafka para enviar mensgens para o topico:
```bash
docker-compose exec kafka kafka-console-producer.sh --topic meu-topico --bootstrap-server localhost:9092
```

Execute o produtor par enviar uma mensagem simples:
```bash
go run producer.go
```