# Products

## Get All Products
This endpoint retrieves products by solr

Example 1: Basic Solr search - get all products and specify list size per page
### HTTP Request
`GET https://storeapi.csomni.com/products/solr?parsedQ=&rows=20`

### Header Parameters
| Parameter     | Required | Type   | Description   |
|---------------|----------|--------|---------------|
| siteToken     | true     | string | Site Token ID |

### Query Parameters
| Parameter    | Required | Type   | Default | Description                                                                                                                                              |
|--------------|----------|--------|---------|----------------------------------------------------------------------------------------------------------------------------------------------------------|
| parsedQ      | false    | string | -       | The search term. <br/> If no exact match is found, partial matches will be returned<br/>If parameter is left empty, a full list of products is returned. |
| start        | false    | string | 0       | At which field to start                                                                                                                                  |
| rows         | false    | int    | 10      | Amount of rows to returns                                                                                                                                |
| sort         | false    | string | -       | Any field to sort by                                                                                                                                     |
| sortOrder    | false    | string | asc     | asc (ascending) or desc (descending)                                                                                                                     |
| responseData | false    | string | -       | comma delimited list of response data (full,variantAggregates,specs,specialValues,firstAggregate). See below for list of response types                  |
| fq           | false    | string | -       | A list of filters (for example if you want to show items from specific collection put fq={"prodCollectionSlugs":"collection-name"})                      |
| facets       | false    | bool   | -       | Set to '1' to be served facets.                                                                                                                          |


### Response Data Options
| Parameter         | Description                                                   |
|-------------------|---------------------------------------------------------------|
| full              | Returns All variants on the product                           |
| variantAggregates | Returns the variant count, highest and lowest priced variants |
| specs             | Returns Specs on the product and variant                      |
| specialValues     | Returns Special Values on the product and variant             |
| firstVariant      | Returns only the first variant on the product (as an object)  |
| fullAccessories   | Returns array of accessory products                           |

Sample in Shell:

```shell
curl --request GET \
  --url https://storeapi.csomni.com/products/solr?parsedQ=&rows=20 \
  --header 'token: site_xxxxxxxxxx'
```

> The above command returns the response JSON structured like this:

