# Ansible: ClickHouse + Vector + Lighthouse

Репозиторий предназначен для развёртывания системы сбора и анализа логов:

- ClickHouse — хранение данных  
- Vector — сбор и доставка логов  
- Lighthouse — веб-интерфейс  

---

## 📦 Используемые роли

```yaml
- name: clickhouse 
  src: git@github.com:AlexeySetevoi/ansible-clickhouse.git
  version: "1.13"

- name: vector
  src: git@github.com:w1ncez/vector-role.git
  version: "1.0.0"

- name: lighthouse
  src: git@github.com:w1ncez/lighthouse-role.git
  version: "1.0.0"
