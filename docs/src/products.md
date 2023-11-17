# Products

## Get a Specific Product

```shell
curl --request GET \
  --url https://storeapi.csomni.com/products/[prodToken||slug] \
  --header 'token: 123'
```

> The above command returns JSON structured like this:

```json
{
  "prodToken": "prod_CopF1h0dqzc9mR61",
  "companyToken": "comp_sfgb50s0dsdgsfh5g",
  "prodName": "No moref",
  "prodImage": {
    "file": "11-24-2020/1606237454516__1133421__1605838189835__12153371__ad_-_11X17_-_Copy.jpg"
  },
  "prodImages": [],
  "prodWeight": "",
  "prodDimW": "",
  "prodDimL": "",
  "prodDimH": "",
  "prodUpc": "",
  "prodNumber": "",
  "prodPrice": 0,
  "prodDescription": "<p>asdf</p>",
  "prodHighlights": "<p>adsfadsf</p>",
  "prodAlert": "",
  "prodLowlevel": "",
  "prodSlug": "fffff",
  "prodVisible": 1,
  "prodAllowCheckout": 0,
  "prodCheckInvetory": 0,
  "prodTrackInventory": 0,
  "inventoryCount": "0",
  "shippingProduct": 0,
  "prodMetaTitle": "",
  "prodMetaDescription": "",
  "prodBrand": "brnd_dNX2r7qA7GRw8smMRrHI",
  "prodType": "",
  "prodTemplate": "fdsa",
  "prodAccessories": [
    "prod_dgHZuXkYjXsTF7ZB",
    "prod_lkg9GfQ1PSS1QvLF"
  ],
  "google_prodCategory": "",
  "google_prodType": "",
  "google_prodCondition": "",
  "backOrderWarning": 0,
  "prodCollections": [
    "clcs_vFPTXp7oQu0XcV7S",
    "clcs_B216qbvH9CNBbJyr",
    "clcs_B216qbvH9CNBbJyr",
    "clcs_pLae516pzjDsAndI"
  ],
  "variantInfo": {
    "priceTo": 0,
    "priceFrom": 0,
    "variantCount": 4
  },
  "prodOptions": [
    {
      "optionToken": "optn_IoKsm82SMC5ImEg9jmOe",
      "optionName": "size",
      "optionOrder": ""
    },
    {
      "optionToken": "optn_4ICF2Y9Iz1eqEYEXxbmc",
      "optionName": "color",
      "optionOrder": "1"
    }
  ]
}
```

This endpoint retrieves a Specific Product.

### HTTP Request

`GET https://storeapi.csomni.com/products/[prodToken||slug]`

### URL Parameters

| Parameter     | Description                       |
| ------------- | --------------------------------- |
| Product Token | Token of the Product to retrieve. |
| Slug          | OR a slug of the product          |

## Get a Full Product (options,variants)

```shell
curl --request GET \
  --url https://storeapi.csomni.com/products/[prodToken||slug]/full \
  --header 'token: 123'
```

> The above command returns JSON structured like this:

