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
# Customers API

## 1. GET /customers

دریافت لیست مشتریان.

موفق:
200 OK

## 2. GET /customers/{id}

دریافت اطلاعات یک مشتری.

موفق:
200 OK

اگر مشتری وجود نداشت:
404 Not Found

## 3. POST /customers

ثبت مشتری جدید.

اطلاعات ورودی:
- name
- email
- phone

موفق:
201 Created

اطلاعات اشتباه:
400 Bad Request

ایمیل تکراری:
409 Conflict

## 4. PUT /customers/{id}

ویرایش اطلاعات مشتری.

اطلاعات ورودی:
- name
- email
- phone

موفق:
200 OK

اگر مشتری وجود نداشت:
404 Not Found

## 5. DELETE /customers/{id}

حذف مشتری.

موفق:
200 OK

اگر مشتری وجود نداشت:
404 Not Found

# Project Tasks

## Products Tasks

- Add a new product
- View all products
- View product details
- Update product information
- Delete a product

## Orders Tasks

- Create a new order
- View all orders
- View order details
- Update an order
- Cancel an order

## Customers Tasks

- Register a new customer
- View all customers
- View customer details
- Update customer information
- Delete a customer


# User Stories

## Products

As a store manager,
I want to add products,
so that I can manage store inventory.

## Orders

As a store manager,
I want to manage customer orders,
so that I can track sales.

## Customers

As a store manager,
I want to manage customer information,
so that I can keep customer records.

# Rate Limiting & User Quotas

## Guest User
- Maximum 20 requests per minute

## Normal User
- Maximum 60 requests per minute

## Admin User
- Maximum 120 requests per minute

## Rate Limit Response

Status Code:
429 Too Many Requests

Response:

{
  "status": 429,
  "message": "Too many requests",
  "error": "Rate limit exceeded",
  "retryAfter": 60
}

## Rate Limit Headers

- X-RateLimit-Limit
- X-RateLimit-Remaining
- X-RateLimit-Reset
- Retry-After
# Error Handling

## Standard Error Response

{
  "status": 404,
  "error": "PRODUCT_NOT_FOUND",
  "message": "Product not found",
  "details": null
}

## Error Codes

400 - BAD_REQUEST
401 - UNAUTHORIZED
403 - FORBIDDEN
404 - NOT_FOUND
409 - CONFLICT
422 - VALIDATION_ERROR
429 - RATE_LIMIT_EXCEEDED
500 - INTERNAL_SERVER_ERROR

## Error Handling Rules

- All errors must have a consistent response format.
- Error messages must be clear.
- Internal server details must not be exposed.
- Validation errors must identify invalid fields.
- Every error must return the correct HTTP status code.

# API Headers

## Request Headers

Content-Type: application/json
Accept: application/json
Authorization: Bearer TOKEN
User-Agent: Store-Management-Client

## Response Headers

Content-Type: application/json
X-RateLimit-Limit
X-RateLimit-Remaining
X-RateLimit-Reset
Retry-After

## Header Rules

- API uses JSON format.
- Content-Type must be application/json for JSON request bodies.
- Accept must be application/json.
- Protected endpoints require Authorization.
- Rate limit information must be returned in response headers.
# Pagination, Filtering & Sorting

## Pagination

Endpoint:
GET /products?page=1&limit=10

Parameters:
- page: Current page number
- limit: Number of products per page

Default values:
- page = 1
- limit = 10

## Filtering

Available filters:

- minPrice: Minimum product price
- maxPrice: Maximum product price
- inStock: Product availability

Examples:

GET /products?minPrice=100&maxPrice=500

GET /products?inStock=true

## Sorting

Parameters:

- sortBy: Field to sort by
- order: asc or desc

Example:

GET /products?sortBy=price&order=asc

## Pagination Response

- currentPage
- limit
- totalProducts
- totalPages

## Rules

- Page must be greater than zero.
- Limit must be between 1 and 100.
- Invalid query parameters return 400 Bad Request.
- Empty product lists return 200 OK with an empty array.
