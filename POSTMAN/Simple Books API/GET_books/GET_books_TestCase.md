# GET/books

---

## Objective

Verify that the endpoint correctly returns the list of available books

---

## Test Case 1

### Objective

Verify that the API returns HTTP 200

### Steps

1. Send GET /books request

### Expected result

- Status code = 200 OK

---

## Test Case 2

### Objective

Verify that each book contains all required fields

### Steps

1. Send GET /books request
2. Check every object in response

### Expected result

Each object contains:
- id
- name
- type
- available

--- 

## Test Case 3 
### Objective

Verify that field values are valid

### Steps

1. Send GET /book request
2. Check field values

### Expected result

- available contains only true or false
- type contains only fiction or non-fiction
