# Store Management System

## Resources

- Products
- Orders
- Customers

## Products Endpoints

GET /products
GET /products/{id}
POST /products
PUT /products/{id}
DELETE /products/{id}

## Orders Endpoints

GET /orders
GET /orders/{id}
POST /orders
PUT /orders/{id}
DELETE /orders/{id}

## Customers Endpoints

GET /customers
GET /customers/{id}
POST /customers
PUT /customers/{id}
DELETE /customers/{id}

## Status Codes

200 - OK
201 - Created
400 - Bad Request
404 - Not Found
409 - Conflict
422 - Unprocessable Entity
500 - Internal Server Error

# Products API

## 1. GET /products

دریافت لیست محصولات.

موفق:
200 OK

خطا:
404 Not Found


## 2. GET /products/{id}

دریافت یک محصول مشخص.

موفق:
200 OK

اگر محصول وجود نداشت:
404 Not Found


## 3. POST /products

ایجاد محصول جدید.

اطلاعات ورودی:
- name
- price
- stock

موفق:
201 Created

اطلاعات اشتباه:
400 Bad Request

محصول تکراری:
409 Conflict


## 4. PUT /products/{id}

ویرایش محصول.

اطلاعات ورودی:
- name
- price
- stock

موفق:
200 OK

اگر محصول وجود نداشت:
404 Not Found


## 5. DELETE /products/{id}

حذف محصول.

موفق:
200 OK

اگر محصول وجود نداشت:
404 Not Found
