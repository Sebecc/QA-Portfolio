# PATCH_update_an_order

## Objective

Verify that PATCH /orders/{orderId} correctly changes order details and properly handles authorization and invalid input scenarios.

---

## Test Case 1

### Objective 

Verify that the API returns status 204 No Content for a valid order and changes details

### Preconditions

- API is available
- Valid authorization token is available
- Order exists
- Existing details that can be changed

### Steps

1. Copy one of "id" from Get all orders request
2. Paste the "id" into PATCH /orders/{orderId}
3. Send /orders/{orderId} request

### Expected result

- Status code is 204 No Content
- Response body contains nothing in return:
```json

```
- Get validation from GET /orders/{orderId} that name is changed
---


## Test Case 2

### Objective 

Verify that the API returns Status 400 Bad Request after changing details without string of characters

### Preconditions 

- API is available
- Valid authorization token is not available
- Order exists
- Existing details that can be changed

### Steps

1. Request body should in JSON format in following order:
```json
{
  "customerName": ""
}
```
2. Send /orders/orderId request

### Expected Result

- API returns Status 400 Bad Request

---

## Test Case 3 

### Objective

Verify that the API returns Status 400 Bad Request after changing details only into digits

### Preconditions 
- API is available
- Valid authorization token is available
- Order exists
- Existing details that can be changed

### Steps

1. Request body should in JSON format in following order:
```json
{
  "customerName": 123
}
```
2. Send /orders/orderId request

### Expected Result

- API returns Status 400 Bad Request or 

---
