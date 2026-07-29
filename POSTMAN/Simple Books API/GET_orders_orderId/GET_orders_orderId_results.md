# GET_orders_orderId RESULTS

## Summary

Verify that GET /orders/{orderId} correctly returns order details and properly handles authorization and invalid input scenarios.

## Verified

- HTTP Status Code is 200 OK for valid request
- HTTP Status Code is 401 Unauthorized for invalid `token`
- HTTP Status Code is 401 Unauthorized for valid, not available `token`
- HTTP Status Code is 404 Not Found for empty value in `orderId`
- HTTP Status Code is 404 Not Found for misspelled value in `orderId`
- HTTP Status Code is 404 Not Found for "1" value in `orderId`
- HTTP Status Code is 500 Internal Server Error for "1" value in `orderId` (Non-reproductable)

## Test Case 1

# Result

- Status Code is 200 OK
- Respones body contains:
```json
{
    "id": "9SoBrQX0LeIW4v4ibeTep",
    "bookId": "1",
    "customerName": "Jaś",
    "quantity": 1,
    "timestamp": 1785168450238
}
```

## Test Case 2 

# Result

- Status Code is 401 Unauthorized
- Respones body contains:
```json
{
    "error": "Missing Authorization header."
}
```

## Test Case 3 

# Result

- Status Code is 401 Unauthorized
- Respones body contains:
```json
{
    "error": "Invalid bearer token."
}
```

## Test Case 4a

# Result

- Status Code is 404 Not Found
- Respones body contains:
```json
{
    "error": "No order with id 1."
}
```

## Test Case 4b

# Result

- Status Code is 500 Internal Server Error
- Respones body contains:
```json
{
    "error": "Internal Server Error."
}
```

## Test Case 5

# Result

- Status Code is 404 Not Found
- Respones body contains:
```json
{
    "error": "No order with id 9SoBrQX0LeIW4v4ibeTe."
}
```

## Test Case 6

# Result

- Status Code is 404 Not Found
- Respones body contains:
```json
{
    "error": "No order with id :orderId:."
}
```
