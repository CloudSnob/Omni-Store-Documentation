# Sites

## GET site info
This endpoint returns the sites details - for example name and address

### HTTP Request
`GET https://storeapi.csomni.com/sites`


### Header Parameters
| Parameter     | Type   | Description       |
|---------------|--------|-------------------|
| token         | string | Site Token ID     |

Sample in Shell:

```shell
curl --request GET \
  --url https://storeapi.csomni.com/sites/ \
  --header 'token: site_xxxxxxxxxx'
```

> The above command returns JSON structured like this:

```json
{
    "siteToken": "site_xxxxxxxxxxxxx",
    "siteName": "Bakery Best",
    "address1": "7 Sedgewick Place",
    "address2": "Apt. 4",
    "city": "Brooklyn",
    "state": "NY",
    "zipCode": "11206",
    "country": "US",
    "logo": "https://bakery-best.com/img/####.png",
    "phoneNumber": "1234568901"
}
```
