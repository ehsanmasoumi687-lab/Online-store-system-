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
# Orders API

## 1. GET /orders

دریافت لیست سفارش‌ها.

موفق:
200 OK

اگر سفارشی وجود نداشت:
404 Not Found


## 2. GET /orders/{id}

دریافت یک سفارش مشخص.

موفق:
200 OK

اگر سفارش وجود نداشت:
404 Not Found


## 3. POST /orders

ایجاد سفارش جدید.

اطلاعات ورودی:
- customerId
- productId
- quantity

موفق:
201 Created

اطلاعات اشتباه:
400 Bad Request

اگر محصول وجود نداشت:
404 Not Found


## 4. PUT /orders/{id}

ویرایش سفارش.

اطلاعات ورودی:
- productId
- quantity

موفق:
200 OK

اگر سفارش وجود نداشت:
404 Not Found


## 5. DELETE /orders/{id}

لغو سفارش.

موفق:
200 OK

اگر سفارش وجود نداشت:
404 Not Found
