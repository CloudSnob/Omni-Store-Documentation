# Cart Products

## Add Product to cart

### Header Parameters
| Parameter     | Required | Unique | Description                                 |
|---------------|----------|--------|---------------------------------------------|
| customerToken | false    | string | Customer Token (creates a new one if empty) |
| siteToken     | true     | string | Unique siteToken                            |


### Data Parameters

| Parameter        | Required | Type   | Description                       |
|------------------|----------|--------|-----------------------------------|
| prodToken        | true     | string | Variant Token to be added to cart |
| cartProdQuantity | true     | int    | Quantity to add to cart           |

```shell
curl --request POST \
  --url https://storeapi.csomni.com/cartprods \
  --header 'token: site_xxxxxxxx' \
  --data '{ "cartProdQuantity" : 1, "prodToken" : "vrnt_xxxxxxxxxxxxx" }'

```

> The above command returns JSON structured like this for a new product to cart

```json
{
  "cartToken": "cart_xxxxxxxxxxxxxxxx",
  "cartProdToken": "cp_xxxxxxxxxxxxxxxxxxxx",
  "cartProdQuantity": "1",
  "customerToken": "cs_xxxxxxxxxxxxxxxxxxxxxx",
  "prodToken": "prod_xxxxxxxxxxxxxxxx",
  "cartAddedQuantity": "3",
  "status": "Prod Added"
}
```

> If the product is already listed in the cart, the above command returns a JSON structured like this

```json
{
  "cartToken": "cart_xxxxxxxxxxxxx",
  "prodToken": "prod_xxxxxxxxxxxxxx",
  "customerToken": "cs_xxxxxxxxxxxxxxxxx",
  "cartProdQuantity": 23,
  "cartProdToken": "cp_xxxxxxxxxxxxxxxxxx",
  "cartAddedQuantity": "8",
  "status": "Prod Updated"
}
```

## Edit cart product

This endpoint Edits a cart product item

### HTTP Request

`POST https://storeapi.csomni.com/cartprods/{cartProdToken}`

### Header Parameters
| Parameter     | Required | Type      | Description      |
|---------------|----------|-----------|------------------|
| customerToken | true     | string    | Customer Token   |
| siteToken     | true     | string    | Unique siteToken |

### Query Parameters

| Parameter        | Required | Type   | Description                 |
|------------------|----------|--------|-----------------------------|
| cartProdQuantity | true     | int    | Quantity to add to cart     |
| prodToken        | true     | string | variant targeted for change |

```shell
curl --request POST \
  --url https://storeapi.csomni.com/cartprods/{cartProdToken} \
  --header 'token: site_xxxxxxxxxxx' \
  -- header 'customerToken : cs _xxxxxxxxxxxxxxxx'\
  --data '{ "cartProdQuantity" : 1, "prodToken", "vrnt_xxxxxxxxxxxxx"}'

```

> The above command returns JSON structured like this

```json
{
  "cartToken": "cart_xxxxxxxxxxxxxxxxxxx",
  "prodToken": "vrnt_xxxxxxxxxxxxxxxxxxx",
  "customerToken": "cs_xxxxxxxxxxxxxxxxxxxxxx",
  "cartProdQuantity": 7,
  "cartProdToken": "cp_xxxxxxxxxxxxxxxxxx",
  "cartAddedQuantity": 1,
  "status": "Prod Updated"
}
```

## Get A Cart Product
This endpoint retrieves a cart products


### HTTP Request

`GET https://storeapi.csomni.com/cartprods/{cartProdToken}`

### Header Parameters
| Parameter     | Required | Type   | Description      |
|---------------|----------|--------|------------------|
| customerToken | true     | string | Customer Token   |
| siteToken     | true     | string | Unique siteToken |

```shell
curl --request GET \
  --url https://storeapi.csomni.com/cartprods/[cartProdToken] \
  --header 'token: site_xxxxxxxxxxxx' \
  --header 'customerToken: cs_xxxxxxxxxxxxxxxxxx'
```

