# QUOTES

## Create new Quote/Request Shipping Quotes

### HTTP Request

`POST https://storeapi.csomni.com/quotes`

### URL Parameters

| Parameter     | Description                       |
| -----------   | -------------------------------   |
| token         | site Token (header)               |
| customerToken | customer Token (header)           |

```shell

curl --location --request POST 'https://storeapi.csomni.com/quotes' \
--header 'token: site_123' \
--header 'customerToken: cs_123' \
--header 'Content-Type: application/json' \
--data-raw '{
    "quoteItems": [
        {
            "variantToken": "vrnt_80zIBJ85QSyj7n04",
            "quantity": 2
        }
    ],
    "shippingAddress": "adrs_B8IsppsJUvNpdZlpYNkjLk2I",
    "contactDetails": {
        "firstName": "Sharon",
        "lastName": "Doe",
        "email": "chayelle+360Ebba@evelt.com",
        "phoneNumber": "987657489",
        "companyName": "Techo"
    }
}'

```

Response:

```json

{
    "quoteToken": "quote_9Uih2O4wb9Ys",
    "customerToken": "cs_lla3GWnCzC16YfMsPyI06sAoggU2TGHtcnld",
    "companyToken": "comp_################",
    "quoteFiles": "",
    "status": "waiting-response",
    "deleted": 0,
    "dateCreated": "2023-11-08 11:53:11",
    "dateUpdated": "2023-11-08 15:53:11",
    "variantsTotal": 0.2,
    "shippingTotal": 0,
    "taxTotal": 0,
    "itemsCount": 1,
    "itemsQuantity": 2,
    "combinedTotal": null,
    "quoteNumber": 50080,
    "variantDetails": [
        {
            "quote_variantsToken": "quoteVariant_fHQS2ddsw8PU",
            "variantToken": "vrnt_80zIBJ85QSyj7n04",
            "quantity": 2,
            "itemPrice": 0.1,
            "itemTax": 0,
            "lineTotal": 0.2,
            "fullDetails": {
                "prodToken": "prod_MdSn0NBeds35AnsE",
                "variantToken": "vrnt_80zIBJ85QSyj7n04",
                "companyToken": "comp_################",
                "variantName": "Solomon",
                "variantImage": [],
                "variantImages": [],
                "variantWeight": "1",
                "variantDimW": "",
                "variantDimL": "",
                "variantDimH": "",
                "variantUpc": "KZ475588342L48902468",
                "variantNumber": "BE35711026406049",
                "manufacturerPartNumber": "",
                "variantPrice": 0.1,
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
                "google_variantCategory": null,
                "google_variantType": null,
                "google_variantCondition": null,
                "taxable": 1,
                "variantAllowCheckout": 0,
                "variantCheckInvetory": 0,
                "variantTrackInventory": 0,
                "inventoryCount": -91582,
                "shippingProduct": 0,
                "variantMetaTitle": "",
                "variantMetaDescription": "",
                "variantBrand": "",
                "sortOrder": 2,
                "dateCreated": "1675165175",
                "deleted": 0,
                "backOrderWarning": 0,
                "createdAt": "2023-01-31 11:39:35",
                "editedAt": "2023-10-29 19:45:12",
                "variantInStock": true,
                "prodName": "Generic Rubber Hat primary"
            }
        }
    ],
    "shippingAddress": {
        "addressToken": "adrs_B8IsppsJUvNpdZlpYNkjLk2I",
        "addressLabel": "",
        "address": "12354 Main Street",
        "address2": "dont ship",
        "addressCity": "Monsey",
        "addressState": "NY",
        "addressZip": "10952",
        "addressFirstName": "Mika",
        "addressLastName": "Green",
        "phoneNumber": "",
        "mobileNumber": "",
        "addressCountry": "United States",
        "addressDefault": 0,
        "customerToken": "cust_#################",
        "createdAt": "2023-11-08 15:53:02",
        "editedAt": "2023-11-08 15:53:02",
        "specialValues": []
    },
    "contactDetails": {
        "quote_ContactToken": "quoteContact_I1GOLZEOa1kU",
        "firstName": "Sharon",
        "lastName": "Doe",
        "email": "chayelle+360Ebba@evelt.com",
        "phoneNumber": "987657489",
        "companyName": "Techo"
    },
    "shippingQuote": []
}

```


