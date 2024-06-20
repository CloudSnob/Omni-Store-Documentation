# Navigations

## Get all navigations
This endpoint retrieves a full navigation list

### HTTP Request
`GET https://storeapi.csomni.com/navigations`

### Header Parameters
| Parameter     | Required | Type   | Unique | Description |
|---------------|----------|--------|--------|-------------|
| token         | true     | string | true   | Site ID     |


### URL Parameters
| Parameter       | Description                      |
|-----------------|----------------------------------|
| navigationToken | The navigation ID to retreive OR |
| navigationSlug  | The navigation slug to retreive  |


### Response Data (Add as GET param ?responeData) comma delimited
| Option            | Description                                     |
|-------------------|-------------------------------------------------|
| fullProducts      | Return the full product (Product with variants) |
| variantAggregates | Return the variant aggregates on each variant   |

```shell
curl --request GET \
  --url https://storeapi.csomni.com/navigations\
  --header 'token: site_xxxxxxxxxxx'
```

> The above command returns JSON structured like this:

```json
[
  {
    "navigationToken": "nav_0F2Bz4vY7qRgwlde",
    "name": "Janitorial",
    "slug": "janitorial",
    "navigationImage": "5-26-2021\/1622045767391__148741__janitorial.png",
    "createdAt": "2022-12-18 23:00:57",
    "editedAt": "2022-12-18 23:00:57"
  },
  {
    "navigationToken": "nav_3BtFrQubtdfMCtoE",
    "name": "Hardware",
    "slug": "hardware",
    "navigationImage": "5-26-2021\/1622066629268__124781__hardware.png",
    "createdAt": "2022-12-18 23:00:57",
    "editedAt": "2022-12-18 23:00:57"
  },
  {
    "navigationToken": "nav_NSECtcUKMs2dHab4",
    "name": "Plumbing",
    "slug": "plumbing",
    "navigationImage": "5-26-2021\/1622045798493__123758__plumbing.png",
    "createdAt": "2022-12-18 23:00:57",
    "editedAt": "2022-12-18 23:00:57"
  },
  {
    "navigationToken": "nav_OZm6qkDjJmpoqbXH",
    "name": "Building Supplies",
    "slug": "building-supplies",
    "navigationImage": "5-26-2021\/1622045814745__199202__building-supplies.png",
    "createdAt": "2022-12-18 23:00:57",
    "editedAt": "2023-09-28 19:28:52"
  },
  {
    "navigationToken": "nav_Y80CxhQ0HaHdpF4U",
    "name": "Lighting",
    "slug": "lighting",
    "navigationImage": "5-26-2021\/1622045823730__95344__lighting.png",
    "createdAt": "2022-12-18 23:00:57",
    "editedAt": "2022-12-18 23:00:57"
  },
  {
    "navigationToken": "nav_ef03mxaoGzHyFaop",
    "name": "Tools",
    "slug": "tools",
    "navigationImage": "5-26-2021\/1622045833708__133255__tools.png",
    "createdAt": "2022-12-18 23:00:57",
    "editedAt": "2022-12-18 23:00:57"
  }
]
```
## Get navigation by id or slug
This endpoint retrieves a navigation by navigationToken or slug

### HTTP Request
`GET https://storeapi.csomni.com/navigations/{navigationToken/navigationSlug}`

### Header Parameters
| Parameter     | Required | Type   | Unique | Description |
|---------------|----------|--------|--------|-------------|
| token         | true     | string | true   | Site ID     |


### URL Parameters
| Parameter       | Description                      |
|-----------------|----------------------------------|
| navigationToken | The navigation ID to retrieve OR |
| navigationSlug  | The navigation slug to retrieve  |


### Response Data (Add as GET param ?responeData) comma delimited
| Option            | Description                                     |
|-------------------|-------------------------------------------------|
| fullProducts      | Return the full product (Product with variants) |
| variantAggregates | Return the variant aggregates on each variant   |