```json
{
  "numFound": 2203,
  "start": 0,
  "numFoundExact": true,
  "docs": [
    {
      "prodToken": "prod_Pnllm7TeX9ZpSDCS",
      "prodName": "Surface-Mount Double Toilet Paper Holder, Chrome",
      "prodImage": {
        "file": "2-3-2021\/1612376323137__21714__93015.jpg",
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
      "prodDescription": "<ul><li>Chrome<\/li><li>Surface-Mount<\/li><li>Holds 2 Rolls<\/li><\/ul>",
      "prodHighlights": "",
      "prodAlert": "",
      "prodLowlevel": "",
      "prodSlug": "double-roll-toilet-paper-holder-",
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
      "prodAccessories": [
        "prod_Ci5ly6NqRiVzaBgb",
        "prod_RwGyyJPLH2s6I5vU",
        "prod_YMNVLGJTLkhANUOW",
        "prod_ZZ5kjqqWOpp8Wv7J"
      ],
      "google_prodCategory": "",
      "google_prodType": "",
      "google_prodCondition": "",
      "archived": 0,
      "backOrderWarning": 0,
      "createdAt": "2022-12-18 23:01:00",
      "editedAt": "2022-12-18 23:01:00",
      "prodCollections": [
        "clcs_X84pzkjlQpaJPp7r"
      ],
      "variantInfo": {
        "priceTo": 0,
        "priceFrom": 0,
        "variantCount": 1
      }
    },
    {
      "prodToken": "prod_BCqk75xNGmbyZMwI",
      "prodName": "Curved Steel Floor Squeegee, 24\" with Tapered Wood Handle",
      "prodImage": {
        "file": "6-17-2021\/1623947921984__18918__13059.jpg",
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
      "prodDescription": "<ul><li>Scraping edge for removing job site debris, sludge, ice and snow<\/li><li>Stands up to most chemicals, paints, and solvents<\/li><li>Galvanized steel construction<\/li><\/ul>",
      "prodHighlights": "",
      "prodAlert": "",
      "prodLowlevel": "",
      "prodSlug": "curved-steel-floor-squeegee-24-with-54-tapered-wood-handle",
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
      "prodAccessories": [
        "prod_np74FIo3sTdLiLdo",
        "prod_6lRqA5VvZ7zO0O8Y",
        "prod_03lZcsgezLqzS8qc",
        "prod_QgBXLyuANnVOqkHM"
      ],
      "google_prodCategory": "",
      "google_prodType": "",
      "google_prodCondition": "",
      "archived": 0,
      "backOrderWarning": 0,
      "createdAt": "2022-12-18 23:01:00",
      "editedAt": "2022-12-18 23:01:00",
      "prodCollections": [
        "clcs_3KAdzRr9xYkhRlbG"
      ],
      "variantInfo": {
        "priceTo": 21.95,
        "priceFrom": 0,
        "variantCount": 3
      },
      "prodOptions": [
        {
          "optionToken": "optn_L9wEPF6PvSa70buLR1Ek",
          "optionName": "",
          "optionOrder": "0"
        }
      ]
    },
    {
      "prodToken": "prod_PMehQTerQYPxfHnt",
      "prodName": "Black Floor Pads ",
      "prodImage": {
        "file": "2-4-2021\/1612456968174__242712__14000.jpg",
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
      "prodDescription": "<p>Stripping Pads<\/p><p>Cs 5<\/p>",
      "prodHighlights": "",
      "prodAlert": "",
      "prodLowlevel": "",
      "prodSlug": "black-floor-pads-",
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
      "prodAccessories": [],
      "google_prodCategory": "",
      "google_prodType": "",
      "google_prodCondition": "",
      "archived": 0,
      "backOrderWarning": 0,
      "createdAt": "2022-12-18 23:01:00",
      "editedAt": "2022-12-18 23:01:00",
      "prodCollections": [],
      "variantInfo": {
        "priceTo": 34.95,
        "priceFrom": 0,
        "variantCount": 7
      },
      "prodOptions": [
        {
          "optionToken": "optn_IsYdz0y1mKkFFZlzPxL6",
          "optionName": "size",
          "optionOrder": "0"
        }
      ]
    }...*
```
...* : RESULT IS CUT SHORT DUE TO LARGE LENGTH

Example 2: Search with a search term ('flapper'), page list limit, responseData attributes and facets.

### HTTP Request
`GET https://storeapi.csomni.com/products/solr?parsedQ=flapper&fq={}&rows=20&start=0&responseData=firstVariant,variantAggregates&facets=1`

Sample in Shell:

```shell
curl --request GET \
--url https://storeapi.csomni.com/products/solr?parsedQ=flapper&fq={}&rows=20&start=0&responseData=firstVariant,variantAggregates&facets=1 \
--header 'token: site_xxxxxxxxxx'
```


> The above command returns the response JSON structured like this:

