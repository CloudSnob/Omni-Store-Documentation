# Customers


## Create Customer
This endpoint creates a customer

### HTTP Request

`POST https://storeapi.csomni.com/customers`

### Header Parameters
| Parameter     | Required | Type   | Description       |
|---------------|----------|--------|-------------------|
| siteToken     | true     | string | Unique siteToken  |

### Data Parameters

| Parameter           | Required | Type   | Unique | Description           |
|---------------------|----------|--------|--------|-----------------------|
| customerEmail       | true     | string | true   | Customer Email        |
| customerFirstName   | true     | string | false  | Customer First Name   |
| customerLastName    | true     | string | false  | Customer Last Name    |
| customerPhone       | false    | string | false  | Customer Phone Number |
| customerPassword    | true     | string | false  | Customer Password     |
| customerCompanyName | false    | string | false  | Company Name          |

Sample in Shell:

```shell
curl --request POST \
  --url https://storeapi.csomni.com/customers \
  --header 'token: site_xxxxxxxxx' \
  --data '{ 
            "customerFirstName" : "Sarah", 
            "customerLastName" : "Jones", 
            "customerEmail" : "sjones@gmail.com", 
            "customerPassword" : "123456Aa" 
          }'

```

> The above command returns JSON structured like this

```json
{
  "id": 51150,
  "customerFirstName": "Sarah",
  "customerLastName": "Jones",
  "customerEmail": "sjones@gmail.com",
  "customerPhone": "",
  "customerCompanyName": "",
  "dateCreated": "1639760040",
  "customerStatus": "",
  "customerTypes": null,
  "customerGroups": null,
  "isLoggedIn": 1,
  "customerDocs": null,
  "taxExempt": null,
  "taxExemptID": null,
  "createdAt": "2021-12-17 16:54:00",
  "editedAt": "2021-12-17 16:54:00",
  "customerToken": "cs_3C04TQd6OSkDNFa90UyYAUaD1Lq8NcQbHjQi"
}
```

## Edit Customer
This endpoint edits a customer

### HTTP Request
`POST https://storeapi.csomni.com/customers`

### Header Parameters
| Parameter     | Required | Type   | Description          |
|---------------|----------|--------|----------------------|
| siteToken     | true     | string | Unique siteToken     |
| customerToken | true     | string | Unique customerToken |


### Data Parameters
| Parameter           | Required | Type   | Unique | Description           |
|---------------------|----------|--------|--------|-----------------------|
| customerEmail       | true     | string | true   | Customer Email        |
| customerFirstName   | true     | string | false  | Customer First Name   |
| customerLastName    | true     | string | false  | Customer Last Name    |
| customerPhone       | false    | string | false  | Customer Phone Number |
| customerPassword    | true     | string | false  | Customer Password     |
| customerCompanyName | false    | string | false  | Company Name          |

Sample in Shell:

```shell
curl --request POST \
  --url https://storeapi.csomni.com/customers \
  --header 'token: site_xxxxxxxxx' \
  --header 'token: cs_3C04TQd6OSkDNFa90UyYAUaD1Lq8NcQbHjQi' \
  --data '{ 
            "customerFirstName" : "Sarah", 
            "customerLastName" : "Jones", 
            "customerEmail" : "sjones@gmail.com", 
            "customerPassword" : "123456Aa" 
          }'

```

> The above command returns JSON structured like this
```json
{
  "customerPhone": "1234567890123",
  "isLoggedIn": true,
  "customerToken": "cs_3C04TQd6OSkDNFa90UyYAUaD1Lq8NcQbHjQi"
}
```

## Get A Specific Customer
This endpoint retrieves a specific customer

### HTTP Request

`GET https://storeapi.csomni.com/customers/{{customerToken}}`

### URL Parameters
| Parameter     | Required | Type   | Description           |
|---------------|----------|--------|-----------------------|
| customerToken | true     | string | Unique customer token |

### Header Parameters
| Parameter     | Required | Type   | Description           |
|---------------|----------|--------|-----------------------|
| siteToken     | true     | string | Unique site token     |
| customerToken | true     | string | Unique customer token |

Sample in Shell:

```shell
curl --request GET \
  --url https://storeapi.csomni.com/customers/ \
  --header 'token: site_xxxxxxxxxxx' \
  --header 'customerToken: cs_3C04TQd6OSkDNFa90UyYAUaD1Lq8NcQbHjQi'
```

> The above command returns JSON structured like this:

```json
{
  "id": 51150,
  "customerFirstName": "Sarah",
  "customerLastName": "Jones",
  "customerEmail": "sjones@gmail.com",
  "customerPhone": "",
  "customerCompanyName": "",
  "dateCreated": "1639760040",
  "customerStatus": "",
  "customerTypes": null,
  "customerGroups": null,
  "isLoggedIn": 1,
  "customerDocs": null,
  "taxExempt": null,
  "taxExemptID": null,
  "createdAt": "2021-12-17 16:54:00",
  "editedAt": "2021-12-17 16:57:31"
}
```


## Archive customer
This endpoint soft deletes a customer. The customer data remains accessible through admin under 'archived'

### Header Parameters
| Parameter     | Required | Type   | Description           |
|---------------|----------|--------|-----------------------|
| siteToken     | true     | string | Unique site token     |
| customerToken | true     | string | Unique customer token |


Sample in Shell:

```shell
curl --request DELETE \
  --url https://storeapi.csomni.com/customers/{customerToken}\
  --header 'token: site_xxxxxxxxxx' \
  --header 'customerToken: cs_3C04TQd6OSkDNFa90UyYAUaD1Lq8NcQbHjQi'
```

> The above command returns JSON structured like this:

```json
{
  "token": "cs_3C04TQd6OSkDNFa90UyYAUaD1Lq8NcQbHjQi",
  "deleted": "true"
}
```