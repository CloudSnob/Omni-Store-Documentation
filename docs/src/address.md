# Addresses

## Create New Address
This endpoint creates a new address. If the customerToken parameter is empty, a new customer is created

### HTTP Request

`POST https://storeapi.csomni.com/addresses`

### Header Parameters
| Parameter     | Required | Type   | Description          |
|---------------|----------|--------|----------------------|
| siteToken     | true     | string | Unique API siteToken |

### Data Parameters

| Parameter        | Required            | Unique | Type   | Description                                  |
|------------------|---------------------|--------|--------|----------------------------------------------|
| addressLabel     | false               | false  | string | Address Label (home,work)                    |
| addressFirstName | false               | false  | string | Address First Name (first name of recipient) |
| addressLastName  | false               | false  | string | Address Last Name (last name of recipient)   |
| address          | true                | false  | string | Address Line 1                               |
| address2         | false               | false  | string | Address Line 2                               |
| addressCity      | true                | false  | string | City                                         |
| addressState     | true                | false  | string | State                                        |
| addressZip       | true                | false  | string | Zip Code                                     |
| addressCountry   | false, default = US | false  | string | Country                                      |
| addressDefault   | false               | false  | bool   | Mark as default address                      |
| phoneNumber      | false               | false  | string | Phone Number                                 |
| mobileNumber     | false               | false  | string | Mobile/Cell Number                           |


```shell
curl request POST https://storeapi.csomni.com/addresses \
  --header 'token: site_xxxxxxxxxxxx' \
  --data-raw '{ 
      "address" : "123 Main street",
      "address2": "Unit 4",
      "addressCity" : "NY",
      "addressState" : "NY",
      "addressZip" : "10952",
      "addressLabel" : "Home Address",
      "addressFirstName" : "Jane",
      "addressLastName" : "Foster",
      "phoneNumber" : "03356705565",
      "mobileNumber" : "45678945666"
}'


```

> The above commands both return JSON structured like this

```json
{
  "address": "123 Main street",
  "address2": "Unit 4",
  "addressLabel": "Home Address",
  "addressCity": "NY",
  "addressState": "NY",
  "addressZip": "10952",
  "addressFirstName": "Jane",
  "addressLastName": "Foster",
  "phoneNumber": "03356705565",
  "mobileNumber": "45678945666",
  "customerToken": "cs_xxxxxxxxxxxxxxxx",
  "addressCountry": "United States",
  "addressToken": "adrs_xxxxxxxxxxxxx",
  "specialValues": ""
}
```


## Edit Address
This endpoint edits an existing address

### HTTP Request
`POST https://storeapi.csomni.com/addresses/{addressToken}`


### Header Parameters
| Parameter     | Required | Type   | Description      |
|---------------|----------|--------|------------------|
| customerToken | true     | string | Customer Token   |
| siteToken     | true     | string | Unique siteToken |

### Query Parameters

| Parameter        | Required                                | Unique | Type   | Description                                  |
|------------------|-----------------------------------------|--------|--------|----------------------------------------------|
| customerToken    | true                                    | false  | string | Customer Public Token                        |
| addressLabel     | false                                   | false  | string | Address Label (home,work)                    |
| addressFirstName | false                                   | false  | string | Address First Name (first name of recipient) |
| addressLastName  | false                                   | false  | string | Address Last Name (last name of recipient)   |
| address          | true                                    | false  | string | Address                                      |
| address2         | false                                   | false  | string | Address Line 2                               |
| addressCity      | true                                    | false  | string | City                                         |
| addressState     | true                                    | false  | string | State                                        |
| addressZip       | true                                    | false  | string | Zip Code                                     |
| addressCountry   | true (If empty it enters United States) | false  | string | Country                                      |
| addressDefault   | false                                   | false  | bool   | Mark as default address                      |
| phoneNumber      | false                                   | false  | string | Phone Number                                 |


```shell
curl --request POST \
  --url https://storeapi.csomni.com/addresses/[addressToken] \
  --header 'token: site_xxxxxxxxxxx' \
  --header 'customerToken: [cs_xxxxxxxxxxxxxxxxx"
  --data 
  '{ 
      "addressLabel": "Home Address - Edited",
      "addressFirstName": "Brando",
      "addressLastName": "Grady",
      "address": "19 High Street",
      "address2": "Unit 4",
      "addressCity": "Leifchester",
      "addressState": "NY",
      "addressZip": "10952",
      "addressCountry": "US",
      "addressDefault": "1",
      "phoneNumber": "6338526379",
      "mobileNumber": "3034465487"
  }'

```

