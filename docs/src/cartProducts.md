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

Sample in Shell:


#### Example 1: Adding item to cart
```shell
curl --request POST \
  --url https://storeapi.csomni.com/cartprods \
  --header 'token: site_xxxxxxxxxxx' \
  --data '{ 
            "cartProdQuantity" : 1, 
            "prodToken" : "vrnt_nhX0NJqewTbyBPjS" 
          }'

```

> The above command returns JSON structured like this for a new product to cart
```json
{
  "cartToken": "cart_UGfpkwcZ8OCdCxNHJK007uk6",
  "cartProdToken": "cp_Ygj5uVE5Jqaqc4ah4wTFvBWO",
  "cartProdQuantity": "1",
  "customerToken": "cs_P0NW9KYnw061h3PTiUMFl2twP1UscyEt6HF7",
  "prodToken": "vrnt_nhX0NJqewTbyBPjS",
  "cartAddedQuantity": "1",
  "status": "Prod Added"
}
```

> If the product is already listed in the cart, the above command returns a JSON structured like this


```json
{
  "cartToken": "cart_UGfpkwcZ8OCdCxNHJK007uk6",
  "prodToken": "vrnt_nhX0NJqewTbyBPjS",
  "customerToken": "cs_P0NW9KYnw061h3PTiUMFl2twP1UscyEt6HF7",
  "cartProdQuantity": 1,
  "cartProdToken": "cp_Ygj5uVE5Jqaqc4ah4wTFvBWO",
  "cartAddedQuantity": 1,
  "status": "Prod Updated"
}
```

#### Example 2: Adding item with special value:

```shell
curl --request POST \
  --url https://apistore.csomni.com/cartprods/cart_2EwMrNJlBqndLlDr9LLP24VU \
  --header 'token: site_xxxxxxxxxxxxx' \
  --data '{
            "cartProdQuantity" : "1",
            "prodToken" : "vrnt_yqktptPndobaaR86
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
This endpoint Edits a cart product item, for example the quantity

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

Sample in Shell:

```shell
curl --request POST \
  --url https://storeapi.csomni.com/cartprods/cp_Ygj5uVE5Jqaqc4ah4wTFvBWO \
  --header 'token: site_xxxxxxxxxxx' \
  -- header 'customerToken : cs_P0NW9KYnw061h3PTiUMFl2twP1UscyEt6HF7'\
  --data '{ 
            "cartProdQuantity" : 1, 
            "prodToken", "vrnt_nhX0NJqewTbyBPjS"
          }'

```

> The above command returns JSON structured like this
```json
{
  "cartToken": "cart_UGfpkwcZ8OCdCxNHJK007uk6",
  "prodToken": "vrnt_nhX0NJqewTbyBPjS",
  "customerToken": "cs_P0NW9KYnw061h3PTiUMFl2twP1UscyEt6HF7",
  "cartProdQuantity": 5,
  "cartProdToken": "cp_Ygj5uVE5Jqaqc4ah4wTFvBWO",
  "cartAddedQuantity": 5,
  "status": "Prod Updated"
}
```

## Get A Cart Product
This endpoint retrieves a single cart item - a single item within the cart

### HTTP Request
`GET https://storeapi.csomni.com/cartprods/{cartProdToken}`

### Header Parameters
| Parameter     | Required | Type   | Description      |
|---------------|----------|--------|------------------|
| customerToken | true     | string | Customer Token   |
| siteToken     | true     | string | Unique siteToken |

Sample in Shell:

```shell
curl --request GET \
  --url https://storeapi.csomni.com/cartprods/cp_Ygj5uVE5Jqaqc4ah4wTFvBWO \
  --header 'token: site_xxxxxxxxxxxx' \
  --header 'customerToken: cs_P0NW9KYnw061h3PTiUMFl2twP1UscyEt6HF7'
```

> The above command returns JSON structured like this:

```json
{
  "cartToken": "cart_UGfpkwcZ8OCdCxNHJK007uk6",
  "cartProdToken": "cp_Ygj5uVE5Jqaqc4ah4wTFvBWO",
  "cartProdQuantity": 5,
  "addOnToProdToken": "",
  "addOnProdTokens": null,
  "prodToken": "vrnt_nhX0NJqewTbyBPjS",
  "deleted": 0,
  "createdAt": "2024-06-27 09:41:47",
  "editedAt": "2024-06-27 09:41:47",
  "siteToken": "site_KCDlSRZWaIotet0v",
  "customerToken": "cs_P0NW9KYnw061h3PTiUMFl2twP1UscyEt6HF7",
  "cartCreated": "1719481308",
  "cartLastTouched": "1719481308",
  "prodStaticCollections": [],
  "specialValues": [],
  "product": {
    "prodToken": "prod_vGBKFHP3wwH3Hs4r",
    "variantToken": "vrnt_nhX0NJqewTbyBPjS",
    "variantName": "Long sleeve",
    "variantImage": [],
    "variantImages": [],
    "variantWeight": null,
    "variantDimW": null,
    "variantDimL": null,
    "variantDimH": null,
    "variantUpc": null,
    "variantNumber": "123-789",
    "manufacturerPartNumber": null,
    "variantPrice": 0.2,
    "variantMapPrice": null,
    "variantMsrpPrice": null,
    "variantDisplayPrice": null,
    "variantDescription": null,
    "variantAlert": null,
    "variantLowlevel": null,
    "variantSlug": null,
    "variantVisible": 1,
    "taxType": null,
    "hideGoogleData": 0,
    "google_variantCategory": null,
    "google_variantType": null,
    "google_variantCondition": null,
    "taxable": 1,
    "variantAllowCheckout": 0,
    "variantCheckInvetory": 0,
    "variantTrackInventory": 0,
    "inventoryCount": 0,
    "shippingProduct": 0,
    "variantMetaTitle": null,
    "variantMetaDescription": null,
    "variantBrand": null,
    "sortOrder": 0,
    "dateCreated": "1719481982",
    "deleted": 0,
    "backOrderWarning": 0,
    "createdAt": "2024-06-27 09:53:02",
    "editedAt": "2024-06-27 09:53:02",
    "variantInStock": true,
    "prodName": "T-shirts",
    "prodImage": {
      "type": ""
    }
  },
  "addOnProducts": [],
  "pricing": {
    "total": 1
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

Sample in Shell:

```shell
curl --request DELETE \
  --url https://storeapi.csomni.com/cartprods/cp_Ygj5uVE5Jqaqc4ah4wTFvBWO \
  --header 'token: site_xxxxxxxxxxx' \
  --header 'customerToken: cs_P0NW9KYnw061h3PTiUMFl2twP1UscyEt6HF7'
```

> The above command returns JSON structured like this:
```json
{
  "token": "cp_Ygj5uVE5Jqaqc4ah4wTFvBWO",
  "deleted": true
}
```

