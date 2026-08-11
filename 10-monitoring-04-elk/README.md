# Домашнее задание к занятию 15 «Система сбора логов Elastic Stack» - Винцентини С.Г.

## Задание 1

Вам необходимо поднять в докере и связать между собой:

- elasticsearch (hot и warm ноды);
- logstash;
- kibana;
- filebeat.

Logstash следует сконфигурировать для приёма по tcp json-сообщений.

Filebeat следует сконфигурировать для отправки логов docker вашей системы в logstash.

В директории [help](./help) находится манифест docker-compose и конфигурации filebeat/logstash для быстрого 
выполнения этого задания.

Результатом выполнения задания должны быть:

- скриншот `docker ps` через 5 минут после старта всех контейнеров (их должно быть 5);
- скриншот интерфейса kibana;
- docker-compose манифест (если вы не использовали директорию help);
- ваши yml-конфигурации для стека (если вы не использовали директорию help).

><img width="2129" height="171" alt="image" src="https://github.com/user-attachments/assets/be675f55-ed6c-45f6-b074-0d552dc4defd" />
><img width="3433" height="1203" alt="image" src="https://github.com/user-attachments/assets/6ddc332f-e15d-4050-97eb-bdf08b7cbf34" />




## Задание 2

Перейдите в меню [создания index-patterns  в kibana](http://localhost:5601/app/management/kibana/indexPatterns/create) и создайте несколько index-patterns из имеющихся.

Перейдите в меню просмотра логов в kibana (Discover) и самостоятельно изучите, как отображаются логи и как производить поиск по логам.

В манифесте директории help также приведенно dummy-приложение, которое генерирует рандомные события в stdout-контейнера.
Эти логи должны порождать индекс logstash-* в elasticsearch. Если этого индекса нет — воспользуйтесь советами и источниками из раздела «Дополнительные ссылки» этого задания.

><img width="3429" height="1217" alt="image" src="https://github.com/user-attachments/assets/8362352b-e219-4211-9efc-5ccfdf8e310c" />
><img width="3426" height="1218" alt="image" src="https://github.com/user-attachments/assets/ef287fff-cf50-4699-8e27-9c3398e76136" />
><img width="3430" height="1209" alt="image" src="https://github.com/user-attachments/assets/602394a3-b2ca-493d-a732-14848f97ebc1" />
><img width="3410" height="1214" alt="image" src="https://github.com/user-attachments/assets/b6d9ca22-e292-410b-aaf7-912f5841f814" />



 
