# Test Cases - Store Management System

## Products Tests

| ID | Test Scenario | Expected Status Code | Expected Result |
|---|---|---|---|
| TC-01 | Get all products | 200 | Products list returned |
| TC-02 | Get product by valid ID | 200 | Product returned |
| TC-03 | Get product by invalid ID | 404 | Product not found |
| TC-04 | Create product with valid data | 201 | Product created |
| TC-05 | Create product without name | 400 | Invalid request |
| TC-06 | Delete existing product | 200 | Product deleted |

## Orders Tests

| ID | Test Scenario | Expected Status Code | Expected Result |
|---|---|---|---|
| TC-07 | Get all orders | 200 | Orders list returned |
| TC-08 | Get invalid order | 404 | Order not found |
| TC-09 | Create order with valid data | 201 | Order created |
| TC-10 | Create order with invalid data | 400 | Invalid request |

## Customers Tests

| ID | Test Scenario | Expected Status Code | Expected Result |
|---|---|---|---|
| TC-11 | Get all customers | 200 | Customers list returned |
| TC-12 | Get invalid customer | 404 | Customer not found |
| TC-13 | Create customer with valid data | 201 | Customer created |
| TC-14 | Create customer without required data | 400 | Invalid request |
