# Customer Saved List


## Create New List

### HTTP Request
`POST https://storeapi.csomni.com/customeritemlist`

### Header Requirements
| Parameter     | Required | Unique | Description |
|---------------|----------|--------|-------------|
| token         | true     | true   | site id     |
| customerToken | true     | true   | customer id |


### Data Parameters
| Parameter        | Required | Type   | Description               |
|------------------|----------|--------|---------------------------|
| listReadableName | true     | string | Title for the list        |
| sortOrder        | true     | int    | Sort Order listing number |


Sample in Shell:

```shell
curl --request POST \
  --url https://storeapi.csomni.com/customeritemlist \
  --header 'token: site_xxxxxxxxxxx' \
   --header'customerToken: cs_xxxxxxxxxxxxxxx' 
  --data   '{
               "listReadableName":"Summer Holiday List",
               "sortOrder" : 0
             }'

```

Response:

```json
{
    "listToken": "custList_xxxxxxxxxxxxxxxxxxxxxx",
    "listReadableName": "Summer Holiday List"
}
```

## Add items to List

### HTTP Request

`POST https://storeapi.csomni.com/customeritemlist/{custListToken}`

### Header Requirements

| Parameter     | Required | Type   | Unique | Description |
|---------------|----------|--------|--------|-------------|
| token         | true     | string | true   | site ID     |
| customerToken | true     | string | true   | login ID    |

### Data Requirements

Expects an array of objects. 'listItems' includes multiple objects, each representing a list item to be added to the list. Requirements for list objects:

| Parameter             | Required | Type   | Unique | Description                                 |
|-----------------------|----------|--------|--------|---------------------------------------------|
| listItem:variantToken | true     | string | true   | variantToken                                |
| listItem:quantity     | true     | string | false  | quantity for variant                        |
| listItem:sortOrder    | true     | string | false  | Order in which this list item should appear |

&nbsp;

Sample in Shell:

```shell
curl --request POST \
  --url https://storeapi.csomni.com/customeritemlist/{custListToken}
  --header 'token: site_xxxxxxxxxx', 'customerToken: cs_xxxxxxxxxxxxxxxxxx' \
  --data '{
            "listItems": [
                {
                    "variantToken": "vrnt_1xxxxxxxxxxxxx",
                    "quantity": 1,
                    "sortOrder": 0
                },
                {
                    "variantToken": "vrnt_2xxxxxxxxxxxxx",
                    "quantity": 2,
                    "sortOrder": 1
                }
            ],
          }'

```

Response:

```json
{
  "listToken": "custList_xxxxxxxxxxxxxxx",
  "sortOrder": 0,
  "listReadableName": "Autumn List",
  "listItems": [
    {
      "itemToken": "listItem_xxxxxxxxxxx",
      "variantToken": "vrnt_1xxxxxxxxxxxxxxx",
      "quantity": 1,
      "sortOrder": 0,
      "variantDetails": {
        "prodToken": "prod_xxxxxxxxxxxxxxxxxxxxx",
        "variantToken": "vrnt_xxxxxxxxxxxxxxx",
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
    },
    {
      "itemToken": "listItem_xxxxxxxxxxxxxx",
      "variantToken": "vrnt_2xxxxxxxxxxxxx",
      "quantity": 2,
      "sortOrder": 1,
      "variantDetails": {
        "prodToken": "prod_xxxxxxxxxxxxxxxxxx",
        "variantToken": "vrnt_xxxxxxxxxxxxx",
        "variantName": "31\" WHITE CHINA SINK",
        "variantImage": {
          "file": "10-2-2022\/1664742840284__7264__VE3118W.jpg",
          "type": ""
        },
        "variantImages": [],
        "variantWeight": "0",
        "variantDimW": "0",
        "variantDimL": "0",
        "variantDimH": "0",
        "variantUpc": "",
        "variantNumber": "VE3118W",
        "manufacturerPartNumber": "",
        "variantPrice": 0.25,
        "variantMapPrice": 0,
        "variantMsrpPrice": 0,
        "variantDisplayPrice": 0,
        "variantDescription": "",
        "variantAlert": "",
        "variantLowlevel": "",
        "variantSlug": "31-white-china-sink",
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
        "inventoryCount": 180,
        "shippingProduct": 0,
        "variantMetaTitle": "",
        "variantMetaDescription": "",
        "variantBrand": "",
        "sortOrder": 0,
        "dateCreated": "1661531956",
        "deleted": 0,
        "backOrderWarning": 0,
        "createdAt": "2022-12-18 23:01:04",
        "editedAt": "2024-06-20 08:41:56",
        "variantInStock": true
      }
    }
  ],
  "totalItemsCount": 3
}
```


