# GET /orders

---

## Test Case 1

### Objective

Verify that the API returns status 200 OK and measure response time

### Preconditions

- API is available
- Valid authorization token is available

### Steps

1. Send GET /orders request

### Expected result

- Status code is 200 OK
- Response time is relatively fast

---

## Test Case 2

### Objective

Verify that the API returns status 401 Unauthorized when authorization token is missing.

### Preconditions

- API is available
- No authorization token is included in the reqest

### Steps

1. Send GET /orders request

### Expected result

- Status code is 401 Unauthorized
- Response body contains an error related to missing authorization

---

## Test Case 3

### Objective

Verify that body returns all values

### Preconditions

- API is available
- Valid authorization token is available

### Steps 

1. Send GET /orders request

### Expected result

- Status code is 200 OK
- Body format contains 'id', 'bookId', 'customerName', 'quantity' and 'timestamp' in all orders

---
