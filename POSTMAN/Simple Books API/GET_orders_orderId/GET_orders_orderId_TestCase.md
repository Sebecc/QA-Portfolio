# GET_orders_orderId

## Objective

Verify that GET /orders/{orderId} correctly returns order details and properly handles authorization and invalid input scenarios.

---

## Test Case 1

### Objective 

Verify that the API returns status 200 OK for a valid order

### Preconditions

- API is available
- Valid authorization token is available

### Steps

1. Copy one of "id" from Get all orders request
2. Paste the "id" into Path Variable -> orderId -> Value
3. Send /orders/:orderId request

### Expected result

- Status code is 200 OK
- Resonse body contains e.g:
```json
{
    "id",
    "bookId",
    "customerName",
    "quantity",
    "timestamp"
}
```

---

## Test Case 2

### Objective 

Verify that the API returns Status 401 Unauthorized

### Preconditions 

- API is available
- Valid authorization token is not available

### Steps

1. Revoke Authorization Token
2. Send /orders/orderId request

### Expected Result

- API returns Status 401 Unauthorized

---

## Test Case 3 

### Objective

Verify that the API returns Status 401 Unauthorized

### Preconditions 
- API is available
- Invalid authorization token is available

### Steps

1. Change to invalid Authorization Token
2. Send /orders/orderId request

### Expected Result

- API returns Status 401 Unauthorized

---

## Test Case 4

Verify that the API returs Status 404 Not Found

### Precondtions

- API is available
- Valid authorization token is available

### Steps

1. Set orderId value to "1"
2. Send /orders/orderId request

### Expected result

- API returns Status 404 Not Found

---

## Test Case 5

Verify that the API returs Status 404 Not Found

# Precondtions

- API is available
- Valid authorization token is available

### Steps

1. Remove one character from a valid orderId.
2. Send /orders/orderId request

### Expected result

- API returns Status 404 Not Found

---

## Test Case 6

Verify that the API returs Status 404 Not Found

### Precondtions

- API is available
- Valid authorization token is available

### Steps

1. Leave the orderId path parameter empty
2. Send /orders/orderId request

### Expected result

- API returns Status 404 Not Found

---