```json
       {
  "prodToken": "prod_CopF1h0dqzc9mR61",
  "companyToken": "comp_sfgb50s0dsdgsfh5g",
  "prodName": "No moref",
  "prodImage": {
    "file": "11-24-2020/1606237454516__1133421__1605838189835__12153371__ad_-_11X17_-_Copy.jpg"
  },
  "prodImages": [],
  "prodWeight": "",
  "prodDimW": "",
  "prodDimL": "",
  "prodDimH": "",
  "prodUpc": "",
  "prodNumber": "",
  "prodPrice": 0,
  "prodDescription": "<p>asdf</p>",
  "prodHighlights": "<p>adsfadsf</p>",
  "prodAlert": "",
  "prodLowlevel": "",
  "prodSlug": "fffff",
  "prodVisible": 1,
  "prodAllowCheckout": 0,
  "prodCheckInvetory": 0,
  "prodTrackInventory": 0,
  "inventoryCount": "0",
  "shippingProduct": 0,
  "prodMetaTitle": "",
  "prodMetaDescription": "",
  "prodBrand": "brnd_dNX2r7qA7GRw8smMRrHI",
  "prodType": "",
  "prodTemplate": "fdsa",
  "prodAccessories": [
    "prod_dgHZuXkYjXsTF7ZB",
    "prod_lkg9GfQ1PSS1QvLF"
  ],
  "google_prodCategory": "",
  "google_prodType": "",
  "google_prodCondition": "",
  "backOrderWarning": 0,
  "prodCollections": [
    "clcs_vFPTXp7oQu0XcV7S",
    "clcs_B216qbvH9CNBbJyr",
    "clcs_B216qbvH9CNBbJyr",
    "clcs_pLae516pzjDsAndI"
  ],
  "variantInfo": {
    "priceTo": 0,
    "priceFrom": 0,
    "variantCount": 4
  },
  "prodOptions": [
    {
      "optionToken": "optn_IoKsm82SMC5ImEg9jmOe",
      "optionName": "size",
      "optionOrder": "",
      "values": [
        "lg",
        "sm"
      ]
    },
    {
      "optionToken": "optn_4ICF2Y9Iz1eqEYEXxbmc",
      "optionName": "color",
      "optionOrder": "1",
      "values": [
        "red"
      ]
    }
  ],
  "variants": [
    {
      "prodToken": "prod_CopF1h0dqzc9mR61",
      "variantToken": "vrnt_0IeDlg6B0RchCren",
      "companyToken": "comp_sfgb50s0dsdgsfh5g",
      "variantName": "ffffff",
      "variantImage": {
        "file": ""
      },
      "variantImages": [
        {
          "file": "11-24-2020/1606237454516__1133421__1605838189835__12153371__ad_-_11X17_-_Copy.jpg"
        }
      ],
      "variantWeight": "1",
      "variantDimW": "0",
      "variantDimL": "0",
      "variantDimH": "0",
      "variantUpc": "",
      "variantNumber": "pppppppppppppppppppppppppppppppppppppppppp",
      "manufacturerPartNumber": "",
      "variantPrice": 0,
      "variantMapPrice": 0,
      "variantMsrpPrice": 0,
      "variantDisplayPrice": 0,
      "variantDescription": "",
      "variantAlert": "",
      "variantLowlevel": "",
      "variantSlug": "ffffff",
      "variantVisible": 1,
      "variantAllowCheckout": 0,
      "variantCheckInvetory": 0,
      "variantTrackInventory": 0,
      "taxType": "",
      "taxable": 1,
      "inventoryCount": "8",
      "shippingProduct": 1,
      "variantMetaTitle": "",
      "variantMetaDescription": "",
      "variantBrand": "",
      "google_variantCategory": "",
      "google_variantType": "",
      "google_variantCondition": "",
      "hideGoogleData": 0,
      "sortOrder": 0,
      "dateCreated": "1610566995",
      "deleted": 0,
      "backOrderWarning": 0,
      "variantInStock": true,
      "variantOptions": [
        {
          "optionToken": "optn_IoKsm82SMC5ImEg9jmOe",
          "optionValue": "sm",
          "optionName": "size"
        },
        {
          "optionToken": "optn_4ICF2Y9Iz1eqEYEXxbmc",
          "optionValue": "red",
          "optionName": "color"
        }
      ]
    },
    {
      "prodToken": "prod_CopF1h0dqzc9mR61",
      "variantToken": "vrnt_qmrYL7X1JnIfSfls",
      "companyToken": "comp_sfgb50s0dsdgsfh5g",
      "variantName": "ffffff",
      "variantImage": {
        "file": ""
      },
      "variantImages": [
        {
          "file": "11-24-2020/1606237454516__1133421__1605838189835__12153371__ad_-_11X17_-_Copy.jpg"
        }
      ],
      "variantWeight": "1",
      "variantDimW": "0",
      "variantDimL": "0",
      "variantDimH": "0",
      "variantUpc": "",
      "variantNumber": "pppppppppppppppppppppppppppppppppppppppppp",
      "manufacturerPartNumber": "",
      "variantPrice": 0,
      "variantMapPrice": 0,
      "variantMsrpPrice": 0,
      "variantDisplayPrice": 0,
      "variantDescription": "",
      "variantAlert": "",
      "variantLowlevel": "",
      "variantSlug": "ffffff",
      "variantVisible": 1,
      "variantAllowCheckout": 0,
      "variantCheckInvetory": 0,
      "variantTrackInventory": 0,
      "taxType": "",
      "taxable": 1,
      "inventoryCount": "9",
      "shippingProduct": 1,
      "variantMetaTitle": "",
      "variantMetaDescription": "",
      "variantBrand": "",
      "google_variantCategory": "",
      "google_variantType": "",
      "google_variantCondition": "",
      "hideGoogleData": 0,
      "sortOrder": 0,
      "dateCreated": "1610566995",
      "deleted": 0,
      "backOrderWarning": 0,
      "variantInStock": true,
      "variantOptions": [
        {
          "optionToken": "optn_IoKsm82SMC5ImEg9jmOe",
          "optionValue": "lg",
          "optionName": "size"
        },
        {
          "optionToken": "optn_4ICF2Y9Iz1eqEYEXxbmc",
          "optionValue": "red",
          "optionName": "color"
        }
      ]
    },
    {
      "prodToken": "prod_CopF1h0dqzc9mR61",
      "variantToken": "vrnt_WSBp0UD2QJMrObF0",
      "companyToken": "comp_sfgb50s0dsdgsfh5g",
      "variantName": "",
      "variantImage": {
        "file": ""
      },
      "variantImages": [],
      "variantWeight": "0",
      "variantDimW": "0",
      "variantDimL": "0",
      "variantDimH": "0",
      "variantUpc": "",
      "variantNumber": "asdf;a",
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
      "variantAllowCheckout": 0,
      "variantCheckInvetory": 0,
      "variantTrackInventory": 0,
      "taxType": "",
      "taxable": 1,
      "inventoryCount": "0",
      "shippingProduct": 0,
      "variantMetaTitle": "",
      "variantMetaDescription": "",
      "variantBrand": "",
      "google_variantCategory": "",
      "google_variantType": "",
      "google_variantCondition": "",
      "hideGoogleData": 0,
      "sortOrder": 2,
      "dateCreated": "1622563231",
      "deleted": 0,
      "backOrderWarning": 0,
      "variantInStock": true
    },
    {
      "prodToken": "prod_CopF1h0dqzc9mR61",
      "variantToken": "vrnt_Z6fkKd8YqK5MImsU",
      "companyToken": "comp_sfgb50s0dsdgsfh5g",
      "variantName": "",
      "variantImage": {
        "file": ""
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
      "variantAllowCheckout": 0,
      "variantCheckInvetory": 0,
      "variantTrackInventory": 0,
      "taxType": "",
      "taxable": 1,
      "inventoryCount": "0",
      "shippingProduct": 0,
      "variantMetaTitle": "",
      "variantMetaDescription": "",
      "variantBrand": "",
      "google_variantCategory": "",
      "google_variantType": "",
      "google_variantCondition": "",
      "hideGoogleData": 0,
      "sortOrder": 4,
      "dateCreated": "1622563296",
      "deleted": 0,
      "backOrderWarning": 0,
      "variantInStock": true
    }
  ]
}  
```