> The above command returns JSON structured like this

```json
{
  "addressLabel": "Home Address - Edited",
  "addressFirstName": "Brando",
  "addressLastName": "Grady",
  "address": "19 High Street",
  "address2": "Unit 4",
  "addressCity": "Leifchester",
  "addressState": "NY",
  "addressZip": "10952",
  "addressCountry": "US",
  "addressDefault": "1",
  "phoneNumber": "6338526379",
  "mobileNumber": "3034465487",
  "addressToken": "adrs_xxxxxxxxxxxxxxxx",
  "customerToken": "cs_xxxxxxxxxxxxxxxxxx",
  "specialValues": ""
}
```


## Get Address By Customer
This endpoint returns an array of a customer's addresses

### HTTP Request

`GET https://storeapi.csomni.com/addresses`

### Header Parameters
| Parameter     | Required | Type   | Description      |
|---------------|----------|--------|------------------|
| customerToken | true     | string | Customer Token   |
| siteToken     | true     | string | Unique siteToken |

```shell
curl --request GET \
  --url https://storeapi.csomni.com/addresses \
  --header 'token: site_xxxxxxxxxxxxx' \
  --header 'customerToken: cs_xxxxxxxxxxxxxxxxx'
```

> The above command returns JSON structured like this:

```json
[
  {
    "addressToken": "adrs_xxxxxxxxxxxxx",
    "addressLabel": "Home",
    "address": "10 Highfield Park",
    "address2": "Unit 6",
    "addressCity": "New York",
    "addressState": "NY",
    "addressZip": "54000",
    "addressFirstName": "Joe",
    "addressLastName": "Baldly",
    "phoneNumber": "0313445214",
    "mobileNumber": "",
    "addressCountry": "United States",
    "addressDefault": 0,
    "customerToken": "cs_xxxxxxxxxxxxxxx",
    "specialValues": []
  },
  {
    "addressToken": "adrs_xxxxxxxxxxxxx",
    "addressLabel": "Office ",
    "address": "123 Main street",
    "address2": "Unit 4",
    "addressCity": "Monsey",
    "addressState": "NY",
    "addressZip": "10952",
    "addressFirstName": "John",
    "addressLastName": "Doesky",
    "phoneNumber": "03356705565",
    "mobileNumber": "",
    "addressCountry": "USA",
    "addressDefault": 0,
    "customerToken": "cs_xxxxxxxxxxxxxxx",
    "specialValues": []
  }
]
```


## Get Address by address token

This endpoint retrieves a specific address by searching for 'addressToken'


### Header Parameters
| Parameter     | Required | Type   | Description      |
|---------------|----------|--------|------------------|
| customerToken | true     | string | Customer Token   |
| siteToken     | true     | string | Unique siteToken |

```shell
curl --request GET \
  --url https://storeapi.csomni.com/addresses/{}addressToken} \
  --header 'token: site_xxxxxxxxxx' \
  --header 'customerToken: cs_xxxxxxxxxxxxxxxxxxx'
```

> The above command returns JSON structured like this:

```json
{
  "addressToken": "adrs_xxxxxxxxxxxxxxx",
  "addressLabel": "My Address",
  "address": "123 Main street",
  "address2": "unit 4",
  "addressCity": "Monsey",
  "addressState": "NY",
  "addressZip": "10952",
  "addressFirstName": "My address first",
  "addressLastName": "My Address Last Name",
  "phoneNumber": "03356705565",
  "mobileNumber": "",
  "addressCountry": "USA",
  "addressDefault": 0,
  "customerToken": "cs_xxxxxxxxxxxxxxx",
  "specialValues": []
}
```



## Delete Address

This endpoint deletes (archives) an address

### HTTP Request

`DELETE https://storeapi.csomni.com/addresses/{addressToken}`


### Header Parameters
| Parameter     | Required | Type   | Description      |
|---------------|----------|--------|------------------|
| customerToken | true     | string | Customer Token   |
| siteToken     | true     | string | Unique siteToken |

```shell
curl --request DELETE \
  -- https://storeapi.csomni.com/addresses/{addressToken} \
  --header 'token: site_xxxxxxxxxx'\
  --header 'customerToken:cs_xxxxxxxxxxxxxxxxxx'
```

> The above command returns JSON structured like this:

```json
{
  "token": "adrs_xxxxxxxxxxxxxxx",
  "deleted": "true"
}
```
