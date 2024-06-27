# Frequently Purchased

## Get Frequently Purchased List by Site 
This endpoint returns a list of 'frequently purchased' items.
It utilizes cached data for speed. A fresh data pull is triggered if the cached data is <24 hours old.

### HTTP Request
`GET https://storeapi.csomni.com/frequentlyPurchased`

### Header Parameters
| Parameter     | Required | Type   | Unique | Description |
|---------------|----------|--------|--------|-------------|
| token         | true     | string | true   | Site ID     |

Sample in Shell:

```shell
curl --request GET \
  --url https://storeapi.csomni.com/frequentlyPurchased \
  --header 'token: site_xxxxxxxxxxxxxxx'
```

> The above command returns JSON structured like this:

```json
[
  {
    "variantToken": "vrnt_80zIBJ85QSyj7n04",
    "quantity": 6215,
    "price": 0.1,
    "variantImage": {
      "file": "[]"
    },
    "productToken": "prod_MdSn0NBeds35AnsE"
  },
  {
    "variantToken": "prod_QDHDdiPp9cZ5GA1m",
    "quantity": 153,
    "price": "",
    "variantImage": "",
    "productToken": ""
  },
  {
    "variantToken": "prod_dEvvhSBbZGn9o56f",
    "quantity": 132,
    "price": "",
    "variantImage": "",
    "productToken": ""
  },
  {
    "variantToken": "vrnt_qVYmilaeFhycs8Er",
    "quantity": 89,
    "price": "",
    "variantImage": {
      "file": "6-17-2021\/1623962979586__128632__20020.jpg",
      "id": "c1k94yih",
      "status": "poolImages"
    },
    "productToken": "prod_wHgGYzGN5SvvLPAv"
  },
  {
    "variantToken": "prod_zEt7mR9XNTKX0Iu8",
    "quantity": 68,
    "price": "",
    "variantImage": "",
    "productToken": ""
  },
  {
    "variantToken": "vrnt_MenZ7ytfb1oDsU7y",
    "quantity": 64,
    "price": 10.98,
    "variantImage": {
      "file": "9-25-2022\/1664122220667__232775__30086.jpg",
      "type": ""
    },
    "productToken": "prod_qDs0pq1OpSkchNnL"
  },
  {
    "variantToken": "prod_faGeRfhPbNd76IrF",
    "quantity": 51,
    "price": "",
    "variantImage": "",
    "productToken": ""
  },
  {
    "variantToken": "vrnt_wvlV8rix5bonaEuE",
    "quantity": 51,
    "price": 8.64,
    "variantImage": {
      "file": "9-21-2022\/1663803911592__118299__31611.jpg",
      "type": ""
    },
    "productToken": "prod_03FhocJPY5s4DoNT"
  },
  {
    "variantToken": "vrnt_g1euGfX0CQesJS3N",
    "quantity": 43,
    "price": 34.95,
    "variantImage": {
      "file": "5-30-2021\/1622403271812__226354__20000.jpg"
    },
    "productToken": "prod_OVkhZ4t9671VKUw8"
  }
]
```

## Get Frequently Purchased by siteToken FORCE FRESH DATA PULL
This endpoint returns a list of 'frequently purchased' items with a fresh data pull. 

### HTTP Request
`GET https://storeapi.csomni.com/frequentlyPurchased/forceRefresh`

### Header Parameters
| Parameter     | Required | Type   | Unique | Description |
|---------------|----------|--------|--------|-------------|
| token         | true     | string | true   | Site ID     |

Sample in Shell:

```shell
curl --request GET \
  --url https://storeapi.csomni.com/frequentlyPurchased/forceRefresh \
  --header 'token: site_xxxxxxxxxxxxx'
```

> The above command returns JSON structured like this:
```json
[
  {
    "variantToken": "vrnt_80zIBJ85QSyj7n04",
    "quantity": 6215,
    "price": 0.1,
    "variantImage": {
      "file": "[]"
    },
    "productToken": "prod_MdSn0NBeds35AnsE"
  },
  {
    "variantToken": "prod_QDHDdiPp9cZ5GA1m",
    "quantity": 153,
    "price": "",
    "variantImage": "",
    "productToken": ""
  },
  {
    "variantToken": "prod_dEvvhSBbZGn9o56f",
    "quantity": 132,
    "price": "",
    "variantImage": "",
    "productToken": ""
  },
  {
    "variantToken": "vrnt_qVYmilaeFhycs8Er",
    "quantity": 89,
    "price": "",
    "variantImage": {
      "file": "6-17-2021\/1623962979586__128632__20020.jpg",
      "id": "c1k94yih",
      "status": "poolImages"
    },
    "productToken": "prod_wHgGYzGN5SvvLPAv"
  },
  {
    "variantToken": "prod_zEt7mR9XNTKX0Iu8",
    "quantity": 68,
    "price": "",
    "variantImage": "",
    "productToken": ""
  },
  {
    "variantToken": "vrnt_MenZ7ytfb1oDsU7y",
    "quantity": 64,
    "price": 10.98,
    "variantImage": {
      "file": "9-25-2022\/1664122220667__232775__30086.jpg",
      "type": ""
    },
    "productToken": "prod_qDs0pq1OpSkchNnL"
  },
  {
    "variantToken": "prod_faGeRfhPbNd76IrF",
    "quantity": 51,
    "price": "",
    "variantImage": "",
    "productToken": ""
  },
  {
    "variantToken": "vrnt_wvlV8rix5bonaEuE",
    "quantity": 51,
    "price": 8.64,
    "variantImage": {
      "file": "9-21-2022\/1663803911592__118299__31611.jpg",
      "type": ""
    },
    "productToken": "prod_03FhocJPY5s4DoNT"
  },
  {
    "variantToken": "vrnt_g1euGfX0CQesJS3N",
    "quantity": 43,
    "price": 34.95,
    "variantImage": {
      "file": "5-30-2021\/1622403271812__226354__20000.jpg"
    },
    "productToken": "prod_OVkhZ4t9671VKUw8"
  }
]
```

## GET frequently purchased by customer
Follow instructions for GET frequently purchased list, and add an optional customerToken header:

### Optional Header Parameters
| Parameter     | Required | Type   | Unique | Description |
|---------------|----------|--------|--------|-------------|
| customerToken | true     | string | true   | Login ID    |

--header 'customerToken: cs_GWdE9xY2dcL9qqBmNKx7WXivTh73nJtGH4NK'