## Edit List Name or Sort Order

### HTTP Request

`PUT https://storeapi.csomni.com/customeritemlist/{listToken}`

### Header Parameters

| Parameter     | Required | Type   | Unique | Description |
|---------------|----------|--------|--------|-------------|
| token         | true     | string | true   | Site ID     |
| customerToken | true     | string | true   | Customer ID |

### URL Parameters

| Parameter | Required | Type   | Unique | Description  |
|-----------|----------|--------|--------|--------------|
| listToken | true     | string | true   | The lists ID |

### Data Parameters

| Parameter        | Required | Type   | Description              |
|------------------|----------|--------|--------------------------|
| listReadableName | true     | string | Title for the list       |
| sortOrder        | true     | int    | Sort Order for this list |

Sample in Shell:

```shell
curl --request PUT \
  --url https://storeapi.csomni.com/customeritemlist/{listToken} \
  --header 'customerToken: cs_xxxxxxxxxxxxxxx', 'site :site_xxxxxxxxxxxx'\
  --data-raw '{
      "listReadableName":"Autumn List - Edited",
      "sortOrder" : 0
}'
```
Response:

```json
{
    "listToken": "custList_xxxxxxxxxxxxxx",
    "sortOrder": 1,
    "listReadableName": "Autumn List - Edited",
    "listItems": [
        {
            "itemToken": "listItem_xxxxxxxxxxxxx",
            "variantToken": "vrnt_xxxxxxxxxxxxxxxx",
            "quantity": 5,
            "sortOrder": 0
        }
    ],
    "totalItemsCount": 5
}
```

## Edit List Item 

### HTTP Request

`PUT https://storeapi.csomni.com/customeritemlist/{custListToken}/{listItem}`

### Header Requirements
| Parameter     | Required | Type   | Unique | Description |
|---------------|----------|--------|--------|-------------|
| token         | true     | string | true   | site ID     |
| customerToken | true     | string | true   | customer ID |


### Data
| Parameter        | Required | Unique | Description                        |
|------------------|----------|--------|------------------------------------|
| sortOrder        | false    | false  | The sort order for the entire list |
| listReadableName | false    | false  | The name of the list               |

Sample in Shell:

```shell
curl --request PUT \
  --url https://storeapi.csomni.com/customeritemlist/{custListToken} \
  --header 'token: site_xxxxxxxxxxx' \
  --header 'customerToken: cs_xxxxxxxxx' \
  --data-raw '{
      "sortOrder" : 1,
      "variantToken": "vrnt_xxxxxxxxxxxxxx",
      "quantity" : 2
  }'
```
Response:

```json
{
  "listToken": "custList_ees8AFYk97OgMSqu",
  "sortOrder": 0,
  "listReadableName": "Autumn List 727",
  "listItems": [
    {
      "itemToken": "listItem_kmutOL7B3eaD",
      "variantToken": "vrnt_KUr95fEklBxa57vb",
      "quantity": 2,
      "sortOrder": 1,
      "variantDetails": {
        "prodToken": "prod_H8ZYrzUz2kRyWWIl",
        "variantToken": "vrnt_KUr95fEklBxa57vb",
        "variantName": "",
        "variantImage": {
          "file": "10-19-2022\/1666195672309__9424__33392.jpg",
          "type": "",
          "id": "h32jwrpf",
          "status": "poolImages"
        },
        "variantImages": [],
        "variantWeight": "0",
        "variantDimW": "0",
        "variantDimL": "0",
        "variantDimH": "0",
        "variantUpc": "",
        "variantNumber": "33392",
        "manufacturerPartNumber": "",
        "variantPrice": 0.12,
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
        "dateCreated": "1666195683",
        "deleted": 0,
        "backOrderWarning": 0,
        "createdAt": "2022-12-18 23:01:04",
        "editedAt": "2024-06-20 09:11:28",
        "variantInStock": true
      }
    },
    {
      "itemToken": "listItem_SoQt5zCOOo1r",
      "variantToken": "vrnt_OYIwevfBUfxErFG3",
      "quantity": 2,
      "sortOrder": 1,
      "variantDetails": {
        "prodToken": "prod_FgNybasFJG4YUJ4h",
        "variantToken": "vrnt_OYIwevfBUfxErFG3",
        "variantName": "31\" WHITE CHINA SINK",
        "variantImage": {
          "file": "10-2-2022\/1664742840284__7264__VE3118W.jpg",
          "type": ""
        },
        "variantImages": [],
        "variantWeight": "0",
        "variantDimW": "0",
        "variantDimL": "0",
        "variantDimH": "0",
        "variantUpc": "",
        "variantNumber": "VE3118W",
        "manufacturerPartNumber": "",
        "variantPrice": 0.25,
        "variantMapPrice": 0,
        "variantMsrpPrice": 0,
        "variantDisplayPrice": 0,
        "variantDescription": "",
        "variantAlert": "",
        "variantLowlevel": "",
        "variantSlug": "31-white-china-sink",
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
        "inventoryCount": 180,
        "shippingProduct": 0,
        "variantMetaTitle": "",
        "variantMetaDescription": "",
        "variantBrand": "",
        "sortOrder": 0,
        "dateCreated": "1661531956",
        "deleted": 0,
        "backOrderWarning": 0,
        "createdAt": "2022-12-18 23:01:04",
        "editedAt": "2024-06-20 08:41:56",
        "variantInStock": true
      }
    }
  ],
  "totalItemsCount": 4
}
```


