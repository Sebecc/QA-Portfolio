# GET_orders RESULTS

## Summary

The endpoint was successfully tested

## Verified
- HTTP Status Code is 200 OK for valid request
- HTTP Status Code is 401 Unauthorzied for request without authorization token
- Response time is relatively fast
- Response body contains:
```
"id', "bookId", "customerName", "quantity", "timestamp"
```
- Response body contains an error message for invalid request

## Test Case 1

# Result

- Status code is 200 OK
- Response time is relatively fast

## Test Case 2

# Result

- Status code is 401 Unauthorized
- API returned an error message:
  - ```json
    {
      error: "Missing authorization header"
    }
    ```

## Test Case 3 

# Result

- Status code is 200 OK
- - Response body contains:
```
"id', "bookId", "customerName", "quantity", "timestamp"
```

---