This endpoint retrieves a Specific Product And all its information.

### HTTP Request

`GET https://storeapi.csomni.com/products/[prodToken||slug]/full`

### URL Parameters

| Parameter     | Description                                                                                                     |
| ------------- | --------------------------------------------------------------------------------------------------------------- |
| Product Token | Token of the Product to retrieve.                                                                               |
| Slug          | OR a slug of the product                                                                                        |
| full          | To get the whole product and all its variants and options                                                       |
| responseData  | comma dilimited list of response data (full,fullAccessories,specailValues,specs,firstVariant) |

### Response Data Options

| Parameter         | Description                                                   |
| ----------------- | ------------------------------------------------------------- |
| full              | Returns All variants on the product                           |
| specs             | Returns Specs on the product and variant                      |
| specialValues     | Returns Special Values on the product and variant             |
| firstVariant      | Returns only the first variant on the product (as an object)  |
| fullAccessories   | Returns array of accessory products                           |

## Get All Products

This endpoint retrieves all products

### HTTP Request

`GET https://storeapi.csomni.com/products/solr?parsedQ=&rows=20`

### Query Parameters

| Parameter                                                                                                                                                                                                 | Required | Default | Description                                                                                                                         |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- | ------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| parsedQ                                                                                                                                                                                                   | false    | -       | If empty will bring in all values this will                                                                                         |
| do a search in catch all and in prodName,prodNumber,prodDescription,variantName,variantNumber,variantToken,variantUpc and prodUpc if it will match prodName or prodNumber etc. fully it'll return those items first else it'll only check in catchAll for partial matches. Example: parsedQ=laptop |
| start                                                                                                                                                                                                     | false    | 0       | At which field to start                                                                                                             |
| rows                                                                                                                                                                                                      | false    | 10      | Amount of rows to returns                                                                                                           |
| sort                                                                                                                                                                                                      | false    | -       | Any field to sort by                                                                                                                |
| sortOrder                                                                                                                                                                                                 | false    | asc     | asc (ascending) or desc (descending)                                                                                                |
| responseData                                                                                                                                                                                              | false    | -       | comma dilimited list of response data (full,variantAggregates,specs,specialValues,firstAggregate)                                   |
| fq                                                                                                                                                                                                        | false    | -       | A list of filters (for example if you want to show items from specific collection put fq={"prodCollectionSlugs":"collection-name"}) |
| facets                                                                                                                                                                                                    | false    | -       | put the value 1 if you want to get facets for the results.                                                                          |

