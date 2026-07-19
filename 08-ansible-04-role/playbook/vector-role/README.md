# Ansible Role: Vector

Роль устанавливает и настраивает Vector для сбора и отправки логов.

---

## ⚙️ Возможности

- Установка Vector
- Сбор логов (journald, files)
- Трансформация логов
- Отправка в ClickHouse

---

## 📥 Переменные

```yaml
vector_config:
  sources:
    syslog:
      type: journald

  transforms:
    remap_logs:
      type: remap
      inputs: ["syslog"]
      source: |
        .host = get_hostname!()

  sinks:
    clickhouse:
      type: clickhouse
      inputs: ["remap_logs"]
      endpoint: "http://localhost:8123"
      database: "logs"
      table: "logs"
      auth:
        strategy: basic
        user: "logs_user"
        password: "logs_password"
