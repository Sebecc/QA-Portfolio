# POST_submit_an_order RESULTS

## Summary

The endpoint was successfully tested.

## Verified

- HTTP Status Code is 201 Created for valid order creation
- HTTP Status Code is 400 Bad Request for invalid `bookId`
- HTTP Status Code is 400 Bad Request for missing `bookId`
- HTTP Status Code is 400 Bad Request for `bookId` sent as a string
- HTTP Status Code is 401 Unauthorized when authorization header is missing
- Response body contains `created: true` and `orderId` for successful requests
- Response body contains an error message for invalid requests

## Test Case 1

### Result
- Status code is **201 Created**
- Order was created successfully
- Response body contains:
  - `created: true`
  - non-empty `orderId`

## Test Case 2

### Result
- Status code is **400 Bad Request**
- API returned an error message:
  - `"Invalid or missing bookId."`

## Test Case 3

### Result
- Status code is **400 Bad Request**
- API returned an error message:
  - `"Invalid or missing bookId."`

## Test Case 4

### Result
- Status code is **400 Bad Request**
- API returned an error message:
  - `"Invalid or missing bookId."`

## Test Case 5

### Result
- Status code is **401 Unauthorized**
- API returned an error message:
  - `"Missing Authorization header."`

## Test Case 6

### Result
- Status code is **201 Created**
- Order was created successfully
- Response body contains:
  - `created: true`
  - non-empty `orderId`

## Final Result

All planned positive and negative test scenarios passed successfully.
