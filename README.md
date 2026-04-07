# hlpf-env-setup

- Name: Кривенда Вероніка Ігорівна
- Group: Група 232/2

## Практичне заняття №3 — CRUD REST API для MiniShop

### Структура репозиторію

```
.
├── src/
│   ├── categories/
│   │   ├── category.entity.ts
│   │   ├── categories.module.ts
│   │   ├── categories.service.ts
│   │   └── categories.controller.ts
│   ├── products/
│   │   ├── product.entity.ts
│   │   ├── products.module.ts
│   │   ├── products.service.ts
│   │   └── products.controller.ts
│   ├── migrations/
│   │   ├── 1700000001-CreateTables.ts
│   │   └── <timestamp>-AddIsActiveToProducts.ts
│   ├── data-source.ts
│   └── app.module.ts
├── Dockerfile
├── docker-compose.yml
└── README.md
```

### Запуск проекту

```bash
cp .env.example .env
docker compose up --build
```

### API Endpoints

| Method | URL                 | Опис               |
| ------ | ------------------- | ------------------ |
| GET    | /api/categories     | Список категорій   |
| GET    | /api/categories/:id | Одна категорія     |
| POST   | /api/categories     | Створити категорію |
| PATCH  | /api/categories/:id | Оновити категорію  |
| DELETE | /api/categories/:id | Видалити категорію |
| GET    | /api/products       | Список продуктів   |
| GET    | /api/products/:id   | Один продукт       |
| POST   | /api/products       | Створити продукт   |
| PATCH  | /api/products/:id   | Оновити продукт    |
| DELETE | /api/products/:id   | Видалити продукт   |

### Перевірка міграцій

```text
 List of relations
 Schema |    Name    | Type  |  Owner
--------+------------+-------+----------
 public | categories | table | nestuser
 public | migrations | table | nestuser
 public | products   | table | nestuser
(3 rows)
```

### Тест створення категорії

```text
{
    "id":  1,
    "name":  "Electronics",
    "description":  "Gadgets and devices",
    "createdAt":  "2026-04-07T21:46:17.917Z"
}
```

### Тест створення продукту

```text
{
    "id":  1,
    "name":  "iPhone 15",
    "description":  null,
    "price":  999.99,
    "stock":  50,
    "isActive":  true,
    "category":  {
                     "id":  1
                 },
    "createdAt":  "2026-04-07T21:48:44.994Z",
    "updatedAt":  "2026-04-07T21:48:44.994Z"
}
```

### Тест отримання продуктів

```text
{
    "value":  [
                  {
                      "id":  1,
                      "name":  "iPhone 15",
                      "description":  null,
                      "price":  "999.99",
                      "stock":  50,
                      "isActive":  true,
                      "category":  {
                                       "id":  1,
                                       "name":  "Electronics",
                                       "description":  "Gadgets and devices",
                                       "createdAt":  "2026-04-07T21:46:17.917Z"
                                   },
                      "createdAt":  "2026-04-07T21:48:44.994Z",
                      "updatedAt":  "2026-04-07T21:48:44.994Z"
                  }
              ],
    "Count":  1
}
```

### Тест 404

```text
Invoke-RestMethod : {"message":"Product #999 not found","error":"Not Found","statusCode":404}
At line:1 char:1
+ Invoke-RestMethod `
+ ~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (System.Net.HttpWebRequest:HttpWebRequest) [Invoke-RestMethod], WebExc
   eption
    + FullyQualifiedErrorId : WebCmdletWebResponseException,Microsoft.PowerShell.Commands.InvokeRestMethodCommand
```
