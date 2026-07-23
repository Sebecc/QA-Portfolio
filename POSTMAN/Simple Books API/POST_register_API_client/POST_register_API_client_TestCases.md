# POST_register_API_client

---

## Objective

Verify that the endpoint correctly register client, get token and some of negatives scenarios

---

## Test Case 1

### Objective 

Verify that the API returns status 201 Created

### Steps

1. Provide body information in JSON format e.g<br>
{
   "clientName": "Sebastian",<br>
   "clientEmail": "Sebastian@example.com"<br>
}<br>
2. Send /api-clients request

### Expected results

- Status code is 201 Created

---
