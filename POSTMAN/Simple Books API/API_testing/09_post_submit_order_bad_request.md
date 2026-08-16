# POST - Submit an Order - Bad Request

## Endpoint

`POST {{SimpleBookURL}}/orders`

## Request Body

``` json
{
  "bookId": "1,
  "customerName": "Robert"
}
```

## Scenario

Invalid request resulting in a `400 Bad Request` response.

## Expected Result

-   Status code: `400 Bad Request`

## Test

``` javascript
pm.test("Status code is 400 Bad request", () => {
    pm.response.to.have.status(400);
});

pm.test("Response time below 500 ms", () => {

    const response = pm.response.json();

    pm.expect(pm.response.responseTime).to.be.below(500);
})
```

## Result

Test passed successfully.

-   Status code: `400 Bad Request`
-   Response Time: `below 500 ms`
-   Test results: `2/2 PASSED`
