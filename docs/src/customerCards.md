# Customer Cards

## Get Cards by Customer
GET https://storeapi.csomni.com/paymentmanager/cards

### Header Parameters
| Parameter     | Required | Type   | Description      |
|---------------|----------|--------|------------------|
| customerToken | true     | string | Customer Token   |
| siteToken     | true     | string | Unique siteToken |


```shell
curl --location 'https://storeapi.csomni.com/paymentmanager/cards' \
--header 'customerToken: cs_xxxxxxxxxxxxxxxxxx' \
--header 'token: site_xxxxxxxxxx'
```

> The above command returns JSON structured like this

```json
[
    {
        "cardToken": "cc_xxxxxxxxxxx",
        "cardTokenStripe": "",
        "lastFour": "xxxx",
        "expMonth": "xx",
        "expYear": "xx",
        "cvv": "xxx",
        "nameOnCard": "Sarah Jones",
        "billingAddress": "117 Apple Tree Ave",
        "billingAddress2": "",
        "billingCity": "Bala Cynwyd",
        "billingState": "Pennsylvania",
        "billingZip": "19004",
        "billingPhone": "1234567890",
        "billingMobile": "",
        "billingCountry": "United States",
        "zipMatched": null,
        "avsMatched": null,
        "companyToken": "",
        "customerToken": "cs_xxxxxxxxxxxxxxxxxxxxxx",
        "isDefault": 0,
        "createdAt": "2024-05-20 11:05:59",
        "editedAt": "2024-05-20 11:05:59"
    },
    {
        "cardToken": "cc_xxxxxxxxxxx",
        "cardTokenStripe": "",
        "lastFour": "xxxx",
        "expMonth": "xx",
        "expYear": "xx",
        "cvv": "xxx",
        "nameOnCard": "Sarah Jones",
        "billingAddress": "123 Main street",
        "billingAddress2": "Unit 4",
        "billingCity": "NY",
        "billingState": "NY",
        "billingZip": "10952",
        "billingPhone": "718758798",
        "billingMobile": "",
        "billingCountry": "",
        "zipMatched": 0,
        "avsMatched": 0,
        "companyToken": "",
        "customerToken": "cs_xxxxxxxxxxxxxxxxxxxxxxx",
        "isDefault": 0,
        "createdAt": "2024-06-18 12:31:11",
        "editedAt": "2024-06-18 12:31:11"
    }
]
```

## Get Card by Card token
GET https://storeapi.csomni.com/paymentmanager/cards/{cardToken}

### Header Parameters
| Parameter     | Required | Type   | Description      |
|---------------|----------|--------|------------------|
| customerToken | true     | string | Customer Token   |
| siteToken     | true     | string | Unique siteToken |


```shell
curl --location 'https://storeapi.csomni.com/paymentmanager/cards/{cardToken}' \
--header 'customerToken: cs_xxxxxxxxxxxxxxxxxx' \
--header 'token: site_xxxxxxxxxx'
```

> The above command returns JSON structured like this

```json
{
  "cardToken": "cc_xxxxxxxxxxx",
  "cardTokenStripe": "",
  "lastFour": "xxxx",
  "expMonth": "xx",
  "expYear": "xx",
  "cvv": "xxx",
  "nameOnCard": "Sarah Jones",
  "billingAddress": "117 Apple Tree Ave",
  "billingAddress2": "",
  "billingCity": "Bala Cynwyd",
  "billingState": "Pennsylvania",
  "billingZip": "19004",
  "billingPhone": "1234567890",
  "billingMobile": "",
  "billingCountry": "United States",
  "zipMatched": null,
  "avsMatched": null,
  "companyToken": "",
  "customerToken": "cs_xxxxxxxxxxxxxxxxxxxxxx",
  "isDefault": 0,
  "createdAt": "2024-05-20 11:05:59",
  "editedAt": "2024-05-20 11:05:59"
}
```

## Add new Payment Card

### HTTP Request

`POST https://storeapi.csomni.com/paymentmanager`

### Query Parameters

| Parameter       | Required | Unique | Description                                                          |
|-----------------|----------|--------|----------------------------------------------------------------------|
| cardNumbers     | true     | false  | Numbers on Card                                                      |
| cvv             | true     | false  | 3 Digit Security numbers                                             |
| nameOnCard      | true     | false  | Cardholder name                                                      |
| billingAddress  | true     | false  | Billing Address                                                      |
| billingAddress2 | false    | false  | Billing Address Line 2                                               |
| billingZip      | true     | false  | Billing Zip                                                          |
| billingCity     | true     | false  | Biling City                                                          |
| billingState    | true     | false  | Billing State                                                        |
| billingCountry  | true     | false  | Billing country                                                      |
| billingPhone    | true     | false  | Billing Phone                                                        |
| billingMobile   | true     | false  | Billing Mobile                                                       |
| isDefault       | true     | false  | Specify if this card should be the default card used on this account |
| expMonth        | true     | false  | Card expiry Month                                                    |
| expYear         | true     | false  | Card expiry Year                                                     |