when user selects a Facet. Let's say brand:brnd_123, add it to the filter query JSON object. To search by multiptple
brands,put an array, do like this: fq={"prodCollectionSlugs":["brnd_1","brnd_2"]} to search for range do fq={"
variantPrice":"[* TO 500]"} where \* is anything.

### Response Data Options

| Parameter         | Description                                                   |
| ----------------- | ------------------------------------------------------------- |
| full              | Returns All variants on the product                           |
| variantAggregates | Returns the varinat count, highest and lowest priced variants |
| specs             | Returns Specs on the product and variant                      |
| specialValues     | Returns Special Values on the product and variant             |
| firstVariant      | Returns only the first variant on the product (as an object)  |
| fullAccessories   | Returns array of accessory products                           |

```shell
curl --request GET \
  --url https://storeapi.csomni.com/products/solr?parsedQ=flap&rows=6 \
  --header 'token: 123'
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
                      "companyToken": "comp_fxJJZhdcNMfRF9m",
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
                      "companyToken": "comp_fxJJZhdcNMfRF9m",
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
                  },
          ]
}
```

```shell
curl --request GET \
  --url https://storeapi.csomni.com/products/solr?parsedQ=flapper&fq={}&rows=20&start=0&responseData=firstVariant,variantAggregates&facets=1 \
  --header 'token: 123'
```

> The above command returns the response  JSON structured like this:


```json
{
    "numFound": 18,
    "start": 0,
    "numFoundExact": true,
    "docs": [
        {
            "prodToken": "prod_Ar890Yysu525DowM",
            "companyToken": "comp_fxJJZhdcNMfRF9m",
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
                "companyToken": "comp_fxJJZhdcNMfRF9m",
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
            "companyToken": "comp_fxJJZhdcNMfRF9m",
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
                "companyToken": "comp_fxJJZhdcNMfRF9m",
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
            "companyToken": "comp_fxJJZhdcNMfRF9m",
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
                "companyToken": "comp_fxJJZhdcNMfRF9m",
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
## Update Inventory Count

### HTTP Request

`POST https://storeapi.csomni.com/products/{token}`

### QUERY Parameters

| Parameter     | Required | Description            |
| ------------- | -------- | ---------------------- |
| count | true     | count of product     |

```shell
curl --request POST \
  --url https://api.omnifront.cloudsnob.com/products/{token} \
  --header 'cache-control: no-cache' \
  --header 'postman-token: e0dee5b6-94b0-0dd3-f67d-b88804ec5b74' \
    --header 'token: 123'\
  --header 'customerToken: cs_DWCQeqvYAIeWYYzJ1MgAZbXUdUW76Xav4paw' \
  --data '{ "count" :3"  }'

```

Response:

```json
{
  "status": "success",
  "count": 2
}
```