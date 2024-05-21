# Cart Products

## Add Product to cart

### Query Parameters

| Parameter        | Required | Unique | Description                                   |
| ---------------- | -------- | ------ | --------------------------------------------- |
| cartToken        | false    | -      | Cart to add product to (creates one if empty) |
| customerToken    | false    | -      | Customer Token (creates a new one if empty)   |
| prodToken        | true     | -      | Variant Token                                 |
| cartProdQuantity | true     | -      | Quantity to add to cart                       |
| specialValues    | false    | -      | Special Values associated with this cart product                       |
| specialValues:valueName    | true    | -      | Key of the SpecialValue                     |
| specialValues:value    | true    | -      | Value of SpecialValue property                   |

#### Example 1: Only adding item to cart
```shell
curl --request POST \
  --url https://apistore.csomni.com/cartprods/[cartToken] \
  --header 'cache-control: no-cache' \
  --header 'postman-token: 1234567890' \
  --header 'token: 123' \
  --data '{ "cartProdQuantity" : "1", "prodToken" : "prod_123456" }'

```

> The above command returns JSON structured like this

```json
{
  "cartToken": "cart_123456",
  "cartProdToken": "cp_123456",
  "cartProdQuantity": "1",
  "customerToken": "cust_111",
  "prodToken": "prod_123456",
  "cartAddedQuantity": "3",
  "status": "Prod Added"
}
```

> Where a product already exists in the cart, and the cart product is increased/decreased in quantity the above command returns a JSON structured like this

```json
{
  "cartToken": "cart_123456",
  "prodToken": "prod_123456",
  "customerToken": "cs_123456",
  "cartProdQuantity": 23,
  "cartProdToken": "cp_123456",
  "cartAddedQuantity": "8",
  "status": "Prod Updated"
}
```

#### Example 2: Adding item with special value:

```shell
curl --request POST \
  --url https://apistore.csomni.com/cartprods/[cartToken] \
  --header 'cache-control: no-cache' \
  --header 'postman-token: 1234567890' \
  --header 'token: 123' \
  --data '{
            "cartProdQuantity" : "1",
            "prodToken" : "vrnt_##############",
            "specialValues": [
                    {
                        "valueName": "dog",
                        "value": "brown"
                    },
                    {
                        "valueName": "id",
                        "value": "1234"
                    }
                ]
}'

```

> The above command returns JSON structured like this

```json
{
    "specialValues": [
        {
            "specialValueToken": "sv_mXQyCYHGE3bLIiokcBhKI3bJHB3znfM0mvbU",
            "valueName": "dog",
            "value": "brown"
        },
        {
            "specialValueToken": "sv_mXQyCYHGE3bLIiokcBhKI3bJHB3znfM0mvbU",
            "valueName": "id",
            "value": "1234"
        }
    ],
    "cartToken": "cart_2EwMrNJlBqndLlDr9LLP24VU",
    "cartProdToken": "cp_IOadVIVOCUA7sEdjW84POIbd",
    "cartProdQuantity": 1,
    "customerToken": "cs_lEe26Ej6ATKvyo4LD0dNahQEFTU9biuGzezj",
    "prodToken": "vrnt_yqktptPndobaaR86",
    "cartAddedQuantity": 1,
    "status": "Prod Added"
}
```

> Where a product already exists in the cart, and the cart product is increased/decreased in quantity the above command returns a JSON structured like this

```json
{
  "cartToken": "cart_123456",
  "prodToken": "prod_123456",
  "customerToken": "cs_123456",
  "cartProdQuantity": 23,
  "cartProdToken": "cp_123456",
  "cartAddedQuantity": "8",
  "status": "Prod Updated"
}
```





## Edit cart product

This endpoint Edits a product in cart

### HTTP Request

`POST https://apistore.csomni.com/cartprods/{cartProdToken}`

### Query Parameters

| Parameter        | Required | Unique | Description             |
| ---------------- | -------- | ------ | ----------------------- |
| cartProdQuantity | true     | -      | Quantity to add to cart |
| customerToken    | true     | -      | Customer Token          |

```shell
curl --request POST \
  --url https://apistore.csomni.com/cartprods/{cartProdToken} \
  --header 'cache-control: no-cache' \
  --header 'postman-token: 1234567890' \
  --header 'token: 123' \
  --data '{ "cartProdQuantity" : "1" }'

```

> The above command returns JSON structured like this

```json
{
  "cartProdToken": "cp_123456",
  "cartProdQuantity": "50",
  "cartAddedQuantity": "",
  "prodToken": "prod_123456"
}
```

## Get A Cart Product

### HTTP Request

`GET https://apistore.csomni.com/cartprods/[cartProdToken]`

### URL Parameters

| Parameter     | Required | Unique | Description                    |
| ------------- | -------- | ------ | ------------------------------ |
| cartProdToken | true     | -      | cart product Token to retreive |
| customerToken | true     | -      | customer token in header       |

```shell
curl --request GET \
  --url https://apistore.csomni.com/cartprods/[cartProdToken] \
  --header 'token: 123'
  --header 'customerToken: cs_123456'
```

> The above command returns JSON structured like this:

```json
{
  "cartToken": "cart_123456",
  "cartProdToken": "cp_123456",
  "cartProdQuantity": 12,
  "addOnToProdToken": "",
  "addOnProdTokens": null,
  "prodToken": "prod_123456",
  "deleted": 0,
  "createdAt": "2021-12-29 14:57:32",
  "editedAt": "2021-12-29 14:57:32",
  "companyToken": "comp_123456",
  "siteToken": "site_123",
  "customerToken": "cust_123456",
  "cartCreated": "1640789852",
  "cartLastTouched": "1640789852",
  "specialValues": [],
  "product": {},
  "addOnProducts": [],
  "pricing": {
    "total": 0
  },
  "shipping": {
    "totalWeight": 0
  }
}
```

This endpoint retrieves a cart products

## Delete a Product from cart

This endpoint deletes (archives) a cart product

### HTTP Request

`DELETE https://apistore.csomni.com/cartprods/{cartProdToken}`

### URL Parameters

| Parameter | Description                   |
| --------- | ----------------------------- |
| Token     | The Token of the cart product |

```shell
curl --request DELETE \
  --url https://apistore.csomni.com/cartprods/{cartProdToken} \
  --header 'content-type: application/json' \
  --header 'token: 123'
```

> The above command returns JSON structured like this:

```json
{
  "token": "cp_123456",
  "deleted": true
}
```

```

```