## Get All Quotes by Customer

### HTTP Request

`GET https://storeapi.csomni.com/quotes`

### URL Parameters

| Parameter     | Description                       |
| -----------   | -------------------------------   |
| token         | site Token (header)               |
| customerToken | customer Token (header)           |

```shell

curl --location --request GET 'https://storeapi.csomni.com/quotes/' \
--header 'token: site_123' \
--header 'customerToken: cs_123'

```

Response:

```json
[
    {
        "quoteToken": "quote_bWFkhPpaL56P",
        "customerToken": "cs_123",
        "companyToken": "comp_fxJJZhdcNMf",
        "quoteFiles": "",
        "status": "ordr_vNacvxeTF5pncvvqiXsN1WoE",
        "deleted": 0,
        "dateCreated": "2023-10-28 10:28:09",
        "dateUpdated": "2023-10-29 19:45:15",
        "variantsTotal": 5.5,
        "shippingTotal": 50,
        "taxTotal": 0.5,
        "itemsCount": 1,
        "itemsQuantity": 55,
        "combinedTotal": "56.00",
        "quoteNumber": 50079,
        "variantDetails": [
            {
                "quote_variantsToken": "quoteVariant_7939lK8eS9g2",
                "variantToken": "vrnt_80zIBJ85QSyj7n04",
                "quantity": 55,
                "itemPrice": 0.1,
                "itemTax": 0,
                "lineTotal": 5.5,
                "fullDetails": {
                    "prodToken": "prod_MdSn0NBeds35AnsE",
                    "variantToken": "vrnt_80zIBJ85QSyj7n04",
                    "companyToken": "comp_###################",
                    "variantName": "Solomon",
                    "variantImage": [],
                    "variantImages": [],
                    "variantWeight": "1",
                    "variantDimW": "",
                    "variantDimL": "",
                    "variantDimH": "",
                    "variantUpc": "KZ475588342L48902468",
                    "variantNumber": "BE35711026406049",
                    "manufacturerPartNumber": "",
                    "variantPrice": 0.1,
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
                    "google_variantCategory": null,
                    "google_variantType": null,
                    "google_variantCondition": null,
                    "taxable": 1,
                    "variantAllowCheckout": 0,
                    "variantCheckInvetory": 0,
                    "variantTrackInventory": 0,
                    "inventoryCount": -91582,
                    "shippingProduct": 0,
                    "variantMetaTitle": "",
                    "variantMetaDescription": "",
                    "variantBrand": "",
                    "sortOrder": 2,
                    "dateCreated": "1675165175",
                    "deleted": 0,
                    "backOrderWarning": 0,
                    "createdAt": "2023-01-31 11:39:35",
                    "editedAt": "2023-10-29 19:45:12",
                    "variantInStock": true,
                    "prodName": "Generic Rubber Hat primary"
                }
            }
        ],
        "shippingAddress": {
            "addressToken": "adrs_OaIIoAsl1eJVYIVxAO5n0ETE",
            "addressLabel": "",
            "address": "12354 Main Street",
            "address2": "dont ship",
            "addressCity": "Monsey",
            "addressState": "NY",
            "addressZip": "10952",
            "addressFirstName": "Mika",
            "addressLastName": "Green",
            "phoneNumber": "",
            "mobileNumber": "",
            "addressCountry": "United States",
            "addressDefault": 0,
            "customerToken": "cust_###################",
            "createdAt": "2023-10-28 13:27:55",
            "editedAt": "2023-10-28 13:27:55",
            "specialValues": []
        },
        "contactDetails": {
            "quote_ContactToken": "quoteContact_2u9jIhITwzaZ",
            "firstName": "Sharon",
            "lastName": "Doe",
            "email": "awais+ttt11@evelt.com",
            "phoneNumber": "987657489",
            "companyName": "Techo"
        },
        "shippingQuote": [
            {
                "quote_shippingQuoteToken": "shippingQuoteToken_ILwH778I1HNj",
                "carrier": "TCS",
                "methodName": "TCS",
                "origRate": "",
                "rate": "0.00",
                "deliveryDateTime": "",
                "deliveryDays": "2",
                "description": "",
                "approved": 0,
                "approvedBy": null
            },
            {
                "quote_shippingQuoteToken": "shippingQuoteToken_3yw8DHZYCYvk",
                "carrier": "Fdex",
                "methodName": "Fdex",
                "origRate": "",
                "rate": "50.00",
                "deliveryDateTime": "2023-10-29T12:00:00.000Z",
                "deliveryDays": "1",
                "description": "",
                "approved": 0,
                "approvedBy": null
            }
        ]
    }
]

```

