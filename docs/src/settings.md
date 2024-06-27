# Settings


## Get settings 
This endpoint retrieves the sites settings

### HTTP Request
`GET https://storeapi.csomni.com/settings`

### Header Parameters
| Parameter     | Type   | Description       |
|---------------|--------|-------------------|
| token         | string | Site Token ID     |

Sample in Shell:

```shell
curl --request GET \
  --url https://storeapi.csomni.com/settings \
  --header 'token: site_xxxxxxxxxx'
```

> The above command returns JSON structured like this:

```json
{
    "settings": [
        {
            "settingCategory": "SITE",
            "settingType": "baseUrl",
            "setting": "https://opticsforce.com"
        },
        {
            "settingCategory": "SITE",
            "settingType": "collectionUrl",
            "setting": "[BASE_URL]/collections/[COLLECTION_SLUG]"
        },
        {
            "settingCategory": "SITE",
            "settingType": "productUrl",
            "setting": "[BASE_URL]/products/[PRODUCT_SLUG]"
        },
        {
            "settingCategory": "SITE",
            "settingType": "variantUrl",
            "setting": "[BASE_URL]/products/[PRODUCT_SLUG]?variant=[VARIANT_TOKEN]"
        },
        {
            "settingCategory": "COMPANY",
            "settingType": "fs1GetToken",
            "setting": "123456"
        },
        {
            "settingCategory": "SITE",
            "settingType": "cartQuantityCombine",
            "setting": "1"
        },
        {
            "settingCategory": "SITE",
            "settingType": "googleSheetId",
            "setting": "1Jl81_123456"
        }
    ],
    "settingssite": {
        "settingToken": "stngSite_123456",
        "siteToken": "site_xxxxxxxxxxxxxxx",
        "baseUrl": "https://website.com",
        "cartQuantityCombine": 1,
        "collectionUrl": "",
        "googleSheetId": "",
        "productUrl": "",
        "sendOrderEmail": 1,
        "sendWelcomeEmail": 0,
        "signupStatus": null,
        "smtpEmail": "",
        "smtpHost": "",
        "smtpPassword": "",
        "taxByState": 0,
        "taxOutOfState": "1",
        "taxRate": 8.75,
        "variantUrl": "",
        "deleted": 0,
        "dateCreated": "0000-00-00 00:00:00",
        "dateUpdated": "2022-11-20 22:08:55",
        "deleteSessionsRuleInDays": 40,
        "sendPendingAccountEmail": 0,
        "quotesEnabled": 1
    }
}
```
