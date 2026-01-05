# N8N Полное развертывание для self hosting and tunel

## Если есть проблемы

### Проверьте создан ли пользователь n8n_user в PostgreSQL:

```
docker exec myconf-postgres-1 psql -U n8n_admin -d n8n -c "
CREATE USER n8n_user WITH PASSWORD 'PASSWORd';
GRANT ALL PRIVILEGES ON DATABASE n8n TO n8n_user;
GRANT CREATE ON SCHEMA public TO n8n_user;
ALTER USER n8n_user WITH CREATEDB;
"
```

Перезапустите n8n:

```
docker-compose restart n8n
```

### Дайте права скрипту init-data.sh:

```
chmod +x init-data.sh
```