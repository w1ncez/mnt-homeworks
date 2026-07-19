# Ansible Role: Lighthouse

Роль устанавливает Lighthouse — веб-интерфейс для ClickHouse.

---

## ⚙️ Возможности

- Установка Lighthouse
- Настройка подключения к ClickHouse
- Развёртывание через Nginx

---

## 📥 Переменные

```yaml
lighthouse_host: localhost
lighthouse_port: 80

clickhouse_host: localhost
clickhouse_port: 8123
