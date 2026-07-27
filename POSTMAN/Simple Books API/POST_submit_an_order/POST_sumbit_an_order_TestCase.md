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
