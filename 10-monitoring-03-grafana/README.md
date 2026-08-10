# Домашнее задание к занятию 14 «Средство визуализации Grafana» - Винцентини С.Г.

## Задание повышенной сложности

**При решении задания 1** не используйте директорию [help](./help) для сборки проекта. Самостоятельно разверните grafana, где в роли источника данных будет выступать prometheus, а сборщиком данных будет node-exporter:

- grafana;
- prometheus-server;
- prometheus node-exporter.

За дополнительными материалами можете обратиться в официальную документацию grafana и prometheus.

В решении к домашнему заданию также приведите все конфигурации, скрипты, манифесты, которые вы 
использовали в процессе решения задания.

> [docker-compose.yaml](https://github.com/w1ncez/mnt-homeworks/blob/main/10-monitoring-03-grafana/docker-compose.yaml) <br>
> [prometheus.yml](https://github.com/w1ncez/mnt-homeworks/blob/main/10-monitoring-03-grafana/prometheus.yml)

**При решении задания 3** вы должны самостоятельно завести удобный для вас канал нотификации, например, Telegram или email, и отправить туда тестовые события.

В решении приведите скриншоты тестовых событий из каналов нотификаций.

><img width="810" height="396" alt="image" src="https://github.com/user-attachments/assets/63a654cf-910b-46cb-97e7-77e7293a9795" />


## Обязательные задания

### Задание 1

1. Используя директорию [help](./help) внутри этого домашнего задания, запустите связку prometheus-grafana.
2. Зайдите в веб-интерфейс grafana, используя авторизационные данные, указанные в манифесте docker-compose.
3. Подключите поднятый вами prometheus, как источник данных.
4. Решение домашнего задания — скриншот веб-интерфейса grafana со списком подключенных Datasource.

> <img width="3438" height="713" alt="image" src="https://github.com/user-attachments/assets/3ca33353-8840-4728-b8a1-e559b71d8b17" />


## Задание 2

Изучите самостоятельно ресурсы:

1. [PromQL tutorial for beginners and humans](https://valyala.medium.com/promql-tutorial-for-beginners-9ab455142085).
2. [Understanding Machine CPU usage](https://www.robustperception.io/understanding-machine-cpu-usage).
3. [Introduction to PromQL, the Prometheus query language](https://grafana.com/blog/2020/02/04/introduction-to-promql-the-prometheus-query-language/).

Создайте Dashboard и в ней создайте Panels:

- утилизация CPU для nodeexporter (в процентах, 100-idle);
- CPULA 1/5/15;
- количество свободной оперативной памяти;
- количество места на файловой системе.

Для решения этого задания приведите promql-запросы для выдачи этих метрик, а также скриншот получившейся Dashboard.

> Утилизация CPU (в процентах, 100 - idle) <br>
> ``` 100 - (avg by (instance) (rate(node_cpu_seconds_total{mode="idle"}[5m])) * 100) ```

> CPU Load Average 1/5/15 <br>
```node_load1```<br>
 ```node_load5```<br>
 ```node_load15```<br>
 
>Количество свободной оперативной памяти <br>
>```node_memory_MemAvailable_bytes```

> Количество свободного места на файловой системе <br>
> ```node_filesystem_free_bytes{mountpoint="/"}```

<img width="3431" height="864" alt="image" src="https://github.com/user-attachments/assets/2533d6da-3bd0-41c2-9ccf-b574c3f9a414" />


## Задание 3

1. Создайте для каждой Dashboard подходящее правило alert — можно обратиться к первой лекции в блоке «Мониторинг».
2. В качестве решения задания приведите скриншот вашей итоговой Dashboard.

> <img width="3409" height="1225" alt="image" src="https://github.com/user-attachments/assets/1c2bf9cf-e7f3-471a-9e6a-6be2affc27f6" />


## Задание 4

1. Сохраните ваш Dashboard.Для этого перейдите в настройки Dashboard, выберите в боковом меню «JSON MODEL». Далее скопируйте отображаемое json-содержимое в отдельный файл и сохраните его.
2. В качестве решения задания приведите листинг этого файла.

> [dashboard.json](https://github.com/w1ncez/mnt-homeworks/blob/main/10-monitoring-03-grafana/dashboard.json)

---

### Как оформить решение задания

Выполненное домашнее задание пришлите в виде ссылки на .md-файл в вашем репозитории.

---
