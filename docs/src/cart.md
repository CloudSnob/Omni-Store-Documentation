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

```shell
curl --request POST \
  --url https://storeapi.csomni.com/cart/ \
  --header 'token: site-xxxxxxxxx'\
  --header 'customerToken: cs_xxxxxxxxxxxxxxxxxxxxx'
```

> The above command returns JSON structured like this when a new cart is created:

```json
{
  "cartToken": "cart_xxxxxxxxxxxxxx",
  "companyToken": "comp_xxxxxxxxxxxxxx",
  "siteToken": "site_xxxxxxxxxx",
  "customerToken": "cs_xxxxxxxxxxxxxxxxx",
  "status": "cart created"
}
```

> The above command returns JSON structured like this when a cart is retrieved:

```json
{
  "cartToken": "cart_xxxxxxxxxxxxxx",
  "companyToken": "comp_xxxxxxxxxxxxxx",
  "siteToken": "site_xxxxxxxxxx",
  "customerToken": "cs_xxxxxxxxxxxxxxxxx",
  "status": "cart retrieved"
}
```


## New Cart and new customer

This endpoint creates a new guest customer and a new cart

### HTTP Request

`POST https://storeapi.csomni.com/cart`

### Header Parameters
| Parameter     | Required | Type   | Description      |
|---------------|----------|--------|------------------|
| siteToken     | true     | string | Unique siteToken |

```shell
curl --request POST \
  --url https://storeapi.csomni.com/cart/ \
  --header 'token: site_xxxxxxxxxxxx'
```

> The above command returns JSON structured like this

```json
{
  "cartToken": "cart_xxxxxxxxxxxxxx",
  "companyToken": "comp_xxxxxxxxxxxxxx",
  "siteToken": "site_xxxxxxxxxx",
  "customerToken": "cs_xxxxxxxxxxxxxxxxx",
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

```shell
curl --request GET \
  --url https://storeapi.csomni.com/cart \
  --header 'token: site-xxxxxxxxx'\
  --header 'customerToken: cs_xxxxxxxxxxxxxxxxxxx'