## Get a quote by Quote Token

### HTTP Request

`GET https://storeapi.csomni.com/quotes/[quoteToken]`

### URL Parameters

| Parameter         | Description                       |
| -----------       | -------------------------------   |
| token             | site Token (header)               |
| customerToken     | customer Token (header)           |
| quoteToken(GET)   | Token of the Quote to retrieve.   |

```shell
curl --location --request GET 'https://storeapidev.csomni.com/quotes/quote_bWFkhPpaL56P' \
--header 'token: site_123' \
--header 'customerToken: cs_123'
```

Response:

```json
{
    "quoteToken": "quote_bWFkhPpaL56P",
    "customerToken": "cs_lla3GWnCzC16YfMsPyI06sAoggU2TGHtcnld",
    "companyToken": "comp_fxJJZhdcNMfRF9m",
    "quoteFiles": "",
    "status": "ordr_vNacvxeTF5pncvvqiXsN1WoE",
    "deleted": 0,
    "dateCreated": "2023-10-28 10:28:09",
    "dateUpdated": "2023-10-29 19:45:15",
    "variantsTotal": 5.5,
    "shippingTotal": 50,
    "taxTotal": 0.5,
    "itemsCount": 1,
    "itemsQuantity": 55,
    "combinedTotal": "56.00",
    "quoteNumber": 50079,
    "variantDetails": [
        {
            "quote_variantsToken": "quoteVariant_7939lK8eS9g2",
            "variantToken": "vrnt_80zIBJ85QSyj7n04",
            "quantity": 55,
            "itemPrice": 0.1,
            "itemTax": 0,
            "lineTotal": 5.5,
            "fullDetails": {
                "prodToken": "prod_MdSn0NBeds35AnsE",
                "variantToken": "vrnt_80zIBJ85QSyj7n04",
                "companyToken": "comp_fxJJZhdcNMfRF9m",
                "variantName": "Solomon",
                "variantImage": [],
                "variantImages": [],
                "variantWeight": "1",
                "variantDimW": "",
                "variantDimL": "",
                "variantDimH": "",
                "variantUpc": "KZ475588342L48902468",
                "variantNumber": "BE35711026406049",
                "manufacturerPartNumber": "",
                "variantPrice": 0.1,
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
                "google_variantCategory": null,
                "google_variantType": null,
                "google_variantCondition": null,
                "taxable": 1,
                "variantAllowCheckout": 0,
                "variantCheckInvetory": 0,
                "variantTrackInventory": 0,
                "inventoryCount": -91582,
                "shippingProduct": 0,
                "variantMetaTitle": "",
                "variantMetaDescription": "",
                "variantBrand": "",
                "sortOrder": 2,
                "dateCreated": "1675165175",
                "deleted": 0,
                "backOrderWarning": 0,
                "createdAt": "2023-01-31 11:39:35",
                "editedAt": "2023-10-29 19:45:12",
                "variantInStock": true,
                "prodName": "Generic Rubber Hat primary"
            }
        }
    ],
    "shippingAddress": {
        "addressToken": "adrs_OaIIoAsl1eJVYIVxAO5n0ETE",
        "addressLabel": "",
        "address": "12354 Main Street",
        "address2": "dont ship",
        "addressCity": "Monsey",
        "addressState": "NY",
        "addressZip": "10952",
        "addressFirstName": "Mika",
        "addressLastName": "Green",
        "phoneNumber": "",
        "mobileNumber": "",
        "addressCountry": "United States",
        "addressDefault": 0,
        "customerToken": "cust_###################",
        "createdAt": "2023-10-28 13:27:55",
        "editedAt": "2023-10-28 13:27:55",
        "specialValues": []
    },
    "contactDetails": {
        "quote_ContactToken": "quoteContact_2u9jIhITwzaZ",
        "firstName": "Sharon",
        "lastName": "Doe",
        "email": "awais+ttt11@evelt.com",
        "phoneNumber": "987657489",
        "companyName": "Techo"
    },
    "shippingQuote": [
        {
            "quote_shippingQuoteToken": "shippingQuoteToken_ILwH778I1HNj",
            "carrier": "TCS",
            "methodName": "TCS",
            "origRate": "",
            "rate": "0.00",
            "deliveryDateTime": "",
            "deliveryDays": "2",
            "description": "",
            "approved": 0,
            "approvedBy": null
        },
        {
            "quote_shippingQuoteToken": "shippingQuoteToken_3yw8DHZYCYvk",
            "carrier": "Fdex",
            "methodName": "Fdex",
            "origRate": "",
            "rate": "50.00",
            "deliveryDateTime": "2023-10-29T12:00:00.000Z",
            "deliveryDays": "1",
            "description": "",
            "approved": 0,
            "approvedBy": null
        }
    ]
}

```

