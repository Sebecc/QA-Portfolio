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

## Test Case 2

### Objective 

Verify that the API returns status 409 Conflict

### Steps

1. Provide body information with same data from previous step in JSON format e.g<br>
{
   "clientName": "Sebastian",<br>
   "clientEmail": "Sebastian@example.com"<br>
}<br>
2. Send /api-clients request

### Expected results

- Status code is 409 Conflict

---

## Test Case 3

### Objective 

Verify what happen when "clientName" is number format instead of text

### Steps

1. Provide body information in JSON format e.g
<br>{
   "clientName": Sebastian,<br>
   "clientEmail": "Sebastian@example.com"<br>
}<br>
2. Send /api-clients request

### Expected results

- Status code is 400 Bad Request
- Expecting error "Invalid or missing client name"

---

## Test Case 4

### Objective 

Verify what happen when mail doesn't have proper syntax 

### Steps

1. Provide body information in JSON format e.g<br>
{
   "clientName": "Mariola",<br>
   "clientEmail": "Sebastiandas.com"<br>
}<br>
2. Send /api-clients request

### Expected results

- Status code is 400 Bad Request
- Expecting error "Invalid or missing client mail"

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
