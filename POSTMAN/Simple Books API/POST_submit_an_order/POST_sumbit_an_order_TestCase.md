# POST_submit_an_order

## Objective
Verify that the endpoint correctly creates an order, returns an order id, and handles invalid input and authorization errors.

---

## Test Case 1

### Objective
Verify that the API returns status **201 Created** for a valid order.

### Preconditions
- API is available.
- Valid authorization token is available.
- `bookId` exists in the system.

### Steps
1. Provide body information in JSON format, e.g.
```json
{
  "bookId": 3,
  "customerName": "Robert"
}
```
2. Send /orders request

### Expected result

- Status code is 201 Created
- Response body contains:
  - created: true
  - non-empty orderId
 
---

## Test Case 2

### Objective
Verify that the API returns status 400 Bad Request for invalid bookId.

### Preconditions
- API is available.
- Valid authorization token is available.

### Steps
1. Provide body information in JSON format, e.g.
```json
{
  "bookId": 21,
  "customerName": "Robert"
}
```
2. Send /orders request

### Expected result

- Status code is 400 Bad Request
- Response body contains an error message related to invalid bookId
 
---

## Test Case 3

### Objective
Verify what happens when bookId is missing.

### Preconditions
- API is available.
- Valid authorization token is available.

### Steps
1. Provide body information in JSON format, e.g.
```json
{
  "customerName": "Jan"
}
```
2. Send /orders request

### Expected result

- Status code is 400 Bad Request
- Response body contains an error message related to missing customerName
 
---

## Test Case 4

### Objective
Verify what happens when customerName is empty.

### Preconditions
- API is available.
- Valid authorization token is available.

### Steps
1. Provide body information in JSON format, e.g.
```json
{
  "bookId": 1,
  "customerName": ""
}
```
2. Send /orders request

### Expected result

- Status code is 400 Bad Request
- Response body contains an error message related to invalid customerName
 
---

## Test Case 5

### Objective
Verify that the API returns status 401 Unauthorized when authorization token is missing.

### Preconditions
- API is available.
- No authorization token is included in the request.

### Steps
1. Provide body information in JSON format, e.g.
```json
{
  "bookId": 21,
  "customerName": "Robert"
}
```
2. Remove the authorization token 
3. Send /orders request

### Expected result

- Status code is 401 Unauthorized
- Response body contains an error message related to missing authorization
 
---

## Test Case 6

### Objective
Verify what happens when bookId is sent as a string instead of a number.

### Preconditions
- API is available.
- Valid authorization token is available.

### Steps
1. Provide body information in JSON format, e.g.
```json
{
  "bookId": "3",
  "customerName": "Robert"
}
```
2. Send /orders request

### Expected result
- API should validate the data type of bookId
  - Status code is 400 Bad Request, or
  - Request accepted if API automatically converts the value
- Behavior should be documented clearly
 
---