## Approve Shipping Quote

### HTTP Request

`POST https://storeapi.csomni.com/quotes/shippingQuoteToken_3yw8DHZYCYvk/approve-shipping`

### URL Parameters

| Parameter                     | Description                                                           |
| --------------------------    | --------------------------------------------------------------------- |
| token                         | site Token (header)                                                   |
| customerToken                 | customer Token (header)                                               |
| quoteToken(GET)               | Token of the Quote to retrieve.                                       |
| shippingQuoteToken (GET)      | Shipping Quote Token as GET Param                                     |
| approved (POST)               | true                                                                  |
| approvedBy (POST)             | Customer Name who is approving quote                                  |

```shell
curl --location --request POST 'https://storeapi.csomni.com/quotes/shippingQuoteToken_3yw8DHZYCYvk/approve-shipping' \
--header 'token: site_123' \
--header 'customerToken: cs_123'
--header 'Content-Type: application/json' \
--data-raw '{
    "approved": true,
    "approvedBy": "[customer-name]"  
}'
```

Response:

```json
{
    "quoteToken": "quote_bWFkhPpaL56P",
    "shipQuoteToken": "shippingQuoteToken_3yw8DHZYCYvk",
    "approved": true
}
```

## Process Quote
### Option 1: Pay Now: Submit new payment card

### HTTP Request

`POST https://storeapi.csomni.com//checkout/payment/{quoteToken}`

```shell
curl --location --request POST 'https://storeapi.csomni.com//checkout/payment/{quoteToken}' \
--header 'token: site_123' \
--header 'customerToken: cs_123'
--data '{
    "nameOnCard": "Jay Kuptez",
    "cardNumbers": "000000000000000000",
    "expMonth": "00",
    "expYear": "00",
    "cvv": "000",
    "billingAddress": "25 Eros Gardens",
    "billingCity": "Airmont",
    "billingState": "NJ",
    "billingZip": "1234567",
    "billingCountry": "United States",
    "billingPhone": "000000",
    "po": "1234"
}'
```