```json
{
  "numFound": 3,
  "start": 0,
  "numFoundExact": true,
  "docs": [
    {
      "prodToken": "prod_J6Kcyx43Xefz44DZ",
      "prodName": "KORKY TOILET FLAPPER BLACK 316540",
      "prodImage": {
        "file": "11-13-2022\/1668373988001__3802__72102.jpg",
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
      "prodDescription": "",
      "prodHighlights": "",
      "prodAlert": "",
      "prodLowlevel": "",
      "prodSlug": "korky-toilet-flapper-black-316540",
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
      "prodAccessories": [],
      "google_prodCategory": "",
      "google_prodType": "",
      "google_prodCondition": "",
      "archived": 0,
      "backOrderWarning": 0,
      "createdAt": "2022-12-18 23:01:00",
      "editedAt": "2022-12-18 23:01:00",
      "prodCollections": [
        "clcs_IdT3XKUXXIqBybaN"
      ],
      "variantInfo": {
        "priceTo": 0,
        "priceFrom": 0,
        "variantCount": 1
      },
      "firstVariant": {
        "prodToken": "prod_J6Kcyx43Xefz44DZ",
        "variantToken": "vrnt_7lCrBWvVut8oMjUQ",
        "variantName": "",
        "variantImage": {
          "file": "11-13-2022\/1668373988001__3802__72102.jpg",
          "type": ""
        },
        "variantImages": [],
        "variantWeight": "0",
        "variantDimW": "0",
        "variantDimL": "0",
        "variantDimH": "0",
        "variantUpc": "",
        "variantNumber": "72102",
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
        "inventoryCount": -1,
        "shippingProduct": 0,
        "variantMetaTitle": "",
        "variantMetaDescription": "",
        "variantBrand": "",
        "sortOrder": 0,
        "dateCreated": "1668373994",
        "deleted": 0,
        "backOrderWarning": 0,
        "createdAt": "2022-12-18 23:01:04",
        "editedAt": "2023-05-29 13:28:50",
        "variantInStock": true
      }
    },
    {
      "prodToken": "prod_HMvvCv8wA3oe6f9f",
      "prodName": "FLUIDMASTERS FLAPPER PERFORMANCE 502",
      "prodImage": {
        "file": "11-9-2022\/1668007722412__6537__502P21.jpg",
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
      "prodDescription": "",
      "prodHighlights": "",
      "prodAlert": "",
      "prodLowlevel": "",
      "prodSlug": "fluidmasters-flapper-performance-502",
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
      "prodAccessories": [],
      "google_prodCategory": "",
      "google_prodType": "",
      "google_prodCondition": "",
      "archived": 0,
      "backOrderWarning": 0,
      "createdAt": "2022-12-18 23:01:00",
      "editedAt": "2024-01-18 13:58:34",
      "prodCollections": [
        "clcs_IdT3XKUXXIqBybaN",
        "clcs_KHPYhbf6eOGsaCJo"
      ],
      "variantInfo": {
        "priceTo": 0,
        "priceFrom": 0,
        "variantCount": 1
      },
      "firstVariant": {
        "prodToken": "prod_HMvvCv8wA3oe6f9f",
        "variantToken": "vrnt_KewgBZoZD0ePWdyV",
        "variantName": "",
        "variantImage": {
          "file": "11-9-2022\/1668007722412__6537__502P21.jpg",
          "type": ""
        },
        "variantImages": [],
        "variantWeight": "2",
        "variantDimW": "0",
        "variantDimL": "0",
        "variantDimH": "0",
        "variantUpc": "",
        "variantNumber": "502P21",
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
        "google_variantCategory": "",
        "google_variantType": "",
        "google_variantCondition": "",
        "taxable": 1,
        "variantAllowCheckout": 0,
        "variantCheckInvetory": 0,
        "variantTrackInventory": 0,
        "inventoryCount": -13,
        "shippingProduct": 0,
        "variantMetaTitle": "",
        "variantMetaDescription": "",
        "variantBrand": "",
        "sortOrder": 0,
        "dateCreated": "1668007746",
        "deleted": 0,
        "backOrderWarning": 0,
        "createdAt": "2022-12-18 23:01:04",
        "editedAt": "2024-01-25 18:59:37",
        "variantInStock": true
      }
    },
    {
      "prodToken": "prod_4FNLFRwfvbOhUQvf",
      "prodName": "Flapper double",
      "prodImage": {
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
      "prodDescription": "",
      "prodHighlights": "",
      "prodAlert": "",
      "prodLowlevel": "",
      "prodSlug": "flapper-double",
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
      "prodAccessories": [],
      "google_prodCategory": "",
      "google_prodType": "",
      "google_prodCondition": "",
      "archived": 0,
      "backOrderWarning": 0,
      "createdAt": "2024-06-24 11:01:40",
      "editedAt": "2024-06-24 11:02:01",
      "prodCollections": [],
      "variantInfo": {
        "priceTo": null,
        "priceFrom": null,
        "variantCount": 0
      },
      "firstVariant": {}
    }
  ],
  "facets": {
    "count": 3,
    "prodBrand": {
      "buckets": []
    },
    "prodCollectionSlugs": {
      "buckets": [
        {
          "val": "flappers",
          "count": 2,
          "productsCount": 2
        },
        {
          "val": "toilet-tank-repair-parts",
          "count": 1,
          "productsCount": 1
        }
      ]
    },
    "variantPrice": {
      "buckets": [
        {
          "val": "[*, 100]",
          "count": 2,
          "productsCount": 2
        },
        {
          "val": "[100, 250]",
          "count": 0
        },
        {
          "val": "[250, 500]",
          "count": 0
        },
        {
          "val": "[500, 1000]",
          "count": 0
        },
        {
          "val": "[1000, 2000]",
          "count": 0
        },
        {
          "val": "[2000, *]",
          "count": 0
        }
      ]
    }
  }
}
```