```shell
curl --location POST 'https://storeapi.csomni.com/paymentmanager/addcard' \
--header 'customerToken: cs_xxxxxxxxxxxxxxxx' \
--header 'token: site_xxxxxxxxx' \
--data '{
    "cardNumbers": "11111111111111111",
    "cvv": "1234",
    "nameOnCard": "Sarah Jones",
    "billingAddress": "20 Maple Ave",
    "billingAddress2": "",
    "billingZip": "123456",
    "billingCity": "Bala Cynwyd",
    "billingState": "Pennsylvania",
    "billingCountry": "United States",
    "billingPhone": "1234567890",
    "billingMobile": "",
    "isDefault": true,
    "expMonth": "01",
    "expYear": "11"
}'
```

> The above command returns JSON structured like this

```json
{
    "cardToken": "cc_xxxxxxxxx",
    "cardTokenStripe": "",
    "numbers": "11111111111111111",
    "lastFour": "6789",
    "expMonth": "01",
    "expYear": "11",
    "cvv": "1234",
    "nameOnCard": "Sarah Jones",
    "billingAddress": "20 Maple Ave",
    "billingAddress2": "",
    "billingCity": "Bala Cynwyd",
    "billingState": "Pennsylvania",
    "billingZip": "123456",
    "billingPhone": "1234567890",
    "billingMobile": "",
    "billingCountry": "United States",
    "zipMatched": null,
    "avsMatched": null,
    "companyToken": "cs_xxxxxxxxxxxxxxxxxxxxxx",
    "customerToken": "",
    "isDefault": 1,
    "archived": 0,
    "createdAt": "2023-04-20 21:17:19",
    "editedAt": "2023-04-20 22:31:19"
}
```


## Edit Card

### HTTP Request

`PUT https://storeapi.csomni.com/paymentmanager/{{cardToken}}`

### Query Parameters

| Parameter       | Required | Unique | Description                                                          |
|-----------------|----------|--------|----------------------------------------------------------------------|
| cardNumbers     | true     | false  | Numbers on Card                                                      |
| cvv             | true     | false  | 3 Digit Security numbers                                             |
| nameOnCard      | true     | false  | Cardholder name                                                      |
| billingAddress  | true     | false  | Billing Address                                                      |
| billingAddress2 | false    | false  | Billing Address Line 2                                               |
| billingZip      | true     | false  | Billing Zip                                                          |
| billingCity     | true     | false  | Biling City                                                          |
| billingState    | true     | false  | Billing State                                                        |
| billingCountry  | true     | false  | Billing country                                                      |
| billingPhone    | true     | false  | Billing Phone                                                        |
| billingMobile   | true     | false  | Billing Mobile                                                       |
| isDefault       | true     | false  | Specify if this card should be the default card used on this account |
| expMonth        | true     | false  | Card expiry Month                                                    |
| expYear         | true     | false  | Card expiry Year                                                     |


```shell
curl --location PUT 'https://storeapi.csomni.com/paymentmanager/{{cardToken}}' \
--header 'customerToken: cs_xxxxxxxxxxxxxxxx' \
--header 'token: site_xxxxxxxxx' \
--data '{
    "cardNumbers": "11111111111111111",
    "cvv": "1234",
    "nameOnCard": "Sarah Jones",
    "billingAddress": "20 Maple Ave",
    "billingAddress2": "",
    "billingZip": "123456",
    "billingCity": "Bala Cynwyd",
    "billingState": "Pennsylvania",
    "billingCountry": "United States",
    "billingPhone": "1234567890",
    "billingMobile": "",
    "isDefault": true,
    "expMonth": "01",
    "expYear": "11"
}'
```

> The above command returns JSON structured like this

```json
{
    "cardToken": "cc_xxxxxxxxx",
    "cardTokenStripe": "",
    "numbers": "11111111111111111",
    "lastFour": "6789",
    "expMonth": "01",
    "expYear": "11",
    "cvv": "1234",
    "nameOnCard": "Sarah Jones",
    "billingAddress": "20 Maple Ave",
    "billingAddress2": "",
    "billingCity": "Bala Cynwyd",
    "billingState": "Pennsylvania",
    "billingZip": "123456",
    "billingPhone": "1234567890",
    "billingMobile": "",
    "billingCountry": "United States",
    "zipMatched": null,
    "avsMatched": null,
    "companyToken": "",
    "customerToken": "",
    "isDefault": 1,
    "archived": 0,
    "createdAt": "2023-04-20 21:17:19",
    "editedAt": "2023-04-20 22:31:19"
}
```

