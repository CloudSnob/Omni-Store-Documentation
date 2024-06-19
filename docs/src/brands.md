# Brands

## Get Brands

This endpoint retrieves all brands 

### HTTP Request

`GET https://storeapi.csomni/brands`

### Header Parameters
| Parameter     | Required | Type   | Description      |
|---------------|----------|--------|------------------|
| siteToken     | true     | string | Unique siteToken |

```shell
curl --request GET \
  --url https://storeapi.csomni/brands \
  --header 'token: site_xxxxxxxxxxxx'
```

> The above command returns JSON structured like this:

```json
[
  {
    "companyToken": "comp_xxxxxxxxxxxxx",
    "brandToken": "brnd_xxxxxxxxxxxxx",
    "brandName": "Elph & Rand",
    "brandImage": "",
    "createdAt": "2021-12-16 18:45:21",
    "editedAt": "2021-12-16 18:45:21"
  },
  {
    "companyToken": "comp_xxxxxxxxxxxxx",
    "brandToken": "brnd_xxxxxxxxxxxxx",
    "brandName": "Kite Bulls",
    "brandImage": "",
    "createdAt": "2021-12-16 18:45:21",
    "editedAt": "2021-12-16 18:45:21"
  },
  {
    "companyToken": "comp_xxxxxxxxxxxxx",
    "brandToken": "brnd_xxxxxxxxxxxxx",
    "brandName": "Rock-a-bye",
    "brandImage": "",
    "createdAt": "2021-12-16 18:45:21",
    "editedAt": "2021-12-16 18:45:21"
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

```shell
curl --request GET \
  --url https://storeapi.csomni/brands/{}brandToken} \
  --header 'token: site_xxxxxxxxxxxxx'
```

> The above command returns JSON structured like this:

```json
{
  "brandToken": "brnd_xxxxxxxxxxxxx",
  "brandName": "Rock-a-bye",
  "brandImage": "",
  "createdAt": "2021-12-16 18:45:21",
  "editedAt": "2021-12-16 18:45:21"
}
```
