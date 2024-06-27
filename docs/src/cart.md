# Cart

## New Cart for existing customer
This endpoint creates a cart for a customer, or retrieves the cart if the customer has a cart

### HTTP Request
`POST https://storeapi.csomni.com/cart`

### Header Parameters
| Parameter     | Required | Type   | Description      |
|---------------|----------|--------|------------------|
| customerToken | true     | string | Customer Token   |
| siteToken     | true     | string | Unique siteToken |

Sample in Shell:

```shell
curl --request POST \
  --url https://storeapi.csomni.com/cart/ \
  --header 'token: site-xxxxxxxxx'\
  --header 'customerToken: cs_GWdE9xY2dcL9qqBmNKx7WXivTh73nJtGH4NK'
```

> If a new cart is created, the above command returns a JSON structured like this:
```json
{
  "cartToken": "cart_UGfpkwcZ8OCdCxNHJK007uk6",
  "siteToken": "site_KCDlSRZWaIotet0v",
  "customerToken": "cs_P0NW9KYnw061h3PTiUMFl2twP1UscyEt6HF7",
  "status": "cart created"
}
```

> If customer has an existing cart, the above command returns a JSON structure like this:
```json
{
  "cartToken": "cart_UGfpkwcZ8OCdCxNHJK007uk6",
  "siteToken": "site_KCDlSRZWaIotet0v",
  "customerToken": "cs_P0NW9KYnw061h3PTiUMFl2twP1UscyEt6HF7",
  "status": "cart retrieved"
}
```

## New Cart and new customer
This endpoint creates a new guest customer and a new cart for the guest customer

### HTTP Request
`POST https://storeapi.csomni.com/cart`

### Header Parameters
| Parameter     | Required | Type   | Description      |
|---------------|----------|--------|------------------|
| siteToken     | true     | string | Unique siteToken |

Sample in Shell:

```shell
curl --request POST \
  --url https://storeapi.csomni.com/cart/ \
  --header 'token: site_xxxxxxxxxxxx'
```

> The above command returns JSON structured like this
```json
{
  "cartToken": "cart_E4LgT2xLYS3OJiN8pI8ZvBBB",
  "siteToken": "site_xxxxxxxxxxxxx",
  "customerToken": "cs_7WHuVUMDCt5dSmbTGaYSS4OAeT5l14YcGVPm",
  "status": "cart created"
}
```

## Get Cart By Customer
This endpoint retrieves a cart by customer token

### HTTP Request
`GET https://storeapi.csomni.com/cart`

### Header Parameters
| Parameter     | Required | Type   | Description      |
|---------------|----------|--------|------------------|
| customerToken | true     | string | Customer Token   |
| siteToken     | true     | string | Unique siteToken |

Sample in Shell:

```shell
curl --request GET \
  --url https://storeapi.csomni.com/cart \
  --header 'token: site-xxxxxxxxx'\
  --header 'customerToken: cs_7WHuVUMDCt5dSmbTGaYSS4OAeT5l14YcGVPm'

```

> The above command returns JSON structured like this:

```json
{
  "siteToken": "site_xxxxxxxxxxxxxxxx",
  "cartToken": "cart_UGfpkwcZ8OCdCxNHJK007uk6",
  "customerToken": "cs_P0NW9KYnw061h3PTiUMFl2twP1UscyEt6HF7",
  "cartCreated": "1719481308",
  "cartLastTouched": "1719481308",
  "deleted": 0,
  "createdAt": "2024-06-27 09:41:47",
  "editedAt": "2024-06-27 09:41:47",
  "pricing": {
    "total": 0.2
  },
  "itemsInCart": 1,
  "cartWeight": 0,
  "cartProds": [
    {
      "cartToken": "cart_UGfpkwcZ8OCdCxNHJK007uk6",
      "cartProdToken": "cp_Ygj5uVE5Jqaqc4ah4wTFvBWO",
      "cartProdQuantity": 1,
      "addOnToProdToken": "",
      "addOnProdTokens": null,
      "prodToken": "vrnt_nhX0NJqewTbyBPjS",
      "deleted": 0,
      "createdAt": "2024-06-27 09:41:47",
      "editedAt": "2024-06-27 09:41:47",
      "siteToken": "site_xxxxxxxxxxxxx",
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
        "total": 0.2
      },
      "shipping": {
        "totalWeight": 0
      }
    }
  ]
}
```


## Combine Carts
This endpoint Adds a user to a cart

### HTTP Request

`POST https://storeapi.csomni.com/cart/combine/[cartToken]/[customerToken]/`

### URL Parameters

| Parameter     | Required | Unique | Description                                                      |
|---------------|----------|--------|------------------------------------------------------------------|
| cartToken     | true     | true   | Cart Token for the cart that should be transferred               |
| customerToken | true     | true   | Customer Token for the account the cart should be transferred to |

### Header Parameters
| Parameter     | Required | Unique | Description                                                           |
|---------------|----------|--------|-----------------------------------------------------------------------|
| customerToken | true     | -      | Customer Token for account that the cart is currently associated with |
| siteToken     | true     | -      | Unique site token                                                     |

Sample in Shell:

```shell
curl --request POST \
  --url https://storeapi.csomni.com/cart/combine/[cartToken]/[customerToken] \
  --header 'token: site_xxxxxxxxx' \
  --header 'customerToken : cs_xxxxxxxxxxxxxxxx' 
```

> The above command returns JSON structured like this

```json
{
  "siteToken": "site_KCDlSRZWaIotet0v",
  "cartToken": "cart_UGfpkwcZ8OCdCxNHJK007uk6",
  "customerToken": "cs_P0NW9KYnw061h3PTiUMFl2twP1UscyEt6HF7",
  "cartCreated": "1719481308",
  "cartLastTouched": "1719481308",
  "deleted": 0,
  "createdAt": "2024-06-27 09:41:47",
  "editedAt": "2024-06-27 09:41:47",
  "pricing": {
    "total": 0.2
  },
  "itemsInCart": 1,
  "cartWeight": 0,
  "cartProds": [
    {
      "cartToken": "cart_UGfpkwcZ8OCdCxNHJK007uk6",
      "cartProdToken": "cp_Ygj5uVE5Jqaqc4ah4wTFvBWO",
      "cartProdQuantity": 1,
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
        "total": 0.2
      },
      "shipping": {
        "totalWeight": 0
      }
    }
  ]
}
```