## Get A specific list

### HTTP Request

`GET https://storeapi.csomni.com/customeritemlist/{custListToken}`

### Header Parameters
| Parameter     | Required | Type   | Unique | Description |
|---------------|----------|--------|--------|-------------|
| token         | true     | string | true   | siteToken   |
| customerToken | true     | string | true   | loginToken  |


Response:

```json
{
  "listToken": "custList_ees8AFYk97OgMSqu",
  "sortOrder": 0,
  "listReadableName": "Autumn List 727",
  "listItems": [
    {
      "itemToken": "listItem_kmutOL7B3eaD",
      "variantToken": "vrnt_KUr95fEklBxa57vb",
      "quantity": 2,
      "sortOrder": 1,
      "variantDetails": {
        "prodToken": "prod_H8ZYrzUz2kRyWWIl",
        "variantToken": "vrnt_KUr95fEklBxa57vb",
        "variantName": "",
        "variantImage": {
          "file": "10-19-2022\/1666195672309__9424__33392.jpg",
          "type": "",
          "id": "h32jwrpf",
          "status": "poolImages"
        },
        "variantImages": [],
        "variantWeight": "0",
        "variantDimW": "0",
        "variantDimL": "0",
        "variantDimH": "0",
        "variantUpc": "",
        "variantNumber": "33392",
        "manufacturerPartNumber": "",
        "variantPrice": 0.12,
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
        "dateCreated": "1666195683",
        "deleted": 0,
        "backOrderWarning": 0,
        "createdAt": "2022-12-18 23:01:04",
        "editedAt": "2024-06-20 09:11:28",
        "variantInStock": true
      }
    },
    {
      "itemToken": "listItem_SoQt5zCOOo1r",
      "variantToken": "vrnt_OYIwevfBUfxErFG3",
      "quantity": 2,
      "sortOrder": 1,
      "variantDetails": {
        "prodToken": "prod_FgNybasFJG4YUJ4h",
        "variantToken": "vrnt_OYIwevfBUfxErFG3",
        "variantName": "31\" WHITE CHINA SINK",
        "variantImage": {
          "file": "10-2-2022\/1664742840284__7264__VE3118W.jpg",
          "type": ""
        },
        "variantImages": [],
        "variantWeight": "0",
        "variantDimW": "0",
        "variantDimL": "0",
        "variantDimH": "0",
        "variantUpc": "",
        "variantNumber": "VE3118W",
        "manufacturerPartNumber": "",
        "variantPrice": 0.25,
        "variantMapPrice": 0,
        "variantMsrpPrice": 0,
        "variantDisplayPrice": 0,
        "variantDescription": "",
        "variantAlert": "",
        "variantLowlevel": "",
        "variantSlug": "31-white-china-sink",
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
        "inventoryCount": 180,
        "shippingProduct": 0,
        "variantMetaTitle": "",
        "variantMetaDescription": "",
        "variantBrand": "",
        "sortOrder": 0,
        "dateCreated": "1661531956",
        "deleted": 0,
        "backOrderWarning": 0,
        "createdAt": "2022-12-18 23:01:04",
        "editedAt": "2024-06-20 08:41:56",
        "variantInStock": true
      }
    }
  ],
  "totalItemsCount": 4
}
```

## Get Lists by customer

### HTTP Request
`GET https://storeapi.csomni.com/customeritemlist/`

### Header Parameters
| Parameter     | Required | Type   | Unique | Description |
|---------------|----------|--------|--------|-------------|
| token         | true     | string | true   | Site ID     |
| customerToken | true     | string | true   | Login ID    |

&nbsp;

Sample in Shell:

