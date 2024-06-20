# Products

## Get All Products
This endpoint retrieves products by solr

Example 1:
### HTTP Request
`GET https://storeapi.csomni.com/products/solr?parsedQ=&rows=20`

### Query Parameters
| Parameter                                                                                                                                                                                                                                                                                          | Required | Default | Description                                                                                                                         |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------|---------|-------------------------------------------------------------------------------------------------------------------------------------|
| parsedQ                                                                                                                                                                                                                                                                                            | false    | -       | If empty will bring in all values this will                                                                                         |
| do a search in catch all and in prodName,prodNumber,prodDescription,variantName,variantNumber,variantToken,variantUpc and prodUpc if it will match prodName or prodNumber etc. fully it'll return those items first else it'll only check in catchAll for partial matches. Example: parsedQ=laptop |
| start                                                                                                                                                                                                                                                                                              | false    | 0       | At which field to start                                                                                                             |
| rows                                                                                                                                                                                                                                                                                               | false    | 10      | Amount of rows to returns                                                                                                           |
| sort                                                                                                                                                                                                                                                                                               | false    | -       | Any field to sort by                                                                                                                |
| sortOrder                                                                                                                                                                                                                                                                                          | false    | asc     | asc (ascending) or desc (descending)                                                                                                |
| responseData                                                                                                                                                                                                                                                                                       | false    | -       | comma dilimited list of response data (full,variantAggregates,specs,specialValues,firstAggregate)                                   |
| fq                                                                                                                                                                                                                                                                                                 | false    | -       | A list of filters (for example if you want to show items from specific collection put fq={"prodCollectionSlugs":"collection-name"}) |
| facets                                                                                                                                                                                                                                                                                             | false    | -       | put the value 1 if you want to get facets for the results.                                                                          |

