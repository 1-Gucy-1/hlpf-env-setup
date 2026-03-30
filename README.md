# hlpf-env-setup

- Name: Кривенда Вероніка Ігорівна
- Group: Група 232/2

## Практичне заняття №2 — NestJS + PostgreSQL + Redis

## Структура репозиторію

````

├── src/              	# NestJS source code
├── Dockerfile
├── docker-compose.yml
├── .env.example      	# шаблон змінних оточення
└── README.md

## Запуск проекту
```bash
cp .env.example .env   # налаштувати значення
docker compose up --build
````

## Перевірка сервісів

```text
PS C:\Users\Nika\hlpf-env-setup> docker compose ps
NAME                        IMAGE                COMMAND                  SERVICE    CREATED        STATUS                   PORTS
hlpf-env-setup-postgres-1   postgres:16-alpine   "docker-entrypoint.s…"   postgres   46 hours ago   Up 2 minutes (healthy)   0.0.0.0:5432->5432/tcp
hlpf-env-setup-redis-1      redis:7-alpine       "docker-entrypoint.s…"   redis      46 hours ago   Up 2 minutes (healthy)   0.0.0.0:6379->6379/tcp
```

## Перевірка PostgreSQL

```text
 List of databases
   Name    |  Owner   | Encoding | Locale Provider |  Collate   |   Ctype    | ICU Locale | ICU Rules |   Access privileges
-----------+----------+----------+-----------------+------------+------------+------------+-----------+-----------------------
 nestdb    | nestuser | UTF8     | libc            | en_US.utf8 | en_US.utf8 |            |           |
 postgres  | nestuser | UTF8     | libc            | en_US.utf8 | en_US.utf8 |            |           |
 template0 | nestuser | UTF8     | libc            | en_US.utf8 | en_US.utf8 |            |           | =c/nestuser          +
           |          |          |                 |            |            |            |           | nestuser=CTc/nestuser
 template1 | nestuser | UTF8     | libc            | en_US.utf8 | en_US.utf8 |            |           | =c/nestuser          +
           |          |          |                 |            |            |            |           | nestuser=CTc/nestuser
(4 rows)
```

## Перевірка Redis

```text
PONG
```

## Перевірка застосунку

```text
```
<img width="251" height="185" alt="mdd" src="https://github.com/user-attachments/assets/bb828cf1-a4f1-4f67-899e-8b7589271e8f" />

## Логи NestJS

```text
app-1  | [Nest] 34  - 03/30/2026, 5:27:22 PM     LOG [NestFactory] Starting Nest application...
app-1  | [Nest] 34  - 03/30/2026, 5:27:24 PM     LOG [InstanceLoader] TypeOrmModule dependencies initialized +1831ms
app-1  | [Nest] 34  - 03/30/2026, 5:27:24 PM     LOG [InstanceLoader] TypeOrmCoreModule dependencies initialized +86ms
app-1  | [Nest] 34  - 03/30/2026, 5:27:24 PM     LOG [NestApplication] Nest application successfully started +9ms
```
