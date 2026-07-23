# GET /books/id

---
## Objective 

Testing negative test scenarios

---

## Test Case 1 

Verify that API returns HTTP 404 Not Found to non-existing id

### Steps

1. Send GET /books/id/0 request

### Expected result

- Status Code 404 Not Found

---

## Test  case 2

Verify that API returns HTTP 400 Bad Request to invalid id format

### Steps

1. Send GET /books/id/abc request

### Expected result 

- Status Code 400 Bad Request
