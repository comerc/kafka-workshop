# Интенсив «Kafka за 90 минут»

[![Sponsored by SberMarket Tech](images/sbermarket-tech-logo.svg)](https://sbermarket.ru)

Интенсив «Kafka за 90 минут» состоит из двух частей: теории и практики. Теория поможет составить ментальную модель Kafka, а практика — попробовать инструмент в действии и получить набор готовых конфигураций для применения их в своих лабораторных и тестовых средах на работе.

## Теория

### Содержание

- Расскажем о сценариях использования Kafka.
- Узнаем, что такое консумер, продюсер и брокер.
- Разберём, как связаны топики, партиции и сегменты.
- Поговорим о формате сообщений в Kafka.
- Расскажем о лидере партиций, репликации данных и партицировании.
- Поговорим о гарантиях доставки сообщений и идемпотентности.
- Выясним, что такое консумер-группа и ребалансировка консумеров в ней.

**Длительность**: 45 минут

### Материал

- [Презентация](docs/theory/slides.pdf)
- [Расшифровка](docs/theory/speaker-notes.md)

## Практика

### Содержание

- Склонируем репозиторий с конфигурацией Docker Compose.
- Подберём конфигурации топиков и создадим их.
- Настроим и запустим продюсер.
- Настроим и запустим консумер.
- Изменим оффсет для консумер-группы.
- Посмотрим на основные показатели в Grafana.

**Длительность**: 30 минут

### Материал

- [Перед началом](docs/guide/001-intro.md)
- [Запуск кластера](docs/guide/002-getting-started.md)
- [Создание топика](docs/guide/003-topics-and-partitions.md)
- [Работа продюсера](docs/guide/004-producers.md)
- [Работа консумера](docs/guide/005-consumers.md)
- [Наблюдаемость Kafka](docs/guide/006-observability.md)

## Бонус-трек

### Материалы

- [Kafka: настройка клиента](docs/cheatsheet/000-kafka-client-setup.md)
- [Kafka: чтение и запись в топик](docs/cheatsheet/001-kafka-consume-or-produce.md)
- [Kafka: управление топиками и партициями](docs/cheatsheet/002-kafka-topics-and-partitions.md)
- [Kafka: управление консумер-группами](docs/cheatsheet/003-kafka-consumer-groups.md)
- [Kafka: управление доступами к топикам](docs/cheatsheet/004-kafka-acl.md)

## Confluent Kafka with JMX?

1. I set up Kafka using https://docs.confluent.io/platform/current/quickstart/ce-docker-quickstart.html#ce-docker-quickstart. This launches Kafka with JMX installed.

2. This installation provides Confluent Control Center so you can view metrics there. However I wanted the raw metrics exposed by JMX so I proceeded to the next steps.

3. I installed VisualVM from here https://visualvm.github.io/download.html. (You can also use jconsole available in the JAVA/jdk/bin folder installed in your local m/c but I had connectivity issues running jconsole against the container JMX.)

4. Install the VisualVM-MBeans plugin in VisualVM.

5. Add a JMX connection using the KAFKA_JMX_HOSTNAME:KAFKA_JMX_PORT values from your docker-compose.yml in Step 1.

Bingo you can see the metrics from Confluent Kafka running on the container!

-- OR --

[Create A Kafka Multi-Broker Cluster](https://docs.bitnami.com/google-templates/infrastructure/kafka/administration/create-cluster/) by bitnami.
