# Brands

## Get Brands
This endpoint retrieves all brands 

### HTTP Request
`GET https://storeapi.csomni/brands`

### Header Parameters
| Parameter     | Required | Type   | Description      |
|---------------|----------|--------|------------------|
| siteToken     | true     | string | Unique siteToken |

Sample in Shell:

```shell
curl --request GET \
  --url https://storeapi.csomni/brands \
  --header 'token: site_xxxxxxxxxxxx'
```

> The above command returns JSON structured like this:

```json
[
  {
    "brandToken": "brnd_70i7N4YSnlijPyyiTlzN",
    "brandName": "zero",
    "brandImage": "Kiribati",
    "createdAt": "2024-06-04 10:55:13",
    "editedAt": "2024-06-04 10:55:13"
  },
  {
    "brandToken": "brnd_hQczGAFxeJllqFeodca4",
    "brandName": "Green Cert",
    "brandImage": "",
    "createdAt": "2022-11-08 10:14:50",
    "editedAt": "2022-11-08 10:14:50"
  },
  {
    "brandToken": "brnd_LSpy0mTUWXfVEqpmkCHy",
    "brandName": "Zep",
    "brandImage": "6-3-2021\/1622735483066__58533__zep_logo.png",
    "createdAt": "2022-11-08 10:14:50",
    "editedAt": "2022-11-08 10:14:50"
  }
]
```

## Get a Brand by brandToken

This endpoint retrieves a Specific brand.

### HTTP Request

`GET https://storeapi.csomni/brands/{brandToken}`

### Header Parameters
| Parameter     | Required | Type   | Description      |
|---------------|----------|--------|------------------|
| siteToken     | true     | string | Unique siteToken |

Sample in Shell:

```shell
curl --request GET \
  --url https://storeapi.csomni/brands/brnd_70i7N4YSnlijPyyiTlzN \
  --header 'token: site_xxxxxxxxxxxxx'
```

> The above command returns JSON structured like this:

```json
{
  "brandToken": "brnd_70i7N4YSnlijPyyiTlzN",
  "brandName": "zero",
  "brandImage": "Kiribati",
  "createdAt": "2024-06-04 10:55:13",
  "editedAt": "2024-06-04 10:55:13"
}
```