Example 3: Using the response from Example 2, a secondary search is made in this example by selecting the 'variantPrice' facet to filter a specific price point range. The result filters out 1 item that is above the price point.

Any facet specifications can be specified with the 'fq' parameter. Some examples:
fq={"variantPrice":"[* TO 100]"} can be replaced by other facet specifications for example:
fq={"prodCollectionSlugs":"toilet-tank-repair-parts"}
fq={"brands":"brand_token"}
fq={"brands":["brand_token1", "brand_token2"]}


### HTTP Request
`GET https://storeapi.csomni.com/products/solr?parsedQ=flapper&fq={"variantPrice":"[* TO 100]"}&rows=20&start=0&responseData=firstVariant,variantAggregates&facets=1`

Sample in Shell:

```shell
curl --request GET \
--url https://storeapi.csomni.com/products/solr?parsedQ=flapper&fq={"variantPrice":"[* TO 100]"}&rows=20&start=0&responseData=firstVariant,variantAggregates&facets=1 \
--header 'token: site_xxxxxxxxxx'
```

> The above command returns the response JSON structured like this:

```json
{
  "numFound": 2,
  "start": 0,
  "numFoundExact": true,
  "docs": [
    {
      "prodToken": "prod_J6Kcyx43Xefz44DZ",
      "prodName": "KORKY TOILET FLAPPER BLACK 316540",
      "prodImage": {
        "file": "11-13-2022\/1668373988001__3802__72102.jpg",
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
      "prodDescription": "",
      "prodHighlights": "",
      "prodAlert": "",
      "prodLowlevel": "",
      "prodSlug": "korky-toilet-flapper-black-316540",
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
      "prodAccessories": [],
      "google_prodCategory": "",
      "google_prodType": "",
      "google_prodCondition": "",
      "archived": 0,
      "backOrderWarning": 0,
      "createdAt": "2022-12-18 23:01:00",
      "editedAt": "2022-12-18 23:01:00",
      "prodCollections": [
        "clcs_IdT3XKUXXIqBybaN"
      ],
      "variantInfo": {
        "priceTo": 0,
        "priceFrom": 0,
        "variantCount": 1
      },
      "firstVariant": {
        "prodToken": "prod_J6Kcyx43Xefz44DZ",
        "variantToken": "vrnt_7lCrBWvVut8oMjUQ",
        "variantName": "",
        "variantImage": {
          "file": "11-13-2022\/1668373988001__3802__72102.jpg",
          "type": ""
        },
        "variantImages": [],
        "variantWeight": "0",
        "variantDimW": "0",
        "variantDimL": "0",
        "variantDimH": "0",
        "variantUpc": "",
        "variantNumber": "72102",
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
        "inventoryCount": -1,
        "shippingProduct": 0,
        "variantMetaTitle": "",
        "variantMetaDescription": "",
        "variantBrand": "",
        "sortOrder": 0,
        "dateCreated": "1668373994",
        "deleted": 0,
        "backOrderWarning": 0,
        "createdAt": "2022-12-18 23:01:04",
        "editedAt": "2023-05-29 13:28:50",
        "variantInStock": true
      }
    },
    {
      "prodToken": "prod_HMvvCv8wA3oe6f9f",
      "prodName": "FLUIDMASTERS FLAPPER PERFORMANCE 502",
      "prodImage": {
        "file": "11-9-2022\/1668007722412__6537__502P21.jpg",
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
      "prodDescription": "",
      "prodHighlights": "",
      "prodAlert": "",
      "prodLowlevel": "",
      "prodSlug": "fluidmasters-flapper-performance-502",
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
      "prodAccessories": [],
      "google_prodCategory": "",
      "google_prodType": "",
      "google_prodCondition": "",
      "archived": 0,
      "backOrderWarning": 0,
      "createdAt": "2022-12-18 23:01:00",
      "editedAt": "2024-01-18 13:58:34",
      "prodCollections": [
        "clcs_IdT3XKUXXIqBybaN",
        "clcs_KHPYhbf6eOGsaCJo"
      ],
      "variantInfo": {
        "priceTo": 0,
        "priceFrom": 0,
        "variantCount": 1
      },
      "firstVariant": {
        "prodToken": "prod_HMvvCv8wA3oe6f9f",
        "variantToken": "vrnt_KewgBZoZD0ePWdyV",
        "variantName": "",
        "variantImage": {
          "file": "11-9-2022\/1668007722412__6537__502P21.jpg",
          "type": ""
        },
        "variantImages": [],
        "variantWeight": "2",
        "variantDimW": "0",
        "variantDimL": "0",
        "variantDimH": "0",
        "variantUpc": "",
        "variantNumber": "502P21",
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
        "google_variantCategory": "",
        "google_variantType": "",
        "google_variantCondition": "",
        "taxable": 1,
        "variantAllowCheckout": 0,
        "variantCheckInvetory": 0,
        "variantTrackInventory": 0,
        "inventoryCount": -13,
        "shippingProduct": 0,
        "variantMetaTitle": "",
        "variantMetaDescription": "",
        "variantBrand": "",
        "sortOrder": 0,
        "dateCreated": "1668007746",
        "deleted": 0,
        "backOrderWarning": 0,
        "createdAt": "2022-12-18 23:01:04",
        "editedAt": "2024-01-25 18:59:37",
        "variantInStock": true
      }
    }
  ],
  "facets": {
    "count": 2,
    "prodBrand": {
      "buckets": []
    },
    "prodCollectionSlugs": {
      "buckets": [
        {
          "val": "flappers",
          "count": 2,
          "productsCount": 2
        },
        {
          "val": "toilet-tank-repair-parts",
          "count": 1,
          "productsCount": 1
        }
      ]
    },
    "variantPrice": {
      "buckets": [
        {
          "val": "[*, 100]",
          "count": 2,
          "productsCount": 2
        },
        {
          "val": "[100, 250]",
          "count": 0
        },
        {
          "val": "[250, 500]",
          "count": 0
        },
        {
          "val": "[500, 1000]",
          "count": 0
        },
        {
          "val": "[1000, 2000]",
          "count": 0
        },
        {
          "val": "[2000, *]",
          "count": 0
        }
      ]
    }
  }
}
```

