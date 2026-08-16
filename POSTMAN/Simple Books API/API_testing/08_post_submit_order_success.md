# POST - Submit an Order

## Endpoint

`POST {{SimpleBookURL}}/orders`

## Request Body

``` json
{
    "bookId": 1,
    "customerName": "Robert"
}
```

## Expected Result

-   Status code: `201 Created`
-   Response contains `orderId`
-   Response time is below `500 ms`

## Tests

``` javascript
pm.test("Status code is 201 Created", () => {
    pm.response.to.have.status(201);
});

pm.test("Does order exist", () => {
    const response = pm.response.json();

    pm.expect(response.orderId).to.exist;
});

pm.test("Response time below 500 ms", () => {
    pm.expect(pm.response.responseTime).to.be.below(500);
});
```

## Result

All tests passed successfully.

-   Status code: `201 Created`
-   Test results: `3/3 PASSED`
