# Collections (static)

## Get All Collections

This endpoint retrieves all collections

### HTTP Request

`GET https://storeapi.csomni.com/collections`

### Header Parameters
| Parameter     | Required | Type   | Description       |
|---------------|----------|--------|-------------------|
| siteToken     | true     | string | Unique siteToken  |

```shell
curl --request GET \
  --url https://storeapi.csomni.com/collections \
  --header 'token: site_xxxxxxxxxx'
```

> The above command returns JSON structured like this:

```json
[
  {
    "collectionToken": "clcs_xxxxxxxxxxxxxxxx",
    "collectionName": "Educational Toys",
    "collectionDefaultSort": "0",
    "collectionSlug": "educational-toys",
    "collectionDescription": "",
    "collectionImage": "",
    "archived": "0",
    "collectionMetaTitle": "",
    "collectionMetaDescription": "",
    "collectionBrand": "",
    "createdAt": "2021-12-15 13:23:54",
    "editedAt": "2021-12-15 13:23:54",
    "products": []
  },
  {
    "collectionToken": "clcs_xxxxxxxxxxxx",
    "collectionName": "Children toys",
    "collectionDefaultSort": "b",
    "collectionSlug": "children-toys",
    "collectionDescription": "desc",
    "collectionImage": "url.url.com",
    "archived": "0",
    "collectionMetaTitle": "",
    "collectionMetaDescription": "",
    "collectionBrand": "",
    "collectionSortOrder": 0,
    "products": []
  }
]
```

## Get Collection by collection token

This endpoint retrieves a specified collection and its products.

### HTTP Request

`GET https://storeapi.csomni.com/collections/{collectiontoken||collectionSlug}`

### URL Parameters

| Parameter       | Type   | Description                 |
|-----------------|--------|-----------------------------|
| collectionToken | string | Token of the Collection, Or |
| collectionSlug  | string | Slug of the collection      |

```shell
curl --request GET \
  --url https://storeapi.csomni.com/collections/[collectiontoken||collectionSlug] \
  --header 'siteToken: site_xxxxxxxxxx'
```

> The above command returns JSON structured like this:

