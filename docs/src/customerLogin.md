# Customer Login



## Login

This endpoint returns logged in user.


### HTTP Request

`POST https://storeapi.csomni.com/login`

### Request Headers (to combine existing cart)
| Parameter     | Required | Type   | Description          |
|---------------|----------|--------|----------------------|
| customerToken | true     | string | Customer Guest Token |
| siteToken     | true     | string | Site Token           |


### Data Parameters
| Parameter        | Required | Description       |
|------------------|----------|-------------------|
| customerEmail    | true     | Customer Email    |
| customerPassword | true     | Customer Password |

```shell
curl --request POST \
  --url https://storeapi.csomni.com/login \
  --header 'token: cs_xxxxxxxxxxxxxx' \
  --data '{
            "customerEmail" : "tesst@gmail.com",
             "customerPassword" : "Abc12345"
          }'
```
> The above command returns JSON structured like this:


```json
{
  "id": 0,
  "customerFirstName": "test",
  "customerLastName": "test",
  "customerEmail": "abcd@gmail.com",
  "customerPhone": "0322487455",
  "customerCompanyName": "abc",
  "dateCreated": "1638353521",
  "customerStatus": "",
  "customerTypes": null,
  "customerGroups": null,
  "isLoggedIn": 1,
  "customerDocs": null,
  "taxExempt": null,
  "taxExemptID": null,
  "createdAt": "2021-12-01 10:12:01",
  "editedAt": "2021-12-01 13:42:53",
  "customerToken": "cs_xxxxxxxxxxxxxxx"
}
```
> If a company setting requires a customer to be approved, until the customer is approved a limited response is provided and login is not initiated

```json
{
    "customerToken": "cs_123456",
    "customerStatus": "cs_awaiting_approval",
    "customerEmail": "123456@evelt.com",
    "customerFirstName": "Sarah"
}
```

## Logout

### HTTP Request

`POST https://storeapi.csomni.com/login/logout`


### Request Headers 
| Parameter     | Required | Type   | Description          |
|---------------|----------|--------|----------------------|
| siteToken     | true     | string | Site Token           |



```shell
curl --location POST 'https://storeapi.csomni.com/login/logout' \
--header 'token: site_xxxxxxxxx' \
--header 'customerToken: cs_xxxxxxxxxxxxxxxxxx'
```

> The above command returns JSON structured like this:

```json
[]
```