```shell
curl --request GET \
  --url https://storeapi.csomni.com/customeritemlist/ \
   --header 'token: site_xxxxxxxxxx', 'customerToken: cs_xxxxxxxxxxxxxxx' 
```

Response:

```json
[
  {
    "listToken": "custList_xqWY7ytHKoAokQbq",
    "sortOrder": 0,
    "listReadableName": "Winter Holiday List",
    "listItems": []
  },
  {
    "listToken": "custList_h7rDA9SJj79G76xk",
    "sortOrder": 0,
    "listReadableName": "Summer Holiday List",
    "listItems": []
  },
  {
    "listToken": "custList_79jrJQX2o91nxAAj",
    "sortOrder": 0,
    "listReadableName": "Winter Holiday List1",
    "listItems": []
  },
  {
    "listToken": "custList_s7kO5X1HgCU7o9qc",
    "sortOrder": 0,
    "listReadableName": "New List",
    "listItems": []
  },
  {
    "listToken": "custList_IXbiidCVgG8L80rK",
    "sortOrder": 0,
    "listReadableName": "",
    "listItems": []
  },
  {
    "listToken": "custList_wG1KKhiOiYFBiciH",
    "sortOrder": 0,
    "listReadableName": "Autumn List",
    "listItems": [
      {
        "itemToken": "listItem_n30YaGtnphNm",
        "variantToken": "vrnt_EvonkJQsR6fRbDtm",
        "quantity": 1,
        "sortOrder": 0
      },
      {
        "itemToken": "listItem_tizrDDXD6zbm",
        "variantToken": "vrnt_EvonkJQsR6fRbDtm",
        "quantity": 1,
        "sortOrder": 0
      },
      {
        "itemToken": "listItem_7lT2rMJ4nEU4",
        "variantToken": "vrnt_OYIwevfBUfxErFG3",
        "quantity": 2,
        "sortOrder": 1
      },
      {
        "itemToken": "listItem_ROnad63u8oeX",
        "variantToken": "vrnt_OYIwevfBUfxErFG3",
        "quantity": 2,
        "sortOrder": 1
      }
    ]
  },
  {
    "listToken": "custList_xxCAxI6seenzz6h4",
    "sortOrder": 0,
    "listReadableName": "Autumn List 160",
    "listItems": []
  },
  {
    "listToken": "custList_r2bv0zhhgXZgI1M1",
    "sortOrder": 0,
    "listReadableName": "Autumn List1",
    "listItems": []
  },
  {
    "listToken": "custList_bWUic9qhWdjieg3M",
    "sortOrder": 0,
    "listReadableName": "Autumn List 876",
    "listItems": []
  },
  {
    "listToken": "custList_ees8AFYk97OgMSqu",
    "sortOrder": 0,
    "listReadableName": "Autumn List 727",
    "listItems": [
      {
        "itemToken": "listItem_kmutOL7B3eaD",
        "variantToken": "vrnt_KUr95fEklBxa57vb",
        "quantity": 2,
        "sortOrder": 1
      },
      {
        "itemToken": "listItem_SoQt5zCOOo1r",
        "variantToken": "vrnt_OYIwevfBUfxErFG3",
        "quantity": 2,
        "sortOrder": 1
      }
    ]
  }
]
```

## Delete a Full List
This endpoint deletes a list in its entirety, including all list items within it

### HTTP Request

`DELETE https://storeapi.csomni.com/customeritemlist/[listToken]`

### Header Parameters
| Parameter     | Required | Type   | Unique | Description |
|---------------|----------|--------|--------|-------------|
| token         | true     | string | true   | Site ID     |
| customerToken | true     | string | true   | Login ID    |

&nbsp;

Sample in Shell:

```shell
curl --request DELETE \
  --url https://storeapi.csomni.com/customeritemlist/{listToken} \
  --header 'token: site_xxxxxxxxxx', 'customerToken: cs_xxxxxxxxxxxxxx'
```

Respose:

```json
{
  "Deleted": true
}
```

## Delete a List Item
This endpoint deletes an item in a list by list and item ID.

### HTTP Request

`DELETE https://storeapi.csomni.com/customeritemlist/{listToken}/{listItemToken}`

### Header Parameters
| Parameter     | Required | Type   | Unique | Description |
|---------------|----------|--------|--------|-------------|
| token         | true     | string | true   | Site ID     |
| customerToken | true     | string | true   | Login ID    |

&nbsp;

Sample in Shell:

```shell
curl --request DELETE \
  --url https://storeapi.csomni.com/customeritemlist/{listToken}/{listItemToken} \
  --header 'token: site_xxxxxxxxx', 'customerToken: cs_1xxxxxxxxxx'
```

Response:

```json
{
  "Deleted": true
}
```