```json
{
  "collectionToken": "clcs_xxxxxxxxxxxx",
  "collectionName": "Drywall Sheetrock",
  "collectionDefaultSort": "",
  "collectionSlug": "drywall-sheetrock",
  "collectionDescription": "",
  "collectionImage": "5-27-2021\/1622123882070__1036__sheetrock.webp",
  "archived": 0,
  "hideCollection": 0,
  "collectionMetaTitle": "",
  "collectionMetaDescription": "",
  "collectionSortOrder": 0,
  "collectionBrand": "",
  "createdAt": "2022-12-18 23:01:01",
  "editedAt": "2022-12-18 23:01:01",
  "active": 0,
  "products": [
    {
      "id": 2996,
      "prodToken": "prod_xxxxxxxxxxxxx",
      "collectionToken": "clcs_xxxxxxxxxxxxx",
      "sortOrder": 0,
      "createdAt": "2022-12-18 23:01:00",
      "editedAt": "2022-12-18 23:01:00",
      "prodName": "Wonder Board 3\"X5\"",
      "prodImage": {
        "file": "9-25-2022\/1664125155630__176320__40073.jpg",
        "type": ""
      },
      "prodImages": [],
      "prodWeight": 0,
      "prodDimW": 0,
      "prodDimL": "",
      "prodDimH": "",
      "prodUpc": "",
      "prodNumber": "",
      "prodPrice": ".00",
      "prodCostPrice": "",
      "prodDescription": "<p>Cement&nbsp;<\/p><p>HardieBacker&nbsp;<\/p><p>&nbsp;<\/p>",
      "prodHighlights": "",
      "prodAlert": "",
      "prodLowlevel": "",
      "prodSlug": "wonder-board-",
      "prodVisible": 1,
      "prodAllowCheckout": 0,
      "prodCheckInvetory": 0,
      "prodTrackInventory": 0,
      "inventoryCount": 0,
      "shippingProduct": 0,
      "prodMetaTitle": "",
      "prodMetaDescription": "",
      "prodBrand": "",
      "prodType": "",
      "prodTemplate": "",
      "prodAccessories": "[]",
      "google_prodCategory": "",
      "google_prodType": "",
      "google_prodCondition": "",
      "archived": 0,
      "backOrderWarning": 0,
      "variants": [
        {
          "prodToken": "prod_xxxxxxxxxxxxx",
          "variantToken": "vrnt_xxxxxxxxxxxxx",
          "variantName": "",
          "variantImage": {
            "file": "9-25-2022\/1664125155630__176320__40073.jpg",
            "type": ""
          },
          "variantImages": [],
          "variantWeight": "0",
          "variantDimW": "0",
          "variantDimL": "0",
          "variantDimH": "0",
          "variantUpc": "",
          "variantNumber": "",
          "manufacturerPartNumber": "",
          "variantPrice": 0,
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
          "google_variantCategory": null,
          "google_variantType": null,
          "google_variantCondition": null,
          "taxable": 1,
          "variantAllowCheckout": 0,
          "variantCheckInvetory": 0,
          "variantTrackInventory": 0,
          "inventoryCount": -4,
          "shippingProduct": 0,
          "variantMetaTitle": "",
          "variantMetaDescription": "",
          "variantBrand": "",
          "sortOrder": 0,
          "dateCreated": "1664124639",
          "deleted": 0,
          "backOrderWarning": 0,
          "createdAt": "2022-12-18 23:01:04",
          "editedAt": "2023-04-19 12:26:57",
          "variantInStock": true
        },
        {
          "prodToken": "prod_xxxxxxxxxxxxx",
          "variantToken": "vrnt_xxxxxxxxxxxxx",
          "variantName": "",
          "variantImage": {
            "file": "9-25-2022\/1664125155630__176320__40073.jpg",
            "type": ""
          },
          "variantImages": [],
          "variantWeight": "0",
          "variantDimW": "0",
          "variantDimL": "0",
          "variantDimH": "0",
          "variantUpc": "",
          "variantNumber": "40073",
          "manufacturerPartNumber": "",
          "variantPrice": 0,
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
          "google_variantCategory": null,
          "google_variantType": null,
          "google_variantCondition": null,
          "taxable": 1,
          "variantAllowCheckout": 0,
          "variantCheckInvetory": 0,
          "variantTrackInventory": 0,
          "inventoryCount": 0,
          "shippingProduct": 0,
          "variantMetaTitle": "",
          "variantMetaDescription": "",
          "variantBrand": "",
          "sortOrder": 1,
          "dateCreated": "1610392185",
          "deleted": 0,
          "backOrderWarning": 0,
          "createdAt": "2022-12-18 23:01:04",
          "editedAt": "2022-12-18 23:01:04",
          "variantInStock": true,
          "variantOptions": [
            {
              "optionToken": "optn_xxxxxxxxxxxxx",
              "optionValue": "1\/4 INCH",
              "optionName": "Size"
            }
          ]
        },
        {
          "prodToken": "prod_xxxxxxxxxxxxx",
          "variantToken": "vrnt_xxxxxxxxxxxxx",
          "variantName": "",
          "variantImage": {
            "file": "2-15-2021\/1613417239722__39450__40075a.jpg",
            "type": ""
          },
          "variantImages": [],
          "variantWeight": "0",
          "variantDimW": "0",
          "variantDimL": "0",
          "variantDimH": "0",
          "variantUpc": "",
          "variantNumber": "40075",
          "manufacturerPartNumber": "",
          "variantPrice": 0,
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
          "google_variantCategory": null,
          "google_variantType": null,
          "google_variantCondition": null,
          "taxable": 1,
          "variantAllowCheckout": 0,
          "variantCheckInvetory": 0,
          "variantTrackInventory": 0,
          "inventoryCount": 0,
          "shippingProduct": 0,
          "variantMetaTitle": "",
          "variantMetaDescription": "",
          "variantBrand": "",
          "sortOrder": 3,
          "dateCreated": "1610392379",
          "deleted": 0,
          "backOrderWarning": 0,
          "createdAt": "2022-12-18 23:01:04",
          "editedAt": "2022-12-18 23:01:04",
          "variantInStock": true,
          "variantOptions": [
            {
              "optionToken": "optn_xxxxxxxxxxxxx",
              "optionValue": "1\/2 INCH",
              "optionName": "Size"
            }
          ]
        },
        {
          "prodToken": "prod_xxxxxxxxxxxxx",
          "variantToken": "vrnt_xxxxxxxxxxxxx",
          "variantName": "",
          "variantImage": {
            "file": "9-25-2022\/1664125155630__176320__40073.jpg",
            "type": ""
          },
          "variantImages": [
            {
              "file": "2-15-2021\/1613417239722__39450__40075a.jpg",
              "type": ""
            }
          ],
          "variantWeight": "0",
          "variantDimW": "0",
          "variantDimL": "0",
          "variantDimH": "0",
          "variantUpc": "",
          "variantNumber": "40076",
          "manufacturerPartNumber": "",
          "variantPrice": 0,
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
          "google_variantCategory": null,
          "google_variantType": null,
          "google_variantCondition": null,
          "taxable": 1,
          "variantAllowCheckout": 0,
          "variantCheckInvetory": 0,
          "variantTrackInventory": 0,
          "inventoryCount": 0,
          "shippingProduct": 0,
          "variantMetaTitle": "",
          "variantMetaDescription": "",
          "variantBrand": "",
          "sortOrder": 4,
          "dateCreated": "1610392379",
          "deleted": 0,
          "backOrderWarning": 0,
          "createdAt": "2022-12-18 23:01:04",
          "editedAt": "2022-12-18 23:01:04",
          "variantInStock": true,
          "variantOptions": [
            {
              "optionToken": "optn_aBRKypaZbIARGzuI0V8l",
              "optionValue": "5\/8 INCH",
              "optionName": "Size"
            }
          ]
        }
      ],
      "variantInfo": {
        "priceTo": 0,
        "priceFrom": 0,
        "variantCount": 4
      }
    },
    {
      "id": 3033,
      "prodToken": "prod_uKN0NqmLoxMAeJhw",
      "collectionToken": "clcs_9hOv0qbYj0eOkngC",
      "sortOrder": 0,
      "createdAt": "2022-12-18 23:01:00",
      "editedAt": "2022-12-18 23:01:00",
      "companyToken": "comp_fxJJZhdcNMfRF9m",
      "prodName": "Sheetrock ",
      "prodImage": {
        "file": "9-25-2022\/1664124035325__1400__45009.jpg",
        "type": ""
      },
      "prodImages": [],
      "prodWeight": 0,
      "prodDimW": 0,
      "prodDimL": "",
      "prodDimH": "",
      "prodUpc": "",
      "prodNumber": "",
      "prodPrice": ".00",
      "prodCostPrice": "",
      "prodDescription": "",
      "prodHighlights": "",
      "prodAlert": "",
      "prodLowlevel": "",
      "prodSlug": "sheetrock-",
      "prodVisible": 1,
      "prodAllowCheckout": 0,
      "prodCheckInvetory": 0,
      "prodTrackInventory": 0,
      "inventoryCount": 0,
      "shippingProduct": 0,
      "prodMetaTitle": "",
      "prodMetaDescription": "",
      "prodBrand": "",
      "prodType": "",
      "prodTemplate": "",
      "prodAccessories": "[]",
      "google_prodCategory": "",
      "google_prodType": "",
      "google_prodCondition": "",
      "archived": 0,
      "backOrderWarning": 0,
      "variants": [
        {
          "prodToken": "prod_xxxxxxxxxxxxx",
          "variantToken": "vrnt_xxxxxxxxxxxxx",
          "variantName": "",
          "variantImage": {
            "file": "9-25-2022\/1664124035325__1400__45009.jpg",
            "type": "",
            "id": "65ls4dx8",
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
          "variantPrice": 0,
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
          "google_variantCategory": null,
          "google_variantType": null,
          "google_variantCondition": null,
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
          "dateCreated": "1664123650",
          "deleted": 0,
          "backOrderWarning": 0,
          "createdAt": "2022-12-18 23:01:04",
          "editedAt": "2022-12-18 23:01:04",
          "variantInStock": true
        },
        {
          "prodToken": "prod_xxxxxxxxxxxxx",
          "variantToken": "vrnt_xxxxxxxxxxxxx,
          "variantName": "",
          "variantImage": {
            "file": "9-25-2022\/1664124035325__1400__45009.jpg",
            "type": ""
          },
          "variantImages": [],
          "variantWeight": "0",
          "variantDimW": "0",
          "variantDimL": "0",
          "variantDimH": "0",
          "variantUpc": "",
          "variantNumber": "45009",
          "manufacturerPartNumber": "",
          "variantPrice": 0,
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
          "google_variantCategory": null,
          "google_variantType": null,
          "google_variantCondition": null,
          "taxable": 1,
          "variantAllowCheckout": 0,
          "variantCheckInvetory": 0,
          "variantTrackInventory": 0,
          "inventoryCount": 0,
          "shippingProduct": 0,
          "variantMetaTitle": "",
          "variantMetaDescription": "",
          "variantBrand": "",
          "sortOrder": 1,
          "dateCreated": "1610561388",
          "deleted": 0,
          "backOrderWarning": 0,
          "createdAt": "2022-12-18 23:01:04",
          "editedAt": "2022-12-18 23:01:04",
          "variantInStock": true,
          "variantOptions": [
            {
              "optionToken": "optn_xxxxxxxxxxxxx",
              "optionValue": "4 x 8 x 3\/8",
              "optionName": "Size"
            }
          ]
        },
        {
          "prodToken": "prod_xxxxxxxxxxxxx",
          "variantToken": "vrnt_xxxxxxxxxxxxx",
          "variantName": "",
          "variantImage": {
            "file": "9-25-2022\/1664124035325__1400__45009.jpg",
            "type": ""
          },
          "variantImages": [],
          "variantWeight": "0",
          "variantDimW": "0",
          "variantDimL": "0",
          "variantDimH": "0",
          "variantUpc": "",
          "variantNumber": "45010",
          "manufacturerPartNumber": "",
          "variantPrice": 0,
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
          "google_variantCategory": null,
          "google_variantType": null,
          "google_variantCondition": null,
          "taxable": 1,
          "variantAllowCheckout": 0,
          "variantCheckInvetory": 0,
          "variantTrackInventory": 0,
          "inventoryCount": 0,
          "shippingProduct": 0,
          "variantMetaTitle": "",
          "variantMetaDescription": "",
          "variantBrand": "",
          "sortOrder": 2,
          "dateCreated": "1610561501",
          "deleted": 0,
          "backOrderWarning": 0,
          "createdAt": "2022-12-18 23:01:04",
          "editedAt": "2022-12-18 23:01:04",
          "variantInStock": true,
          "variantOptions": [
            {
              "optionToken": "optn_xxxxxxxxxxxxx",
              "optionValue": "4 x 8 x 1\/2 ",
              "optionName": "Size"
            }
          ]
        },
        {
          "prodToken": "prod_xxxxxxxxxxxxx",
          "variantToken": "vrnt_xxxxxxxxxxxxx",
          "variantName": "",
          "variantImage": {
            "file": "9-25-2024\/1664124035325__1400__45009.jpg",
            "type": ""
          },
          "variantImages": [],
          "variantWeight": "0",
          "variantDimW": "0",
          "variantDimL": "0",
          "variantDimH": "0",
          "variantUpc": "",
          "variantNumber": "45015",
          "manufacturerPartNumber": "",
          "variantPrice": 0,
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
          "google_variantCategory": null,
          "google_variantType": null,
          "google_variantCondition": null,
          "taxable": 1,
          "variantAllowCheckout": 0,
          "variantCheckInvetory": 0,
          "variantTrackInventory": 0,
          "inventoryCount": 0,
          "shippingProduct": 0,
          "variantMetaTitle": "",
          "variantMetaDescription": "",
          "variantBrand": "",
          "sortOrder": 4,
          "dateCreated": "1610561501",
          "deleted": 0,
          "backOrderWarning": 0,
          "createdAt": "2022-12-18 23:01:04",
          "editedAt": "2022-12-18 23:01:04",
          "variantInStock": true,
          "variantOptions": [
            {
              "optionToken": "optn_xxxxxxxxxxxxx",
              "optionValue": "4 x 8 x 5\/8 ",
              "optionName": "Size"
            }
          ]
        }
      ],
      "variantInfo": {
        "priceTo": 0,
        "priceFrom": 0,
        "variantCount": 4
      }
    },
    {
      "id": 3034,
      "prodToken": "prod_xxxxxxxxxxxxx",
      "collectionToken": "clcs_xxxxxxxxxxxxx",
      "sortOrder": 0,
      "createdAt": "2022-12-18 23:01:00",
      "editedAt": "2022-12-18 23:01:00",
      "prodName": "Sheetrock Waterproof Green 4\"X8\"",
      "prodImage": {
        "file": "9-25-2024\/1664124434665__1521__45011.jpg",
        "type": ""
      },
      "prodImages": [],
      "prodWeight": 0,
      "prodDimW": 0,
      "prodDimL": "",
      "prodDimH": "",
      "prodUpc": "",
      "prodNumber": "",
      "prodPrice": ".00",
      "prodCostPrice": "",
      "prodDescription": "",
      "prodHighlights": "",
      "prodAlert": "",
      "prodLowlevel": "",
      "prodSlug": "sheetrock-waterproof-green",
      "prodVisible": 1,
      "prodAllowCheckout": 0,
      "prodCheckInvetory": 0,
      "prodTrackInventory": 0,
      "inventoryCount": 0,
      "shippingProduct": 0,
      "prodMetaTitle": "",
      "prodMetaDescription": "",
      "prodBrand": "",
      "prodType": "",
      "prodTemplate": "",
      "prodAccessories": "[]",
      "google_prodCategory": "",
      "google_prodType": "",
      "google_prodCondition": "",
      "archived": 0,
      "backOrderWarning": 0,
      "variants": [
        {
          "prodToken": "prod_xxxxxxxxxxxxx",
          "variantToken": "vrnt_xxxxxxxxxxxxx",
          "variantName": "",
          "variantImage": {
            "file": "9-25-2024\/1664124434665__1521__45011.jpg",
            "type": "",
            "id": "z8t3qir6",
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
          "variantPrice": 0,
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
          "google_variantCategory": null,
          "google_variantType": null,
          "google_variantCondition": null,
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
          "dateCreated": "1664124261",
          "deleted": 0,
          "backOrderWarning": 0,
          "createdAt": "2024-12-18 23:01:04",
          "editedAt": "2024-12-18 23:01:04",
          "variantInStock": true
        },
        {
          "prodToken": "prod_xxxxxxxxxxxxx",
          "variantToken": "vrnt_xxxxxxxxxxxxx",
          "variantName": "",
          "variantImage": {
            "file": "9-25-2024\/1664124434665__1521__45011.jpg",
            "type": ""
          },
          "variantImages": [],
          "variantWeight": "0",
          "variantDimW": "0",
          "variantDimL": "0",
          "variantDimH": "0",
          "variantUpc": "",
          "variantNumber": "45011",
          "manufacturerPartNumber": "",
          "variantPrice": 0,
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
          "google_variantCategory": null,
          "google_variantType": null,
          "google_variantCondition": null,
          "taxable": 1,
          "variantAllowCheckout": 0,
          "variantCheckInvetory": 0,
          "variantTrackInventory": 0,
          "inventoryCount": 0,
          "shippingProduct": 0,
          "variantMetaTitle": "",
          "variantMetaDescription": "",
          "variantBrand": "",
          "sortOrder": 1,
          "dateCreated": "1610561625",
          "deleted": 0,
          "backOrderWarning": 0,
          "createdAt": "2024-12-18 23:01:04",
          "editedAt": "2024-12-18 23:01:04",
          "variantInStock": true,
          "variantOptions": [
            {
              "optionToken": "optn_xxxxxxxxxxxxx",
              "optionValue": "1\/2 INCH",
              "optionName": "Size"
            }
          ]
        },
        {
          "prodToken": "prod_xxxxxxxxxxxxx",
          "variantToken": "vrnt_xxxxxxxxxxxxx",
          "variantName": "",
          "variantImage": {
            "file": "9-25-2024\/1664124434665__1521__45011.jpg",
            "type": ""
          },
          "variantImages": [],
          "variantWeight": "0",
          "variantDimW": "0",
          "variantDimL": "0",
          "variantDimH": "0",
          "variantUpc": "",
          "variantNumber": "45016",
          "manufacturerPartNumber": "",
          "variantPrice": 0,
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
          "google_variantCategory": null,
          "google_variantType": null,
          "google_variantCondition": null,
          "taxable": 1,
          "variantAllowCheckout": 0,
          "variantCheckInvetory": 0,
          "variantTrackInventory": 0,
          "inventoryCount": 0,
          "shippingProduct": 0,
          "variantMetaTitle": "",
          "variantMetaDescription": "",
          "variantBrand": "",
          "sortOrder": 2,
          "dateCreated": "1610561660",
          "deleted": 0,
          "backOrderWarning": 0,
          "createdAt": "2024-12-18 23:01:04",
          "editedAt": "2024-12-18 23:01:04",
          "variantInStock": true,
          "variantOptions": [
            {
              "optionToken": "optn_xxxxxxxxxxxxx",
              "optionValue": "5\/8 INCH",
              "optionName": "Size"
            }
          ]
        }
      ],
      "variantInfo": {
        "priceTo": 0,
        "priceFrom": 0,
        "variantCount": 3
      }
    }
  ]
}
```