## Get a Specific Product
This endpoint retrieves a Specific Product.

### HTTP Request

`GET https://storeapi.csomni.com/products/[prodToken||slug]`

### Header Parameters
| Parameter     | Required | Type   | Description       |
|---------------|----------|--------|-------------------|
| siteToken     | true     | string | Site ID token     |

### URL Parameters
| Parameter     | Type   | Description                         |
|---------------|--------|-------------------------------------|
| Product Token | string | Token of the Product to retrieve OR |
| Slug          | string | OR a slug of the product            |

Sample in Shell:

```shell
curl --request GET \
  --url https://storeapi.csomni.com/products/3-4-in-o-d-satin-nickel-drive-in-spring-loaded-ball-style-cabinet-door-latch-with-strike- \
  --header 'token: site_xxxxxxxxxxx'
```

> The above command returns JSON structured like this:

```json
{
  "prodToken": "prod_Q73DQtIhj9IJzZ0y",
  "prodName": "3\/4 IN. O.D. SATIN NICKEL DRIVE-IN, SPRING LOADED, BALL STYLE, CABINET DOOR LATCH WITH STRIKE\t",
  "prodImage": {
    "file": "11-25-2022\/1669391493868__30709__NS-35859.jpg",
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
  "prodDescription": "",
  "prodHighlights": "",
  "prodAlert": "",
  "prodLowlevel": "",
  "prodSlug": "3-4-in-o-d-satin-nickel-drive-in-spring-loaded-ball-style-cabinet-door-latch-with-strike-",
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
  "prodAccessories": [],
  "google_prodCategory": "",
  "google_prodType": "",
  "google_prodCondition": "",
  "archived": 0,
  "backOrderWarning": 0,
  "createdAt": "2022-12-18 23:01:00",
  "editedAt": "2022-12-18 23:01:00",
  "prodCollections": [
    "clcs_DMtKEagwAAPjuKy7"
  ],
  "variantInfo": {
    "priceTo": 0.3,
    "priceFrom": 0.3,
    "variantCount": 1
  }
}
```