```

> The above command returns JSON structured like this:

```json
{
  "siteToken": "site_xxxxxxxxxxxx",
  "cartToken": "cart_xxxxxxxxxxxxxxx",
  "customerToken": "cs_xxxxxxxxxxxxxxxxxxx",
  "cartCreated": "1637945854",
  "cartLastTouched": "1637945854",
  "deleted": 0,
  "createdAt": "2021-12-17 15:37:57",
  "editedAt": "2021-12-17 15:37:57",
  "pricing": {
    "total": 34
  },
  "itemsInCart": 1,
  "cartWeight": 0,
  "cartProds": [
    {
      "cartToken": "cart_xxxxxxxxxxxxxxx",
      "cartProdToken": "cp_xxxxxxxxxxxxxxx",
      "addOnToProdToken": "",
      "cartProdQuantity": 1,
      "addOnProdTokens": null,
      "prodToken": "vrnt_xxxxxxxxxxxxxxx",
      "deleted": 0,
      "companyToken": "comp_xxxxxxxxxxxxxxx",
      "siteToken": "site_xxxxxxxxx",
      "customerToken": "cs_xxxxxxxxxxxxxxxxxxx",
      "cartCreated": "1637945854",
      "cartLastTouched": "1637945854",
      "prodStaticCollections": [
        "clcs_123456",
        "clcs_123456",
        "clcs_123456",
        ""
      ],
      "specialValues": [],
      "product": {
        "prodToken": "prod_xxxxxxxxxxxxxxx",
        "variantToken": "vrnt_xxxxxxxxxxxxxxx",
        "companyToken": "comp_xxxxxxxxxxxxxxx",
        "variantName": "",
        "variantImage": {
          "file": "10-13-2021/1634136843403__65263__aron-yigin-epjvM-Ql5-Y-unsplash.jpg",
          "type": "",
          "id": "abc",
          "status": "poolImages"
        },
        "variantImages": [],
        "variantWeight": "0",
        "variantDimW": "0",
        "variantDimL": "0",
        "variantDimH": "0",
        "variantUpc": "",
        "variantNumber": "",
        "manufacturerPartNumber": "",
        "variantPrice": 34,
        "variantMapPrice": 0,
        "variantMsrpPrice": 0,
        "variantDisplayPrice": 32,
        "variantDescription": "",
        "variantAlert": "",
        "variantLowlevel": "",
        "variantSlug": "",
        "variantVisible": 1,
        "variantAllowCheckout": 0,
        "variantCheckInvetory": 0,
        "variantTrackInventory": 0,
        "taxType": "",
        "taxable": 1,
        "shippingProduct": 0,
        "variantMetaTitle": "",
        "variantMetaDescription": "",
        "variantBrand": "",
        "google_variantCategory": "",
        "google_variantType": "",
        "google_variantCondition": "",
        "hideGoogleData": 0,
        "sortOrder": 0,
        "dateCreated": "1634137246",
        "deleted": 0,
        "backOrderWarning": 0,
        "variantInStock": true,
        "variantOptions": [
          {
            "optionToken": "optn_xxxxxxxxxxxxxxx",
            "optionValue": "dsasda",
            "optionName": "color"
          },
          {
            "optionToken": "optn_xxxxxxxxxxxxxxx",
            "optionValue": "f",
            "optionName": "size"
          }
        ],
        "prodName": "Black T-Shirt",
        "prodImage": {
          "file": "5-1-2024/1622471456251__6160299__jonah-brown-veEPQ7aOx8w-unsplash.jpg",
          "name": "",
          "type": ""
        }
      },
      "addOnProducts": [],
      "pricing": {
        "total": 34
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
| combine       | true     | -      | To combine 2 carts                                               |
| cartToken     | true     | true   | Cart Token for the cart that should be transferred               |
| customerToken | true     | true   | Customer Token for the account the cart should be transferred to |

### Header Parameters
| Parameter     | Required | Unique | Description                                                           |
|---------------|----------|--------|-----------------------------------------------------------------------|
| customerToken | true     | -      | Customer Token for account that the cart is currently associated with |
| siteToken     | true     | -      | Unique site token                                                     |
```shell
curl --request POST \
  --url https://storeapi.csomni.com/cart/combine/[cartToken]/[customerToken] \
  --header 'token: site_xxxxxxxxx' \
  --header 'customerToken : cs_xxxxxxxxxxxxxxxx' 
```

> The above command returns JSON structured like this

```json
{
  "companyToken": "comp_xxxxxxxxxxxxxx",
  "siteToken": "site_xxxxxxxxx",
  "cartToken": "cart_xxxxxxxxxxxxxx",
  "customerToken": "cust_123456",
  "cartCreated": "1638346960",
  "cartLastTouched": "1638346960",
  "deleted": 0,
  "pricing": {
    "total": 12
  },
  "itemsInCart": 4,
  "cartWeight": 4,
  "cartProds": [
    {
      "cartToken": "cart_xxxxxxxxxxxxxx",
      "cartProdToken": "xxx",
      "addOnToProdToken": "",
      "cartProdQuantity": 4,
      "addOnProdTokens": null,
      "prodToken": "vrnt_xxxxxxxxxxxxxx",
      "deleted": 0,
      "companyToken": "comp_xxxxxxxxxxxxxx",
      "siteToken": "site_xxxxxxx",
      "customerToken": "cs_xxxxxxxxxxxxxxxxx",
      "cartCreated": "1638346960",
      "cartLastTouched": "1638346960",
      "prodStaticCollections": [],
      "specialValues": [],
      "product": {
        "prodToken": "prod_xxxxxxxxxxxxxx",
        "variantToken": "vrnt_xxxxxxxxxxxxxx",
        "companyToken": "comp_xxxxxxxxxxxxxx",
        "variantName": "",
        "variantImage": {
          "file": ""
        },
        "variantImages": [],
        "variantWeight": "1",
        "variantDimW": "0",
        "variantDimL": "0",
        "variantDimH": "0",
        "variantUpc": "",
        "variantNumber": "",
        "manufacturerPartNumber": "",
        "variantPrice": 3,
        "variantMapPrice": 0,
        "variantMsrpPrice": 0,
        "variantDisplayPrice": 0,
        "variantDescription": "",
        "variantAlert": "",
        "variantLowlevel": "",
        "variantSlug": "",
        "variantVisible": 1,
        "variantAllowCheckout": 1,
        "variantCheckInvetory": 1,
        "variantTrackInventory": 0,
        "taxType": "",
        "taxable": 1,
        "shippingProduct": 1,
        "variantMetaTitle": "",
        "variantMetaDescription": "",
        "variantBrand": "",
        "google_variantCategory": null,
        "google_variantType": null,
        "google_variantCondition": null,
        "hideGoogleData": 1,
        "sortOrder": 0,
        "dateCreated": "1606236358",
        "deleted": 0,
        "backOrderWarning": 0,
        "variantInStock": true,
        "prodName": "Yes",
        "prodImage": {
          "file": "11-24-2020/1606236354284__36278__GUEST_1e09d33a-dc4e-4ff2-8640-7540993a94ae.jpg"
        }
      },
      "addOnProducts": [],
      "pricing": {
        "total": 12
      },
      "shipping": {
        "totalWeight": 4
      }
    }
  ]
}
```
