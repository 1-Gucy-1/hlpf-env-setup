# hlpf-env-setup

- Name: Кривенда Вероніка Ігорівна
- Group: Група 232/2

# Практичне заняття №4 — DTO + class-validator + Pipes

## Структура репозиторію

.
├── src/
│ ├── categories/
│ │ ├── dto/
│ │ │ ├── create-category.dto.ts
│ │ │ └── update-category.dto.ts
│ │ ├── category.entity.ts
│ │ ├── categories.module.ts
│ │ ├── categories.service.ts
│ │ └── categories.controller.ts
│ ├── products/
│ │ ├── dto/
│ │ │ ├── create-product.dto.ts
│ │ │ └── update-product.dto.ts
│ │ ├── product.entity.ts
│ │ ├── products.module.ts
│ │ ├── products.service.ts
│ │ └── products.controller.ts
│ ├── common/
│ │ └── pipes/
│ │ └── trim.pipe.ts
│ ├── migrations/
│ ├── data-source.ts
│ ├── main.ts
│ └── app.module.ts
├── Dockerfile
├── docker-compose.yml
└── README.md

### Запуск проекту

cp .env.example .env
docker compose up --build

### Тест валідації — порожнє ім'я категорії

Invoke-RestMethod : {"message":["name must be longer than or equal to 2 characters"],"error":"Bad Request","statusCode"
:400}
At line:1 char:1

- Invoke-RestMethod -Uri "http://localhost:3000/api/categories" `

### Тест валідації — від'ємна ціна продукту

Invoke-RestMethod : {"message":["price must not be less than 0.01"],"error":"Bad Request","statusCode":400}
At line:1 char:1

- Invoke-RestMethod -Uri "http://localhost:3000/api/products" `

### Тест валідації — зайве поле

Invoke-RestMethod : {"message":["property isAdmin should not exist"],"error":"Bad Request","statusCode":400}
At line:1 char:1

- Invoke-RestMethod -Uri "http://localhost:3000/api/categories" `

### Тест TrimPipe

id name description createdAt

---

18 Trimmed123 2026-04-30T08:50:30.419Z

### Тест валідне створення продукту

id : 4
name : iPhone 16
description :
price : 999,99
stock : 50
isActive : True
createdAt : 2026-04-30T08:50:59.382Z
updatedAt : 2026-04-30T08:50:59.382Z