```shell
curl --request GET \
  --url https://storeapi.csomni.com/navigations/{navigationToken/navigationSlug} \
  --header 'token: site_xxxxxxxxxxx'
```

> The above command returns JSON structured like this:
 ```json
{
  "navigationToken": "nav_0F2Bz4vY7qRgwlde",
  "name": "Janitorial",
  "slug": "janitorial",
  "navigationImage": "5-26-2021\/1622045767391__148741__janitorial.png",
  "createdAt": "2022-12-18 23:00:57",
  "editedAt": "2022-12-18 23:00:57",
  "items": [
    {
      "id": 966,
      "navigationToken": "nav_0F2Bz4vY7qRgwlde",
      "navigationItemToken": "navI_mU5ys7MbZ8mJ2t4I",
      "itemType": "collection",
      "itemToken": "clcs_MWyWZa1BkzjOKJsw",
      "sort": 0,
      "createdAt": "2022-12-18 23:00:57",
      "editedAt": "2022-12-18 23:00:57",
      "fullItem": {
        "collectionToken": "clcs_MWyWZa1BkzjOKJsw",
        "collectionName": "Cleaners & Degreasers",
        "collectionDefaultSort": "",
        "collectionSlug": "cleaners-degreasers",
        "collectionDescription": "",
        "collectionImage": "4-14-2021\/1618422410531__24516__01019.jpg",
        "archived": 0,
        "hideCollection": 1,
        "collectionMetaTitle": "",
        "collectionMetaDescription": "",
        "collectionSortOrder": 0,
        "collectionBrand": "",
        "createdAt": "2022-12-18 23:01:01",
        "editedAt": "2023-11-29 11:38:54",
        "active": 1
      }
    },
    {
      "id": 967,
      "navigationToken": "nav_0F2Bz4vY7qRgwlde",
      "navigationItemToken": "navI_q4DLB7yQLcAELs7i",
      "itemType": "collection",
      "itemToken": "clcs_759czs0N8JyAczpL",
      "sort": 1,
      "createdAt": "2022-12-18 23:00:57",
      "editedAt": "2022-12-18 23:00:57",
      "fullItem": {
        "collectionToken": "clcs_759czs0N8JyAczpL",
        "collectionName": "Floor Cleaning & Deodorant",
        "collectionDefaultSort": "",
        "collectionSlug": "janitorial",
        "collectionDescription": "\nfor cleaning",
        "collectionImage": "6-23-2021\/1624461506141__314197__Cherry.jpg",
        "archived": 0,
        "hideCollection": 1,
        "collectionMetaTitle": "",
        "collectionMetaDescription": "",
        "collectionSortOrder": 0,
        "collectionBrand": "",
        "createdAt": "2022-12-18 23:01:01",
        "editedAt": "2023-11-29 11:32:48",
        "active": 1
      }
    },
    {
      "id": 965,
      "navigationToken": "nav_0F2Bz4vY7qRgwlde",
      "navigationItemToken": "navI_AqU3sFgXu9tyXegy",
      "itemType": "collection",
      "itemToken": "clcs_YN3mO1E6k64ugiVp",
      "sort": 2,
      "createdAt": "2022-12-18 23:00:57",
      "editedAt": "2022-12-18 23:00:57",
      "fullItem": {
        "collectionToken": "clcs_YN3mO1E6k64ugiVp",
        "collectionName": "Hand Cleanerss",
        "collectionDefaultSort": "",
        "collectionSlug": "hand-cleaners",
        "collectionDescription": "",
        "collectionImage": "3-3-2021\/1614788533413__27020__01183.jpg",
        "archived": 0,
        "hideCollection": 0,
        "collectionMetaTitle": "",
        "collectionMetaDescription": "",
        "collectionSortOrder": 0,
        "collectionBrand": "",
        "createdAt": "2022-12-18 23:01:01",
        "editedAt": "2023-11-28 18:06:08",
        "active": 1
      }
    ]
  }

```
