# PATCH_udpate_an_order

## Summary

## Verified

- HTTP Status is 204 No Content for vaild change request
- HTTP Status is 200 OK for checking changes in `orderId`
- HTTP Status is 204 No Content for changing `customerName` using numerical symbols
- HTTP Status is 204 No Content for changing `customerName` using boolean
- HTTP Status is 400 Bad Request for changing `customerName` with empty string
- HTTP Status is 400 Bad Request for changing JSON format into blank document

## TestCase 1

### Result

- Status is 204 No Content
- Response body gives no response

### Validation

- Name has changed :
```json
{
    "id": "9SoBrQX0LeIW4v4ibeTep",
    "bookId": "1",
    "customerName": Brandi Kreiger,
    "quantity": 1,
    "timestamp": 1785168450238
}
```

## Test Case 2 

- Status Code is 400 Bad Request
- Body responded with information:
```json
{
  "error": "No valid fields to update."
}
```

## Test Case 3 

### Result

- Status is 204 No Content
- Response body gives no response

### Validation

- Name has changed :
```json
{
    "id": "9SoBrQX0LeIW4v4ibeTep",
    "bookId": "1",
    "customerName": 123,
    "quantity": 1,
    "timestamp": 1785168450238
}
```

## Test Case 4

### Result

- Status is 204 No Content
- Response body gives no response

### Validation

- Name has changed :
```json
{
    "id": "9SoBrQX0LeIW4v4ibeTep",
    "bookId": "1",
    "customerName": true,
    "quantity": 1,
    "timestamp": 1785168450238
}
```

## Test Case 5 

- Status is 404 Not Found
- Body responded with information:
```json
{
  "error": "No order with id 123456789."
}
```

## Test Case 6

- Status Code is 400 Bad Request
- Body responded with information:
```json
{
  "error": "No valid fields to update."
}
```

## Test Case 7 

- Status Code is 401 Unauthorized
- Body responded with information:
```json
{
  "error": "Invalid bearer token."
}
```

## Test Case 8 

- Status Code is 401 Unauthorized
- Body responded with information:
```json
{
  "error": "Missing Authorization header."
}
```