## Get a Full Product (options,variants)
This endpoint retrieves a full product and all its information.

### HTTP Request

`GET https://storeapi.csomni.com/products/[prodToken||slug]/full`

### URL Parameters
| Parameter     | Type   | Description                                                                                   |
|---------------|--------|-----------------------------------------------------------------------------------------------|
| Product Token | string | Token of the Product to retrieve.                                                             |
| Slug          | string | OR a slug of the product                                                                      |
| full          | string | To get the whole product and all its variants and options                                     |
| responseData  | string | comma delimited list of response data (full,fullAccessories,specialValues,specs,firstVariant) |


### Response data option breakdown:
| Parameter       | Description                                                  |
|-----------------|--------------------------------------------------------------|
| full            | Returns All variants on the product                          |
| specs           | Returns Specs on the product and variant                     |
| specialValues   | Returns Special Values on the product and variant            |
| firstVariant    | Returns only the first variant on the product (as an object) |
| fullAccessories | Returns array of accessory products                          |

#### Example 1: Get full basic product

Sample in Shell:

```shell
curl --request GET \
  --url https://storeapi.csomni.com/products/prod_Q73DQtIhj9IJzZ0y/full \
  --header 'token: site_xxxxxxxxx'
```

> The above command returns JSON structured like this:

```json
{
  "prodToken": "prod_Q73DQtIhj9IJzZ0y",
  "prodName": "3\/4 IN. O.D. SATIN NICKEL DRIVE-IN, SPRING LOADED, BALL STYLE, CABINET DOOR LATCH WITH STRIKE\t",
  "prodImage": {
    "file": "11-25-2022\/1669391493868__30709__NS-35859.jpg",
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
  "prodDescription": "",
  "prodHighlights": "",
  "prodAlert": "",
  "prodLowlevel": "",
  "prodSlug": "3-4-in-o-d-satin-nickel-drive-in-spring-loaded-ball-style-cabinet-door-latch-with-strike-",
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
  "prodAccessories": [],
  "google_prodCategory": "",
  "google_prodType": "",
  "google_prodCondition": "",
  "archived": 0,
  "backOrderWarning": 0,
  "createdAt": "2022-12-18 23:01:00",
  "editedAt": "2022-12-18 23:01:00",
  "prodCollections": [
    "clcs_DMtKEagwAAPjuKy7"
  ],
  "variantInfo": {
    "priceTo": 0.3,
    "priceFrom": 0.3,
    "variantCount": 1
  },
  "variants": [
    {
      "prodToken": "prod_Q73DQtIhj9IJzZ0y",
      "variantToken": "vrnt_EvonkJQsR6fRbDtm",
      "variantName": "",
      "variantImage": {
        "file": "11-25-2022\/1669391493868__30709__NS-35859.jpg",
        "type": "",
        "id": "srn5s4aj",
        "status": "poolImages"
      },
      "variantImages": [],
      "variantWeight": "1",
      "variantDimW": "0",
      "variantDimL": "0",
      "variantDimH": "0",
      "variantUpc": "",
      "variantNumber": "NS-35859",
      "manufacturerPartNumber": "",
      "variantPrice": 0.3,
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
      "inventoryCount": -17,
      "shippingProduct": 1,
      "variantMetaTitle": "",
      "variantMetaDescription": "",
      "variantBrand": "",
      "sortOrder": 0,
      "dateCreated": "1669391499",
      "deleted": 0,
      "backOrderWarning": 0,
      "createdAt": "2022-12-18 23:01:04",
      "editedAt": "2024-06-19 10:10:30",
      "variantInStock": true
    }
  ]
}
```