> The above command returns JSON structured like this:

```json
{
  "cartToken": "cart_xxxxxxxxxxxxxxxxxx",
  "cartProdToken": "cp_xxxxxxxxxxxxxxxxxxxx",
  "cartProdQuantity": 8,
  "addOnToProdToken": "",
  "addOnProdTokens": null,
  "prodToken": "vrnt_xxxxxxxxxxxxxxx",
  "deleted": 0,
  "createdAt": "2024-05-20 11:07:33",
  "editedAt": "2024-05-20 11:07:33",
  "siteToken": "site_xxxxxxxxxxxxxx",
  "customerToken": "cs_xxxxxxxxxxxxxxxxxxxxxxx",
  "cartCreated": "1716203253",
  "cartLastTouched": "1716203253",
  "prodStaticCollections": [
    "clcs_xxxxxxxxxxxx"
  ],
  "specialValues": [],
  "product": {
    "prodToken": "prod_xxxxxxxxxxxxxxxx",
    "variantToken": "vrnt_xxxxxxxxxxxxx",
    "variantName": "",
    "variantImage": {
      "file": "11-25-2022\/1669391493868__30709__NS-35859.jpg",
      "type": "",
      "id": "cjoqzz33",
      "status": "poolImages"
    },
    "variantImages": [],
    "variantWeight": "0",
    "variantDimW": "0",
    "variantDimL": "0",
    "variantDimH": "0",
    "variantUpc": "",
    "variantNumber": "NS-35859",
    "manufacturerPartNumber": "",
    "variantPrice": 0.1,
    "variantMapPrice": 0,
    "variantMsrpPrice": 0,
    "variantDisplayPrice": 0,
    "variantDescription": "",
    "variantAlert": "",
    "variantLowlevel": "",
    "variantSlug": "",
    "variantVisible": 1,
    "taxType": "",
    "hideGoogleData": 0,
    "google_variantCategory": "",
    "google_variantType": "",
    "google_variantCondition": "",
    "taxable": 1,
    "variantAllowCheckout": 0,
    "variantCheckInvetory": 0,
    "variantTrackInventory": 0,
    "inventoryCount": 0,
    "shippingProduct": 0,
    "variantMetaTitle": "",
    "variantMetaDescription": "",
    "variantBrand": "",
    "sortOrder": 0,
    "dateCreated": "1669391499",
    "deleted": 0,
    "backOrderWarning": 0,
    "createdAt": "2022-12-18 23:01:04",
    "editedAt": "2024-06-17 13:24:13",
    "variantInStock": true,
    "prodName": "3\/4 IN. O.D. SATIN NICKEL DRIVE-IN, SPRING LOADED, BALL STYLE, CABINET DOOR LATCH WITH STRIKE\t",
    "prodImage": {
      "file": "11-25-2022\/1669391493868__30709__NS-35859.jpg",
      "type": ""
    }
  },
  "addOnProducts": [],
  "pricing": {
    "total": 0.8
  },
  "shipping": {
    "totalWeight": 0
  }
}
```


## Delete a Product from cart
This endpoint deletes (archives) a cart product

### HTTP Request

`DELETE https://storeapi.csomni.com/cartprods/{cartProdToken}`

### Header Parameters
| Parameter     | Required | Type   | Description      |
|---------------|----------|--------|------------------|
| customerToken | true     | string | Customer Token   |
| siteToken     | true     | string | Unique siteToken |


### URL Parameters
| Parameter     | Required | Type   | Description            |
|---------------|----------|--------|------------------------|
| cartProdToken | true     | string | The cart product token |

```shell
curl --request DELETE \
  --url https://storeapi.csomni.com/cartprods/{cartProdToken} \
  --header 'token: site_xxxxxxxxxxx' \
  --header 'customerToken: cs_xxxxxxxxxxxxxx'
```

> The above command returns JSON structured like this:

```json
{
  "token": "cp_xxxxxxxxxxxxx",
  "deleted": true
}
```