### Option 2: Pay Now: Refference a saved payment card

### HTTP Request

`POST https://storeapi.csomni.com//checkout/payment/{quoteToken}`

```shell
curl --location --request POST 'https://storeapi.csomni.com//checkout/payment/{quoteToken}' \
--header 'token: site_123' \
--header 'customerToken: cs_123'
--data '{
    "cardToken": "cc_#########"
}'
```

### Option 3: Pay Later: Process as PO

### HTTP Request

```shell
curl --location --request POST 'https://storeapi.csomni.com//checkout/po/{quoteToken}' \
--header 'token: site_123' \
--header 'customerToken: cs_123'
--data '{
     "po": "123-P9ojd",
    "billingName": "Lay & Lay Partners",
    "billingAddress": "10 Branding Drive",
    "billingCity": "Airmont",
    "billingState": "NY",
    "billingZip": "10952",
    "billingCountry": "United States",
    "billingPhone": "000000",
    "orderNotePublic": ""
}'
```


Response:

```json
{
    "status": "success",
    "order": {
        "orderProducts": [
            {
                "cartToken": "cart_#################",
                "cartProdToken": "cp_ereMDhbYG4xZH8BGmXrr1EXn",
                "cartProdQuantity": 5,
                "addOnToProdToken": "",
                "addOnProdTokens": null,
                "prodToken": "vrnt_K15iWEvzzrxoDnZZ",
                "deleted": 0,
                "createdAt": "2024-02-26 11:05:37",
                "editedAt": "2024-02-26 11:05:37",
                "companyToken": "comp_#####################",
                "siteToken": "site_###################",
                "customerToken": "cs_X8LvwuKFfxOwnKrVZM7YNuaMwxsJNdLYpv4m",
                "cartCreated": null,
                "cartLastTouched": null,
                "prodStaticCollections": [],
                "specialValues": [],
                "product": {
                    "prodToken": "prod_tBukFGyCun5nBthb",
                    "variantToken": "vrnt_K15iWEvzzrxoDnZZ",
                    "companyToken": "comp_#################",
                    "variantName": "Costa",
                    "variantImage": [],
                    "variantImages": [],
                    "variantWeight": "1",
                    "variantDimW": "",
                    "variantDimL": "",
                    "variantDimH": "",
                    "variantUpc": "",
                    "variantNumber": "XSS v",
                    "manufacturerPartNumber": "",
                    "variantPrice": 0.1,
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
                    "google_variantCategory": null,
                    "google_variantType": null,
                    "google_variantCondition": null,
                    "taxable": 1,
                    "variantAllowCheckout": 0,
                    "variantCheckInvetory": 0,
                    "variantTrackInventory": 0,
                    "inventoryCount": 84,
                    "shippingProduct": 0,
                    "variantMetaTitle": "",
                    "variantMetaDescription": "",
                    "variantBrand": "",
                    "sortOrder": 2,
                    "dateCreated": "1708595142",
                    "deleted": 0,
                    "backOrderWarning": 0,
                    "createdAt": "2024-02-22 09:45:42",
                    "editedAt": "2024-02-26 10:44:23",
                    "variantInStock": true,
                    "prodName": "Licensed Granite KeyboardBall",
                    "prodImage": {
                        "file": ""
                    }
                },
                "addOnProducts": [],
                "pricing": {
                    "total": 0.5
                },
                "shipping": {
                    "totalWeight": 5
                }
            }
        ],
        "orderEmail": "saraph@los.com",
        "orderShippingMethod": {
            "quoteToken": "quote_##########",
            "carrier": "UPS",
            "methodName": "Next Day Air",
            "origRate": null,
            "rate": "0.01",
            "deliveryDateTime": null,
            "deliveryDays": "1",
            "description": null,
            "approved": 1,
            "approvedBy": "Kim Casper",
            "id": "shippingQuoteToken_nkZNemaRZbie"
        },
        "orderTotal": 0.56,
        "orderTax": 0.05,
        "orderTotalPaid": "0.56",
        "orderShipping": "0.01",
        "orderWeight": 5,
        "orderShippingAddress": "{\"address\":\"10 high\",\"address2\":\"Unit 6\",\"city\":\"Port Jorge\",\"state\":\"NY\",\"zip\":\"10952\",\"country\":\"United States\",\"phone\":\"797-550-6639\",\"mobile\":\"\",\"specialValues\":[]}",
        "orderPaymentMethod": {
            "xResult": "A",
            "xStatus": "Approved",
            "xError": "",
            "xErrorCode": "00000",
            "xRefNum": "##########",
            "xExp": "0126",
            "xAuthCode": "#######",
            "xBatch": "########",
            "xAvsResultCode": "NNN",
            "xAvsResult": "Address: No Match & 5 Digit Zip: No Match",
            "xCvvResultCode": "",
            "xCvvResult": "No CVV data available",
            "xAuthAmount": "0.56",
            "xMaskedCardNumber": "#xxxxxxxxxxx####",
            "xCardType": "Visa",
            "xName": "Jay Klark",
            "xToken": "################################",
            "xMID": "xxxxxxxxxx9999",
            "xTID": "xxxxx6789",
            "xCurrency": "USD",
            "xDate": "2/26/2024 6:05:43 AM",
            "xEntryMethod": "Keyed",
            "cardToken": "cc_#########"
        },
        "contactLastName": "Doe",
        "contactFirstName": "Sharon",
        "orderProdQuantity": 5,
        "paymentObject": "{\"xResult\":\"A\",\"xStatus\":\"Approved\",\"xError\":\"\",\"xErrorCode\":\"00000\",\"xRefNum\":\"10146212864\",\"xExp\":\"0126\",\"xAuthCode\":\"46613A\",\"xBatch\":\"5150840\",\"xAvsResultCode\":\"NNN\",\"xAvsResult\":\"Address: No Match & 5 Digit Zip: No Match\",\"xCvvResultCode\":\"\",\"xCvvResult\":\"No CVV data available\",\"xAuthAmount\":\"0.56\",\"xMaskedCardNumber\":\"#xxxxxxxxxxx####\",\"xCardType\":\"Visa\",\"xName\":\"Jay Klark\",\"xToken\":\"814147871n898568hm1q2g89857gm\",\"xMID\":\"xxxxxxxxxx9979\",\"xTID\":\"xxxxx6799\",\"xCurrency\":\"USD\",\"xDate\":\"2\\/26\\/2024 6:05:43 AM\",\"xEntryMethod\":\"Keyed\",\"cardToken\":\"cc_#######\"}",
        "cardToken": "cc_2NIigpQQnrpX",
        "orderIP": "81.151.212.137",
        "cartToken": "cart_###################",
        "PO": "1234",
        "BillToName": "Jay Klark",
        "BillToAddress": "{\"name\":\"Jay Klein\",\"address\":\"10 Eros Drive\",\"address2\":\"\",\"zip\":\"10952\",\"city\":\"Airmont\",\"state\":\"NY\",\"country\":\"United States\",\"mobile\":\"\",\"phone\":\"000000\"}",
        "orderNotePublic": "this is a public note I wrote and submited through payment checkout api call",
        "quoteToken": "quote_##########",
        "siteToken": "site_###############",
        "companyToken": "comp_#############",
        "customerToken": "cust_#################",
        "orderToken": "ordr_###############",
        "orderNumber": 10005360,
        "orderStatus": "os_awaiting_fulfillment",
        "checkoutObject": "{\"id\":32484,\"cartToken\":\"cart_cQyaclM8aCNwyefF7SW0OPhd\",\"customerToken\":\"cs_X8LvwuKFfxOwnKrVZM7YNuaMwxsJNdLYpv4m\",\"couponCodes\":null,\"addressToken\":\"adrs_0RTQlF3mGAUYPkwxCb7D8ucV\",\"shippingMethod\":{\"quoteToken\":\"quote_ce8VcOopzQBt\",\"carrier\":\"UPS\",\"methodName\":\"Next Day Air\",\"origRate\":null,\"rate\":\"0.01\",\"deliveryDateTime\":null,\"deliveryDays\":\"1\",\"description\":null,\"approved\":1,\"approvedBy\":\"Kim Casper\",\"id\":\"shippingQuoteToken_nkZNemaRZbie\"},\"shippingMethodId\":\"shippingQuoteToken_nkZNemaRZbie\",\"shippingAddressLabel\":null,\"shippingAddress\":{\"address\":\"10 high\",\"address2\":\"dont ship\",\"city\":\"Port Jorge\",\"state\":\"NY\",\"zip\":\"10952\",\"country\":\"United States\",\"phone\":\"797-530-6639\",\"mobile\":\"\",\"specialValues\":[]},\"contactEmail\":\"chayelle+quoteDetails@evelt.com\",\"contactPhone\":\"987657489\",\"shippingMethodsJson\":[{\"quoteToken\":\"quote_ce8VcOopzQBt\",\"carrier\":\"UPS\",\"methodName\":\"Next Day Air\",\"origRate\":null,\"rate\":\"0.01\",\"deliveryDateTime\":null,\"deliveryDays\":\"1\",\"description\":null,\"approved\":1,\"approvedBy\":\"Kim Casper\",\"id\":\"shippingQuoteToken_nkZNemaRZbie\"},{\"quoteToken\":\"quote_ce8VcOopzQBt\",\"carrier\":\"Fedex\",\"methodName\":\"Ground Express\",\"origRate\":null,\"rate\":\"0.02\",\"deliveryDateTime\":null,\"deliveryDays\":\"2\",\"description\":null,\"approved\":0,\"approvedBy\":null,\"id\":\"shippingQuoteToken_pXx6JcI6Kw5t\"}],\"contactFirstName\":\"Sharon\",\"contactLastName\":\"Doe\",\"companyName\":\"Techo\",\"createdAt\":\"2024-02-26 11:05:38\",\"editedAt\":\"2024-02-26 11:05:38\",\"pricing\":{\"productsTotal\":0.5,\"origTotal\":0.5,\"subTotal\":0.5,\"shipping\":\"0.01\",\"tax\":0.05,\"totalCouponDiscount\":0,\"totalAfterCoupon\":0.56,\"total\":0.56},\"couponCodesInfo\":[]}",
        "customerObject": "{\"customerFirstName\":\"Clare\",\"customerLastName\":\"West\",\"customerEmail\":\"weat@los.com\",\"customerPhone\":\"\",\"customerCompanyName\":\"Beahan, Herman and Ferry\",\"customerStatus\":\"cs_approved\",\"customerTypes\":null,\"customerGroups\":null,\"isLoggedIn\":1,\"customerDocs\":\"\",\"taxExempt\":0,\"taxExemptID\":null,\"createdAt\":\"2024-02-26 10:41:52\"}",
        "dateCreated": 1708945545,
        "statusTermsData": {
            "processingStatus": "Processing",
            "shippingStatus": "Pending",
            "paymentStatus": "Closed",
            "orderStatus": "Open",
            "paymentTerms": "Website Payment",
            "postPaymentStatus": "NULL"
        }
    }
}
```




## Delete a Specific quote

### HTTP Request

`DELETE https://storeapi.csomni.com/quotes/{quoteToken}`

```shell
curl --location --request DELETE 'https://storeapi.csomni.com/quotes/quote_##########' \
--header 'token: site_#########' \
--header 'customerToken: cs_#################'
```

Response:

```json
{
  "token": "quote_##########",
  "deleted": "true"
}
```