when user selects a Facet. Let's say brand:brnd_123, add it to the filter query JSON object. To search by multiptple
brands,put an array, do like this: fq={"prodCollectionSlugs":["brnd_1","brnd_2"]} to search for range do fq={"
variantPrice":"[* TO 500]"} where \* is anything.

### Response Data Options

| Parameter         | Description                                                   |
|-------------------|---------------------------------------------------------------|
| full              | Returns All variants on the product                           |
| variantAggregates | Returns the varinat count, highest and lowest priced variants |
| specs             | Returns Specs on the product and variant                      |
| specialValues     | Returns Special Values on the product and variant             |
| firstVariant      | Returns only the first variant on the product (as an object)  |
| fullAccessories   | Returns array of accessory products                           |


```shell
curl --request GET \
  --url https://storeapi.csomni.com/products/solr?parsedQ=flap&rows=6 \
  --header 'token: site_xxxxxxxxxx'
```

> The above command returns the response JSON structured like this:

```json
{
  "numFound": 19,
  "start": 0,
  "numFoundExact": true,
  "docs":[
            {
                      "prodToken": "prod_Ar890Yysu525DowM",
                      "prodName": "KORKY 525BP UNIVERSAL TOILET FLAPPER BLUE",
                      "prodImage": {
                          "file": "1-19-2023\/1674146138554__133110__NS-525.jpg",
                          "type": ""
                      },
                      "prodImages": [],
                      "prodWeight": 0,
                      "prodDimW": "0",
                      "prodDimL": "",
                      "prodDimH": "",
                      "prodUpc": "",
                      "prodNumber": "",
                      "prodPrice": ".00",
                      "prodDescription": "",
                      "prodHighlights": "",
                      "prodAlert": "",
                      "prodLowlevel": "",
                      "prodSlug": "korky-525bp-universal-toilet-flapper-blue",
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
                      "backOrderWarning": 0,
                      "createdAt": "2023-06-21 21:20:33",
                      "editedAt": "2023-06-21 21:20:33",
                      "prodCollections": [
                          "clcs_IdT3XKUXXIqBybaN"
                      ],
                      "variantInfo": {
                          "priceTo": 2.7,
                          "priceFrom": 2.7,
                          "variantCount": 1
                      }
                  },
                  {
                      "prodToken": "prod_kp1eGuTl4MHaeove",
                      "prodName": "KORKY TOILET FLAPPER, RUBBER, BLACK #50BP",
                      "prodImage": {
                          "file": "1-11-2023\/1673480469634__70901__50BP.jpg",
                          "type": ""
                      },
                      "prodImages": [],
                      "prodWeight": 0,
                      "prodDimW": "0",
                      "prodDimL": "",
                      "prodDimH": "",
                      "prodUpc": "",
                      "prodNumber": "",
                      "prodPrice": ".00",
                      "prodDescription": "",
                      "prodHighlights": "",
                      "prodAlert": "",
                      "prodLowlevel": "",
                      "prodSlug": "korky-toilet-flapper-rubber-black-50bp",
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
                      "backOrderWarning": 0,
                      "createdAt": "2023-06-21 21:20:33",
                      "editedAt": "2023-06-21 21:20:33",
                      "prodCollections": [
                          "clcs_IdT3XKUXXIqBybaN"
                      ],
                      "variantInfo": {
                          "priceTo": 3.24,
                          "priceFrom": 3.24,
                          "variantCount": 1
                      }
                  },...
          ]
}
```

Example 2:
### HTTP Request
`GET https://storeapi.csomni.com/products/solr?parsedQ=flapper&fq={}&rows=20&start=0&responseData=firstVariant,variantAggregates&facets=1`

```shell
curl --request GET \
--url https://storeapi.csomni.com/products/solr?parsedQ=flapper&fq={}&rows=20&start=0&responseData=firstVariant,variantAggregates&facets=1 \
--header 'token: site_xxxxxxxxxx'
```

> The above command returns the response JSON structured like this:

```json
{
    "numFound": 18,
    "start": 0,
    "numFoundExact": true,
    "docs": [
        {
            "prodToken": "prod_Ar890Yysu525DowM",
            "prodName": "KORKY 525BP UNIVERSAL TOILET FLAPPER BLUE",
            "prodImage": {
                "file": "1-19-2023\/1674146138554__133110__NS-525.jpg",
                "type": ""
            },
            "prodImages": [],
            "prodWeight": 0,
            "prodDimW": "0",
            "prodDimL": "",
            "prodDimH": "",
            "prodUpc": "",
            "prodNumber": "",
            "prodPrice": ".00",
            "prodDescription": "",
            "prodHighlights": "",
            "prodAlert": "",
            "prodLowlevel": "",
            "prodSlug": "korky-525bp-universal-toilet-flapper-blue",
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
            "backOrderWarning": 0,
            "createdAt": "2023-06-21 21:20:33",
            "editedAt": "2023-06-21 21:20:33",
            "prodCollections": [
                "clcs_IdT3XKUXXIqBybaN"
            ],
            "variantInfo": {
                "priceTo": 2.7,
                "priceFrom": 2.7,
                "variantCount": 1
            },
            "firstVariant": {
                "prodToken": "prod_Ar890Yysu525DowM",
                "variantToken": "vrnt_LlDZqIJNEfvVAAwT",
                "variantName": "",
                "variantImage": {
                    "file": "1-19-2023\/1674146138554__133110__NS-525.jpg",
                    "type": ""
                },
                "variantImages": [],
                "variantWeight": "0",
                "variantDimW": "0",
                "variantDimL": "0",
                "variantDimH": "0",
                "variantUpc": "",
                "variantNumber": "NS-525",
                "manufacturerPartNumber": "",
                "variantPrice": 2.7,
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
                "inventoryCount": 10000,
                "shippingProduct": 0,
                "variantMetaTitle": "",
                "variantMetaDescription": "",
                "variantBrand": "",
                "sortOrder": 0,
                "dateCreated": "1674146144",
                "deleted": 0,
                "backOrderWarning": 0,
                "createdAt": "2023-06-21 21:20:36",
                "editedAt": "2023-08-21 20:21:30",
                "variantInStock": true
            }
        },
        {
            "prodToken": "prod_kp1eGuTl4MHaeove",
            "prodName": "KORKY TOILET FLAPPER, RUBBER, BLACK #50BP",
            "prodImage": {
                "file": "1-11-2023\/1673480469634__70901__50BP.jpg",
                "type": ""
            },
            "prodImages": [],
            "prodWeight": 0,
            "prodDimW": "0",
            "prodDimL": "",
            "prodDimH": "",
            "prodUpc": "",
            "prodNumber": "",
            "prodPrice": ".00",
            "prodDescription": "",
            "prodHighlights": "",
            "prodAlert": "",
            "prodLowlevel": "",
            "prodSlug": "korky-toilet-flapper-rubber-black-50bp",
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
            "backOrderWarning": 0,
            "createdAt": "2023-06-21 21:20:33",
            "editedAt": "2023-06-21 21:20:33",
            "prodCollections": [
                "clcs_IdT3XKUXXIqBybaN"
            ],
            "variantInfo": {
                "priceTo": 3.24,
                "priceFrom": 3.24,
                "variantCount": 1
            },
            "firstVariant": {
                "prodToken": "prod_kp1eGuTl4MHaeove",
                "variantToken": "vrnt_siVUJmd5Ihw2OnQL",
                "variantName": "",
                "variantImage": {
                    "file": "1-11-2023\/1673480469634__70901__50BP.jpg",
                    "type": ""
                },
                "variantImages": [],
                "variantWeight": "0",
                "variantDimW": "0",
                "variantDimL": "0",
                "variantDimH": "0",
                "variantUpc": "",
                "variantNumber": "50BP",
                "manufacturerPartNumber": "",
                "variantPrice": 3.24,
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
                "inventoryCount": 10000,
                "shippingProduct": 0,
                "variantMetaTitle": "",
                "variantMetaDescription": "",
                "variantBrand": "",
                "sortOrder": 0,
                "dateCreated": "1673480474",
                "deleted": 0,
                "backOrderWarning": 0,
                "createdAt": "2023-06-21 21:20:36",
                "editedAt": "2023-08-21 20:18:23",
                "variantInStock": true
            }
        },
        {
            "prodToken": "prod_3juVe2E7nCeI3vIU",
            "prodName": "TOILET TANK FLAPPER FIT ALL",
            "prodImage": {
                "file": "1-16-2023\/1673905838358__14183__89385.jpg",
                "type": ""
            },
            "prodImages": [],
            "prodWeight": 0,
            "prodDimW": "0",
            "prodDimL": "",
            "prodDimH": "",
            "prodUpc": "",
            "prodNumber": "",
            "prodPrice": ".00",
            "prodDescription": "",
            "prodHighlights": "",
            "prodAlert": "",
            "prodLowlevel": "",
            "prodSlug": "toilet-tank-flapper-fit-all",
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
            "backOrderWarning": 0,
            "createdAt": "2023-06-21 21:20:33",
            "editedAt": "2023-06-21 21:20:33",
            "prodCollections": [
                "clcs_IdT3XKUXXIqBybaN"
            ],
            "variantInfo": {
                "priceTo": 3.79,
                "priceFrom": 3.79,
                "variantCount": 1
            },
            "firstVariant": {
                "prodToken": "prod_3juVe2E7nCeI3vIU",
                "variantToken": "vrnt_FJaPr75CHmuN4i34",
                "variantName": "",
                "variantImage": {
                    "file": "1-16-2023\/1673905838358__14183__89385.jpg",
                    "type": ""
                },
                "variantImages": [],
                "variantWeight": "0",
                "variantDimW": "0",
                "variantDimL": "0",
                "variantDimH": "0",
                "variantUpc": "",
                "variantNumber": "89385",
                "manufacturerPartNumber": "",
                "variantPrice": 3.79,
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
                "inventoryCount": 10000,
                "shippingProduct": 0,
                "variantMetaTitle": "",
                "variantMetaDescription": "",
                "variantBrand": "",
                "sortOrder": 0,
                "dateCreated": "1673905841",
                "deleted": 0,
                "backOrderWarning": 0,
                "createdAt": "2023-06-21 21:20:36",
                "editedAt": "2023-08-21 20:20:38",
                "variantInStock": true
            }
        }
    ],
    "facets": {
        "count": 18,
        "prodBrand": {
            "buckets": []
        },
        "prodCollectionSlugs": {
            "buckets": [
                {
                    "val": "flappers",
                    "count": 15,
                    "productsCount": 15
                },
                {
                    "val": "toilet-tank-repair-parts",
                    "count": 4,
                    "productsCount": 4
                }
            ]
        },
        "variantPrice": {
            "buckets": [
                {
                    "val": "[*, 100]",
                    "count": 18,
                    "productsCount": 18
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
| Parameter     | Type   | Description                       |
|---------------|--------|-----------------------------------|
| Product Token | string | Token of the Product to retrieve. |
| Slug          | string | OR a slug of the product          |

```shell
curl --request GET \
  --url https://storeapi.csomni.com/products/[prodToken||slug] \
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
| responseData  | string | comma delimited list of response data (full,fullAccessories,specailValues,specs,firstVariant) |


### Data Parameters
| Parameter       | Description                                                  |
|-----------------|--------------------------------------------------------------|
| full            | Returns All variants on the product                          |
| specs           | Returns Specs on the product and variant                     |
| specialValues   | Returns Special Values on the product and variant            |
| firstVariant    | Returns only the first variant on the product (as an object) |
| fullAccessories | Returns array of accessory products                          |


```shell
curl --request GET \
  --url https://storeapi.csomni.com/products/[prodToken||slug]/full \
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

## Update Inventory Count

### HTTP Request

`POST https://storeapi.csomni.com/products/{token}`

### URL Parameters
| Parameter | Type   | Required | Description      |
|-----------|--------|----------|------------------|
| prodToken | string | true     | Product Token ID |


### Data Parameters
| Parameter | Type   | Required | Description |
|-----------|--------|----------|-------------|
| count     | string | true     | Stock level |

```shell
curl --request POST \
  --url https://storeapi.csomni.com/products/{prodToken} \
  --header 'token: site_xxxxxxxxxx'\
  --data '{ "count" :3" }'

```

Response:

```json
{
  "status": "success",
  "count": 2
}
```