# PATCH_update_an_order

## Objective

Verify that PATCH /orders/{orderId} correctly changes order details and properly handles authorization and invalid input scenarios.

---

## Test Case 1

### Objective 

Verify that the API accepts changing `customerName`

### Preconditions

- API is available
- Valid authorization token is available
- Order exists

### Steps

1. Copy one of "id" from Get all orders request
2. Paste the "id" into PATCH /orders/{orderId}
3. 
Request body should in JSON format in following order:
```json
  {
    "customerName": "{{$randomFullName}}"
  }
```
4. Send PATCH /orders/{orderId}

### Expected result

- Status code is 204 No Content
- Response body contains nothing in return:
```json

```

### Validation

- Get validation from GET /orders/{orderId} that name is changed

---


## Test Case 2

### Objective 

Verify that the API rejects an empty `customerName`

### Preconditions 

- API is available
- Valid authorization token is not available
- Order exists

### Steps

1. Request body should in JSON format in following order:
```json
{
  "customerName": ""
}
```
2. Send PATCH /orders/orderId

### Expected Result

- API rejects invalid request.

---

## Test Case 3 

### Objective

Verify that the API rejects numeric value for `customerName`

### Preconditions 
- API is available
- Valid authorization token is available
- Order exists

### Steps

1. Request body should in JSON format in following order:
```json
{
  "customerName": 123
}
```
2. Send PATCH /orders/orderId

### Expected Result

- API rejects invalid request

### Validation

- Get validation from GET /orders/{orderId} that name is changed

---

## Test Case 4

### Objective

Verify that the API rejects boolean value for `customerName`

### Preconditions 

- API is available
- Valid authorization token is available
- Order exists

### Steps

1. Request body should in JSON format in following order:
```json
{
  "customerName": true
}
```
2. Send PATCH /orders/orderId

### Expected Result

- API rejects invalid request

### Validation

- Get validation from GET /orders/{orderId} that name is changed

---

## Test Case 5 

### Objective

Verify that the API rejects a request with a non-existing order ID.

### Preconditions 

- API is available
- Valid authorization token is available
- Order exists

### Steps

1. Set orderId in the endpoint to a non-existing value.
2. Send PATCH /orders/{orderId} request.

### Expected Result

- API response is Status 404 Not Found
  - Response body contains an appropriate error message indicating that the order was not found.
 
---

## Test Case 6

### Objective

Verify that the API rejects a request JSON format is empty.

### Preconditions 

- API is available
- Valid authorization token is available
- Order exists

### Steps

1. Request body should in JSON format in following order:
```json
{

}
```
2. Send PATCH /orders/orderId

### Expected Result

- API response is Status 400 Bad Request
  - Response body contains an appropriate error message indicating that the order has no valid fields to update.
 
---

## Test Case 7

### Objective

Verify that the API rejects a request when token is not valid.

### Preconditions 
- API is available
- Invalid authorization token is available
- Order exists

### Steps
1. Set token into into invalid token.
2. Send PATCH /orders/{orderId} request.

### Expected Result

- API response is Status 401 Unauthorized
  - Response body contains an appropriate error message indicating that the user has invalid token.
 
---

## Test Case 8

### Objective

Verify that the API rejects a request with a non-existing order ID.

### Preconditions 
- API is available
- Valid authorization token is available
- Order exists

### Steps
1. Roveke access token
2. Send PATCH /orders/{orderId} request.

### Expected Result

- API response is Status 401 Unauthorized
  - Response body contains an appropriate error message indicating that the token is not available.
 
---

