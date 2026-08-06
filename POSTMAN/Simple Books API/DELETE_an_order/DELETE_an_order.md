# DELETE /orders

## Endpoint

DELETE /orders/{orderId}

## Description

Verify that the API correctly deletes an existing order and returns proper responses for invalid requests.

---

## Preconditions

- User account created
- Valid API token generated
- Existing order available (for positive scenario)

---

## Test Scenarios

| ID | Scenario | Expected | Actual | Status | Evidence |
|----|----------|----------|--------|--------|----------|
| Test Case  1 | Delete existing order | 204 No Content | 204 No Content | ✅ Pass | DELETE_an_order_TestCase1 |
| Test Case  2 | Verify deleted order | 404 Not Found | 404 Not Found | ✅ Pass | DELETE_an_order_TestCase2 |
| Test Case  3 | Delete without order ID | 404 Not Found | 404 Not Found | ✅ Pass | - |
| Test Case  4 | Delete non-existing order | 404 Not Found | 404 Not Found | ✅ Pass | - |
| Test Case  5 | Delete using text as ID | 404 Not Found | 404 Not Found | ✅ Pass | - |
| Test Case  6 | Delete using special characters | 400 Bad Request | 400 Bad Request | ✅ Pass | DELETE_an_order_TestCase3 |
| Test Case  7 | Delete without authorization | 401 Unauthorized | Not Tested | ⏳ | - |

---

## Test Execution

### Test Case 1 - Delete existing order

**Request**

```http
DELETE /orders/{orderId}
```

**Expected**

```text
204 No Content
```

**Actual**

```text
204 No Content
```

**Screenshot**

<p align="center">
<img src="../DELETE_an_order//DELETE_an_order_TestCase1" width="80%">
</p>

---

### Test Case 2 - Verify deleted order

**Request**

```http
GET /orders/{orderId}
```

**Expected**

```text
404 Not Found
```

**Actual**

```text
404 Not Found
```

**Screenshot**

<p align="center">
<img src="../DELETE_an_order//DELETE_an_order_TestCase1" width="80%">
</p>

---

### Test Case 6 - Delete using special characters

**Request**

```http
DELETE /orders/*&@#!...
```

**Expected**

```text
400 Bad Request
```

**Actual**

```text
400 Bad Request
```

**Screenshot**

<p align="center">
<img src="../DELETE_an_order//DELETE_an_order_TestCase1" width="80%">
</p>

---

## Summary

- Existing resources are deleted successfully.
- Deleted resources cannot be retrieved afterwards.
- Invalid identifiers are handled correctly.
- Malformed requests return appropriate error codes.