#### Example 2: Get full detailed product with specs, special values and all variant details

Sample in Shell:

```shell
curl --request GET \
  --url https://storeapi.csomni.com/products/clariti-1-day?responseData=specialValues,specs,full \
  --header 'token: site_xxxxxxxxx'
```

> The above command returns JSON structured like this:

```json
{
    "prodToken": "prod_i3tYFqL7jkfHiYIz",
    "prodName": "clariti 1 day",
    "prodImage": {
        "type": ""
    },
    "prodImages": [],
    "prodWeight": 0,
    "prodDimW": "",
    "prodDimL": "",
    "prodDimH": "",
    "prodUpc": "",
    "prodNumber": "3",
    "prodPrice": ".00",
    "prodDescription": "",
    "prodHighlights": "",
    "prodAlert": "",
    "prodLowlevel": "",
    "prodSlug": "clariti-1-day",
    "prodVisible": 1,
    "prodAllowCheckout": 0,
    "prodCheckInvetory": 0,
    "prodTrackInventory": 0,
    "inventoryCount": 0,
    "shippingProduct": 0,
    "prodMetaTitle": "",
    "prodMetaDescription": "",
    "prodBrand": "brnd_vi1w38EXkr4gjKs0hzVB",
    "prodType": null,
    "prodTemplate": "",
    "prodAccessories": "",
    "google_prodCategory": "",
    "google_prodType": "",
    "google_prodCondition": "",
    "archived": 0,
    "backOrderWarning": 0,
    "createdAt": "2024-05-02 14:27:03",
    "editedAt": "2024-05-02 14:27:03",
    "prodCollections": [
        "clcs_nOF2XKA3QUrOEGB3"
    ],
    "variantInfo": {
        "priceTo": 60,
        "priceFrom": 60,
        "variantCount": 3
    },
    "specialValues": [
        {
            "valueName": "BC",
            "value": "8.6",
            "sortOrder": 0,
            "createdAt": "2024-05-02 14:27:03",
            "editedAt": "2024-05-02 14:27:03"
        },
        {
            "valueName": "DIA",
            "value": "14.1",
            "sortOrder": 1,
            "createdAt": "2024-05-02 14:27:03",
            "editedAt": "2024-05-02 14:27:03"
        }
    ],
    "specs": [],
    "prodOptions": [
        {
            "optionToken": "optn_YTDIRwX2IEVVlACreuiV",
            "optionName": "Power",
            "optionOrder": "0",
            "values": [
                "+125",
                "+150",
                "+175"
            ]
        }
    ],
    "variants": [
        {
            "prodToken": "prod_i3tYFqL7jkfHiYIz",
            "variantToken": "vrnt_G9hzpmT6SFdxPLho",
            "variantName": "power: +125",
            "variantImage": [],
            "variantImages": [],
            "variantWeight": "",
            "variantDimW": "",
            "variantDimL": "",
            "variantDimH": "",
            "variantUpc": "",
            "variantNumber": "3-p125",
            "manufacturerPartNumber": "",
            "variantPrice": 60,
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
            "dateCreated": "1714660161",
            "deleted": 0,
            "backOrderWarning": 0,
            "createdAt": "2024-05-02 14:29:21",
            "editedAt": "2024-05-02 14:29:21",
            "variantInStock": true,
            "specialValues": [],
            "specs": [],
            "variantOptions": [
                {
                    "optionToken": "optn_YTDIRwX2IEVVlACreuiV",
                    "optionValue": "+125",
                    "optionName": "Power"
                }
            ]
        },
        {
            "prodToken": "prod_i3tYFqL7jkfHiYIz",
            "variantToken": "vrnt_NSSjHV6l8ZdGmWGM",
            "variantName": "power: +150",
            "variantImage": {
                "file": "[]"
            },
            "variantImages": [],
            "variantWeight": "",
            "variantDimW": "",
            "variantDimL": "",
            "variantDimH": "",
            "variantUpc": "",
            "variantNumber": "3-p150",
            "manufacturerPartNumber": "",
            "variantPrice": 60,
            "variantMapPrice": 0,
            "variantMsrpPrice": 0,
            "variantDisplayPrice": -1,
            "variantDescription": "",
            "variantAlert": "",
            "variantLowlevel": "3",
            "variantSlug": "power-150",
            "variantVisible": 1,
            "taxType": "",
            "hideGoogleData": 0,
            "google_variantCategory": "",
            "google_variantType": "",
            "google_variantCondition": "",
            "taxable": 1,
            "variantAllowCheckout": 0,
            "variantCheckInvetory": 1,
            "variantTrackInventory": 0,
            "inventoryCount": 10,
            "shippingProduct": 0,
            "variantMetaTitle": "",
            "variantMetaDescription": "",
            "variantBrand": "",
            "sortOrder": 1,
            "dateCreated": "1714660163",
            "deleted": 0,
            "backOrderWarning": 0,
            "createdAt": "2024-05-02 14:29:23",
            "editedAt": "2024-05-02 14:30:40",
            "variantInStock": true,
            "specialValues": [],
            "specs": [],
            "variantOptions": [
                {
                    "optionToken": "optn_YTDIRwX2IEVVlACreuiV",
                    "optionValue": "+150",
                    "optionName": "Power"
                }
            ]
        },
        {
            "prodToken": "prod_i3tYFqL7jkfHiYIz",
            "variantToken": "vrnt_PqHLi55RksmPISZj",
            "variantName": "power: +175",
            "variantImage": [],
            "variantImages": [],
            "variantWeight": "",
            "variantDimW": "",
            "variantDimL": "",
            "variantDimH": "",
            "variantUpc": "",
            "variantNumber": "3-p175",
            "manufacturerPartNumber": "",
            "variantPrice": 60,
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
            "dateCreated": "1714663171",
            "deleted": 0,
            "backOrderWarning": 0,
            "createdAt": "2024-05-02 15:19:31",
            "editedAt": "2024-05-02 15:19:31",
            "variantInStock": true,
            "specialValues": [],
            "specs": [],
            "variantOptions": [
                {
                    "optionToken": "optn_YTDIRwX2IEVVlACreuiV",
                    "optionValue": "+175",
                    "optionName": "Power"
                }
            ]
        }
    ]
}
```
