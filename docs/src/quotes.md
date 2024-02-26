# QUOTES

## Create new Quote/Request Shipping Quotes

### HTTP Request

`POST https://adminapi.csomni.com/quotes`

### URL Parameters

| Parameter     | Description                       |
| -----------   | -------------------------------   |
| token         | site Token (header)               |
| customerToken | customer Token (header)           |

```shell

curl --location --request POST 'https://adminapidev.csomni.com/quotes' \
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
    "companyToken": "comp_fxJJZhdcNMfRF9m",
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
        "customerToken": "cust_l513Z8XmSeXRy94tzGaQWfLQ",
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

`GET https://adminapidev.csomni.com/quotes`

### URL Parameters

| Parameter     | Description                       |
| -----------   | -------------------------------   |
| token         | site Token (header)               |
| customerToken | customer Token (header)           |

```shell

curl --location --request GET 'https://adminapi.csomni.com/quotes/' \
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
            "customerToken": "cust_l513Z8XmSeXRy94tzGaQWfLQ",
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

`GET https://adminapi.csomni.com/quotes/[quoteToken]`

### URL Parameters

| Parameter         | Description                       |
| -----------       | -------------------------------   |
| token             | site Token (header)               |
| customerToken     | customer Token (header)           |
| quoteToken(GET)   | Token of the Quote to retrieve.   |

```shell
curl --location --request GET 'https://adminapidev.csomni.com/quotes/quote_bWFkhPpaL56P' \
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
        "customerToken": "cust_l513Z8XmSeXRy94tzGaQWfLQ",
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

`POST https://adminapi.csomni.com/quotes/shippingQuoteToken_123/approve-shipping`

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
curl --location --request POST 'http://azzyomnifrontendapi.com//quotes/shippingQuoteToken_3yw8DHZYCYvk/approve-shipping' \
--header 'token: site_123' \
--header 'customerToken: cs_123'
--header 'Content-Type: application/json' \
--data-raw '{
    "approved": true,
    "approvedBy": "{{customerName}}"  
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

## Quote Checkout | Step 1 - Checkout Review

### HTTP Request

`POST https://adminapi.csomni.com/checkout/review-checkout/quote_bWFkhPpaL56P`

### URL Parameters

| Parameter                     | Description                                                           |
| -------------------------     | --------------------------------------------------------------------- |
| token                         | site Token (header)                                                   |
| customerToken                 | customer Token (header)                                               |
| quoteToken(GET)               | Token of the Quote to retrieve.                                       |
| addressToken (POST)           | address token                                                         |
| shippingMethodId (POST)       | shiping Quote Token                                                   |

```shell
curl --location --request POST 'https://adminapi.csomni.com/checkout/review-checkout/quote_bWFkhPpaL56P' \
--header 'token: site_123' \
--header 'customerToken: cs_123' \
--header 'Content-Type: application/json' \
--data-raw '{
    "addressToken": "adrs_OaIIoAsl1eJVYIVxAO5n0ETE",
    "quoteToken": "quote_bWFkhPpaL56P",
    "shippingMethodId" : "shippingQuoteToken_3yw8DHZYCYvk"
}
```

Response: 

```json
{
    "id": 30921,
    "cartToken": "quoteCart_9oIkF6fedNUOH6K8MBgHhmCV",
    "customerToken": "cs_lla3GWnCzC16YfMsPyI06sAoggU2TGHtcnld",
    "couponCodes": null,
    "addressToken": "",
    "shippingMethod": "{\"id\":\"shippingQuoteToken_ILwH778I1HNj\",\"quote_shippingQuoteToken\":\"shippingQuoteToken_ILwH778I1HNj\",\"quoteToken\":\"quote_bWFkhPpaL56P\",\"carrier\":\"TCS\",\"methodName\":\"TCS\",\"origRate\":\"\",\"rate\":\"0.00\",\"deliveryDateTime\":\"\",\"deliveryDays\":\"2\",\"description\":\"\",\"approved\":1,\"approvedBy\":null}",
    "shippingMethodId": "shippingQuoteToken_3yw8DHZYCYvk",
    "shippingAddressLabel": "",
    "shippingAddress": {
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
    },
    "contactEmail": "awais+111t@evelt.com",
    "contactPhone": "123456789",
    "shippingMethodsJson": [
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
    ],
    "contactFirstName": "Awais",
    "contactLastName": "Zafar",
    "companyName": "STYLE",
    "createdAt": "2023-11-08 16:11:30",
    "editedAt": "2023-11-08 16:11:30",
    "pricing": {
        "productsTotal": 74.85,
        "origTotal": 74.85,
        "subTotal": 74.85,
        "totalCouponDiscount": 0,
        "totalAfterCoupon": 74.85,
        "shipping": 50,
        "tax": 0.75,
        "total": 125.75
    },
    "couponCodesInfo": []
}
```

## Quote Checkout | Step 2 - Apply Coupon

### HTTP Request

`POST https://adminapi.csomni.com/checkout/applycoupon/quote_bWFkhPpaL56P`

### URL Parameters

| Parameter                     | Description                                                           |
| -------------------------     | --------------------------------------------------------------------- |
| token                         | site Token (header)                                                   |
| customerToken                 | customer Token (header)                                               |
| quoteToken(GET)               | Token of the Quote to retrieve.                                       |
| couponCode (POST)             | couponCode                                                            |

```shell
curl --location --request POST 'https://adminapidev.csomni.com/checkout/applycoupon/quote_bWFkhPpaL56P' \
--header 'token: site_123' \
--header 'customerToken: cs_123' \
--header 'Content-Type: application/json' \
--data-raw '{
    "couponCode": "caltmann"
}'
```

Response: 

```json
{
    "id": 30921,
    "cartToken": "quoteCart_9oIkF6fedNUOH6K8MBgHhmCV",
    "customerToken": "cs_lla3GWnCzC16YfMsPyI06sAoggU2TGHtcnld",
    "couponCodes": [
        "caltmann"
    ],
    "addressToken": "",
    "shippingMethod": "{\"id\":\"shippingQuoteToken_ILwH778I1HNj\",\"quote_shippingQuoteToken\":\"shippingQuoteToken_ILwH778I1HNj\",\"quoteToken\":\"quote_bWFkhPpaL56P\",\"carrier\":\"TCS\",\"methodName\":\"TCS\",\"origRate\":\"\",\"rate\":\"0.00\",\"deliveryDateTime\":\"\",\"deliveryDays\":\"2\",\"description\":\"\",\"approved\":1,\"approvedBy\":null}",
    "shippingMethodId": "shippingQuoteToken_3yw8DHZYCYvk",
    "shippingAddressLabel": "",
    "shippingAddress": {
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
    },
    "contactEmail": "awais+111t@evelt.com",
    "contactPhone": "123456789",
    "shippingMethodsJson": [
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
    ],
    "contactFirstName": "Awais",
    "contactLastName": "Zafar",
    "companyName": "STYLE",
    "createdAt": "2023-11-08 16:11:30",
    "editedAt": "2023-11-08 16:11:30",
    "pricing": {
        "productsTotal": 74.85,
        "origTotal": 74.85,
        "subTotal": 74.85,
        "totalCouponDiscount": 74.78,
        "totalAfterCoupon": 0.07,
        "shipping": 50,
        "tax": 0,
        "total": 50.07
    },
    "couponCodesInfo": [
        {
            "name": "caltmann",
            "msg": "Successfully applied",
            "discountAmount": 74.78,
            "status": "valid"
        }
    ]
}
```



## Quote Checkout | Step 3 - Pay by CC

### HTTP Request

`POST https://adminapi.csomni.com/checkout/payment/quote_bWFkhPpaL56P`

```shell
curl --location --request POST 'https://adminapi.csomni.com/checkout/payment/quote_bWFkhPpaL56P' \
--header 'token: site_123' \
--header 'customerToken: cs_123' \
--header 'Content-Type: application/json' \
--data-raw '{
    "nameOnCard": "name on card",
    "cardNumbers": "1233213213232321",
    "expMonth": "01",
    "expYear": "26",
    "cvv": "732",
    "billingAddress": "10 Eros Drive",
    "billingCity": "Airmont",
    "billingState": "NY",
    "billingZip": "10952",
    "billingCountry": "United States",
    "billingPhone": "000000",
    "orderNotePublic": "this is a public note I wrote and submited through payment checkout api call",
    "po": "1234"
}'
```

Response: 

```json
{
    "status": "success",
    "order": {
        "orderProducts": [
            {
                "cartToken": "quoteCart_QZC2rh7f6HtxNtOa0bYMXKy6",
                "cartProdToken": "cp_G7E7KZdkrcXOVHpdlx5SBCPN",
                "cartProdQuantity": 55,
                "prodToken": "vrnt_80zIBJ85QSyj7n04",
                "created_at": "2023-11-08 16:53:54",
                "updated_at": "2023-11-08 16:53:54",
                "deleted": 0,
                "deleted_at": null,
                "companyToken": "comp_fxJJZhdcNMfRF9m",
                "siteToken": "site_63Vdsmr9Qsq0",
                "quoteToken": "quote_bWFkhPpaL56P",
                "quoteCartToken": "quoteCart_QZC2rh7f6HtxNtOa0bYMXKy6",
                "customerToken": "cs_lla3GWnCzC16YfMsPyI06sAoggU2TGHtcnld",
                "addOnProdTokens": "",
                "prodStaticCollections": [],
                "specialValues": [],
                "product": {
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
                    "prodName": "Generic Rubber Hat primary",
                    "prodImage": {
                        "file": "vel-sint-qui"
                    }
                },
                "addOnProducts": [],
                "pricing": {
                    "total": 5.5
                },
                "shipping": {
                    "totalWeight": 55
                }
            },
            {
                "cartToken": "quoteCart_QZC2rh7f6HtxNtOa0bYMXKy6",
                "cartProdToken": "cp_pZs6BC43xbHCSE0JUHB8RskT",
                "cartProdQuantity": 55,
                "prodToken": "vrnt_80zIBJ85QSyj7n04",
                "created_at": "2023-11-08 16:53:54",
                "updated_at": "2023-11-08 16:53:54",
                "deleted": 0,
                "deleted_at": null,
                "companyToken": "comp_fxJJZhdcNMfRF9m",
                "siteToken": "site_63Vdsmr9Qsq0",
                "quoteToken": "quote_bWFkhPpaL56P",
                "quoteCartToken": "quoteCart_QZC2rh7f6HtxNtOa0bYMXKy6",
                "customerToken": "cs_lla3GWnCzC16YfMsPyI06sAoggU2TGHtcnld",
                "addOnProdTokens": "",
                "prodStaticCollections": [],
                "specialValues": [],
                "product": {
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
                    "prodName": "Generic Rubber Hat primary",
                    "prodImage": {
                        "file": "vel-sint-qui"
                    }
                },
                "addOnProducts": [],
                "pricing": {
                    "total": 5.5
                },
                "shipping": {
                    "totalWeight": 55
                }
            },
            {
                "cartToken": "quoteCart_QZC2rh7f6HtxNtOa0bYMXKy6",
                "cartProdToken": "cp_uiRR3Dn7EVK69Tq3d2zzhMAo",
                "cartProdQuantity": 55,
                "prodToken": "vrnt_80zIBJ85QSyj7n04",
                "created_at": "2023-11-08 16:53:54",
                "updated_at": "2023-11-08 16:53:54",
                "deleted": 0,
                "deleted_at": null,
                "companyToken": "comp_fxJJZhdcNMfRF9m",
                "siteToken": "site_63Vdsmr9Qsq0",
                "quoteToken": "quote_bWFkhPpaL56P",
                "quoteCartToken": "quoteCart_QZC2rh7f6HtxNtOa0bYMXKy6",
                "customerToken": "cs_lla3GWnCzC16YfMsPyI06sAoggU2TGHtcnld",
                "addOnProdTokens": "",
                "prodStaticCollections": [],
                "specialValues": [],
                "product": {
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
                    "prodName": "Generic Rubber Hat primary",
                    "prodImage": {
                        "file": "vel-sint-qui"
                    }
                },
                "addOnProducts": [],
                "pricing": {
                    "total": 5.5
                },
                "shipping": {
                    "totalWeight": 55
                }
            }
        ],
        "orderEmail": "awais+111t@evelt.com",
        "orderShippingMethod": "{\"id\":\"shippingQuoteToken_ILwH778I1HNj\",\"quote_shippingQuoteToken\":\"shippingQuoteToken_ILwH778I1HNj\",\"quoteToken\":\"quote_bWFkhPpaL56P\",\"carrier\":\"TCS\",\"methodName\":\"TCS\",\"origRate\":\"\",\"rate\":\"0.00\",\"deliveryDateTime\":\"\",\"deliveryDays\":\"2\",\"description\":\"\",\"approved\":1,\"approvedBy\":null}",
        "orderTotal": 0.07,
        "orderTax": 0,
        "orderTotalPaid": "0.07",
        "orderShipping": 0,
        "orderWeight": 165,
        "orderShippingAddress": "{\"address\":\"12354 Main Street\",\"address2\":\"dont ship\",\"city\":\"Monsey\",\"state\":\"NY\",\"zip\":\"10952\",\"country\":\"\",\"phone\":\"\",\"mobile\":\"\",\"specialValues\":null}",
        "orderPaymentMethod": {
            "xResult": "A",
            "xStatus": "Approved",
            "xError": "",
            "xErrorCode": "00000",
            "xRefNum": "1181967971",
            "xExp": "0126",
            "xAuthCode": "56263A",
            "xBatch": "5150840",
            "xAvsResultCode": "NNN",
            "xAvsResult": "Address: No Match & 5 Digit Zip: No Match",
            "xCvvResultCode": "",
            "xCvvResult": "No CVV data available",
            "xAuthAmount": "0.07",
            "xMaskedCardNumber": "4xxxxxxxxxxx2438",
            "xCardType": "Visa",
            "xName": "Jay Klein",
            "xToken": "gn7947h075pgh5h8g5743609p6g6552p",
            "xMID": "xxxxxxxxxx9999",
            "xTID": "xxxxx6789",
            "xCurrency": "USD",
            "xDate": "11/8/2023 7:19:43 AM",
            "xEntryMethod": "Keyed",
            "cardToken": "cc_ph4FGz1wiFQx"
        },
        "contactLastName": "Zafar",
        "contactFirstName": "Awais",
        "orderProdQuantity": 165,
        "paymentObject": "{\"xResult\":\"A\",\"xStatus\":\"Approved\",\"xError\":\"\",\"xErrorCode\":\"00000\",\"xRefNum\":\"1181967971\",\"xExp\":\"0126\",\"xAuthCode\":\"56263A\",\"xBatch\":\"5150840\",\"xAvsResultCode\":\"NNN\",\"xAvsResult\":\"Address: No Match & 5 Digit Zip: No Match\",\"xCvvResultCode\":\"\",\"xCvvResult\":\"No CVV data available\",\"xAuthAmount\":\"0.07\",\"xMaskedCardNumber\":\"4xxxxxxxxxxx2438\",\"xCardType\":\"Visa\",\"xName\":\"Jay Klein\",\"xToken\":\"gn7947h075pgh5h8g5743609p6g6552p\",\"xMID\":\"xxxxxxxxxx9999\",\"xTID\":\"xxxxx6789\",\"xCurrency\":\"USD\",\"xDate\":\"11\\/8\\/2023 7:19:43 AM\",\"xEntryMethod\":\"Keyed\",\"cardToken\":\"cc_ph4FGz1wiFQx\"}",
        "cardToken": "cc_ph4FGz1wiFQx",
        "orderIP": "127.0.0.1",
        "cartToken": "quoteCart_QZC2rh7f6HtxNtOa0bYMXKy6",
        "PO": "1234",
        "BillToName": "Jay Klein",
        "BillToAddress": "{\"name\":\"Jay Klein\",\"address\":\"10 Eros Drive\",\"address2\":\"\",\"zip\":\"10952\",\"city\":\"Airmont\",\"state\":\"NY\",\"country\":\"United States\",\"mobile\":\"\",\"phone\":\"000000\"}",
        "orderNotePublic": "this is a public note I wrote and submited through payment checkout api call",
        "quoteToken": "quote_bWFkhPpaL56P",
        "siteToken": "site_63Vdsmr9Qsq0",
        "companyToken": "comp_fxJJZhdcNMfRF9m",
        "customerToken": "cust_l513Z8XmSeXRy94tzGaQWfLQ",
        "orderToken": "ordr_O2tCzcOrPNJZMXLqhjXZp7JJ",
        "orderNumber": 100000255,
        "orderStatus": "os_awaiting_fulfillment",
        "checkoutObject": "{\"id\":30921,\"cartToken\":\"quoteCart_QZC2rh7f6HtxNtOa0bYMXKy6\",\"customerToken\":\"cs_lla3GWnCzC16YfMsPyI06sAoggU2TGHtcnld\",\"couponCodes\":[\"caltmann\"],\"addressToken\":\"\",\"shippingMethod\":\"\",\"shippingMethodId\":\"\",\"shippingAddressLabel\":\"\",\"shippingAddress\":{\"address\":\"12354 Main Street\",\"address2\":\"dont ship\",\"city\":\"Monsey\",\"state\":\"NY\",\"zip\":\"10952\",\"country\":\"\",\"phone\":\"\",\"mobile\":\"\",\"specialValues\":null},\"contactEmail\":\"awais+111t@evelt.com\",\"contactPhone\":\"123456789\",\"shippingMethodsJson\":{\"error\":\"Missing previous steps\"},\"contactFirstName\":\"Awais\",\"contactLastName\":\"Zafar\",\"companyName\":\"STYLE\",\"createdAt\":\"2023-11-08 16:11:30\",\"editedAt\":\"2023-11-08 17:20:11\",\"pricing\":{\"productsTotal\":74.85,\"origTotal\":74.85,\"subTotal\":74.85,\"totalCouponDiscount\":74.78,\"totalAfterCoupon\":0.07,\"shipping\":0,\"tax\":0,\"total\":0.07},\"couponCodesInfo\":[{\"name\":\"caltmann\",\"msg\":\"Successfully applied\",\"discountAmount\":74.78,\"status\":\"valid\"}]}",
        "customerObject": "{\"customerFirstName\":\"Awais\",\"customerLastName\":\"Zafar\",\"customerEmail\":\"awais+111t@evelt.com\",\"customerPhone\":\"123456789\",\"customerCompanyName\":\"STYLE\",\"source\":\"store\",\"customerStatus\":\"cs_approved\",\"customerTypes\":null,\"customerGroups\":null,\"isLoggedIn\":1,\"customerDocs\":null,\"taxExempt\":null,\"taxExemptID\":null,\"createdAt\":\"2023-10-28 11:43:26\"}",
        "dateCreated": 1699446014,
        "statusTermsData": {
            "processingStatus": "Processing",
            "shippingStatus": "Pending",
            "paymentStatus": "Closed",
            "orderStatus": "Open",
            "paymentTerms": "Website Payment Transaction",
            "postPaymentStatus": " NULL"
        }
    }
}
```

## Quote Checkout | Step 3 - Invoice Quote

### HTTP Request

`POST https://adminapi.csomni.com/checkout/po/quote_bWFkhPpaL56P`


```shell
curl --location --request POST 'https://adminapi.csomni.com/checkout/po/quote_bWFkhPpaL56P' \
--header 'token: site_123' \
--header 'customerToken: cs_123' \
--header 'Content-Type: application/json' \
--data-raw '{
    "po": "123-P9ojd",
    "billingName": "431 Systems LLC",
    "billingAddress": "10 Eros Drive",
    "billingCity": "Airmont",
    "billingState": "NY",
    "billingZip": "10952",
    "billingCountry": "United States",
    "billingPhone": "000000",
    "orderNotePublic": "order paid through PO pathway"
}'
```

Response: 

```json
{
    "status": "success",
    "order": {
        "orderProducts": [
            {
                "cartToken": "quoteCart_QZC2rh7f6HtxNtOa0bYMXKy6",
                "cartProdToken": "cp_G7E7KZdkrcXOVHpdlx5SBCPN",
                "cartProdQuantity": 55,
                "prodToken": "vrnt_80zIBJ85QSyj7n04",
                "created_at": "2023-11-08 16:53:54",
                "updated_at": "2023-11-08 16:53:54",
                "deleted": 0,
                "deleted_at": null,
                "companyToken": "comp_fxJJZhdcNMfRF9m",
                "siteToken": "site_63Vdsmr9Qsq0",
                "quoteToken": "quote_bWFkhPpaL56P",
                "quoteCartToken": "quoteCart_QZC2rh7f6HtxNtOa0bYMXKy6",
                "customerToken": "cs_lla3GWnCzC16YfMsPyI06sAoggU2TGHtcnld",
                "addOnProdTokens": "",
                "prodStaticCollections": [],
                "specialValues": [],
                "product": {
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
                    "prodName": "Generic Rubber Hat primary",
                    "prodImage": {
                        "file": "vel-sint-qui"
                    }
                },
                "addOnProducts": [],
                "pricing": {
                    "total": 5.5
                },
                "shipping": {
                    "totalWeight": 55
                }
            },
            {
                "cartToken": "quoteCart_QZC2rh7f6HtxNtOa0bYMXKy6",
                "cartProdToken": "cp_pZs6BC43xbHCSE0JUHB8RskT",
                "cartProdQuantity": 55,
                "prodToken": "vrnt_80zIBJ85QSyj7n04",
                "created_at": "2023-11-08 16:53:54",
                "updated_at": "2023-11-08 16:53:54",
                "deleted": 0,
                "deleted_at": null,
                "companyToken": "comp_fxJJZhdcNMfRF9m",
                "siteToken": "site_63Vdsmr9Qsq0",
                "quoteToken": "quote_bWFkhPpaL56P",
                "quoteCartToken": "quoteCart_QZC2rh7f6HtxNtOa0bYMXKy6",
                "customerToken": "cs_lla3GWnCzC16YfMsPyI06sAoggU2TGHtcnld",
                "addOnProdTokens": "",
                "prodStaticCollections": [],
                "specialValues": [],
                "product": {
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
                    "prodName": "Generic Rubber Hat primary",
                    "prodImage": {
                        "file": "vel-sint-qui"
                    }
                },
                "addOnProducts": [],
                "pricing": {
                    "total": 5.5
                },
                "shipping": {
                    "totalWeight": 55
                }
            },
            {
                "cartToken": "quoteCart_QZC2rh7f6HtxNtOa0bYMXKy6",
                "cartProdToken": "cp_uiRR3Dn7EVK69Tq3d2zzhMAo",
                "cartProdQuantity": 55,
                "prodToken": "vrnt_80zIBJ85QSyj7n04",
                "created_at": "2023-11-08 16:53:54",
                "updated_at": "2023-11-08 16:53:54",
                "deleted": 0,
                "deleted_at": null,
                "companyToken": "comp_fxJJZhdcNMfRF9m",
                "siteToken": "site_63Vdsmr9Qsq0",
                "quoteToken": "quote_bWFkhPpaL56P",
                "quoteCartToken": "quoteCart_QZC2rh7f6HtxNtOa0bYMXKy6",
                "customerToken": "cs_lla3GWnCzC16YfMsPyI06sAoggU2TGHtcnld",
                "addOnProdTokens": "",
                "prodStaticCollections": [],
                "specialValues": [],
                "product": {
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
                    "prodName": "Generic Rubber Hat primary",
                    "prodImage": {
                        "file": "vel-sint-qui"
                    }
                },
                "addOnProducts": [],
                "pricing": {
                    "total": 5.5
                },
                "shipping": {
                    "totalWeight": 55
                }
            }
        ],
        "orderEmail": "awais+111t@evelt.com",
        "orderShippingMethod": "{\"id\":\"shippingQuoteToken_ILwH778I1HNj\",\"quote_shippingQuoteToken\":\"shippingQuoteToken_ILwH778I1HNj\",\"quoteToken\":\"quote_bWFkhPpaL56P\",\"carrier\":\"TCS\",\"methodName\":\"TCS\",\"origRate\":\"\",\"rate\":\"0.00\",\"deliveryDateTime\":\"\",\"deliveryDays\":\"2\",\"description\":\"\",\"approved\":1,\"approvedBy\":null}",
        "orderTotal": 0.07,
        "orderTax": 0,
        "orderTotalPaid": "0.07",
        "orderShipping": 0,
        "orderWeight": 165,
        "orderShippingAddress": "{\"address\":\"12354 Main Street\",\"address2\":\"dont ship\",\"city\":\"Monsey\",\"state\":\"NY\",\"zip\":\"10952\",\"country\":\"\",\"phone\":\"\",\"mobile\":\"\",\"specialValues\":null}",
        "orderPaymentMethod": {
            "xResult": "A",
            "xStatus": "Approved",
            "xError": "",
            "xErrorCode": "00000",
            "xRefNum": "1181967971",
            "xExp": "0126",
            "xAuthCode": "56263A",
            "xBatch": "5150840",
            "xAvsResultCode": "NNN",
            "xAvsResult": "Address: No Match & 5 Digit Zip: No Match",
            "xCvvResultCode": "",
            "xCvvResult": "No CVV data available",
            "xAuthAmount": "0.07",
            "xMaskedCardNumber": "4xxxxxxxxxxx2438",
            "xCardType": "Visa",
            "xName": "Jay Klein",
            "xToken": "gn7947h075pgh5h8g5743609p6g6552p",
            "xMID": "xxxxxxxxxx9999",
            "xTID": "xxxxx6789",
            "xCurrency": "USD",
            "xDate": "11/8/2023 7:19:43 AM",
            "xEntryMethod": "Keyed",
            "cardToken": "cc_ph4FGz1wiFQx"
        },
        "contactLastName": "Zafar",
        "contactFirstName": "Awais",
        "orderProdQuantity": 165,
        "paymentObject": "{\"xResult\":\"A\",\"xStatus\":\"Approved\",\"xError\":\"\",\"xErrorCode\":\"00000\",\"xRefNum\":\"1181967971\",\"xExp\":\"0126\",\"xAuthCode\":\"56263A\",\"xBatch\":\"5150840\",\"xAvsResultCode\":\"NNN\",\"xAvsResult\":\"Address: No Match & 5 Digit Zip: No Match\",\"xCvvResultCode\":\"\",\"xCvvResult\":\"No CVV data available\",\"xAuthAmount\":\"0.07\",\"xMaskedCardNumber\":\"4xxxxxxxxxxx2438\",\"xCardType\":\"Visa\",\"xName\":\"Jay Klein\",\"xToken\":\"gn7947h075pgh5h8g5743609p6g6552p\",\"xMID\":\"xxxxxxxxxx9999\",\"xTID\":\"xxxxx6789\",\"xCurrency\":\"USD\",\"xDate\":\"11\\/8\\/2023 7:19:43 AM\",\"xEntryMethod\":\"Keyed\",\"cardToken\":\"cc_ph4FGz1wiFQx\"}",
        "cardToken": "cc_ph4FGz1wiFQx",
        "orderIP": "127.0.0.1",
        "cartToken": "quoteCart_QZC2rh7f6HtxNtOa0bYMXKy6",
        "PO": "1234",
        "BillToName": "Jay Klein",
        "BillToAddress": "{\"name\":\"Jay Klein\",\"address\":\"10 Eros Drive\",\"address2\":\"\",\"zip\":\"10952\",\"city\":\"Airmont\",\"state\":\"NY\",\"country\":\"United States\",\"mobile\":\"\",\"phone\":\"000000\"}",
        "orderNotePublic": "this is a public note I wrote and submited through payment checkout api call",
        "quoteToken": "quote_bWFkhPpaL56P",
        "siteToken": "site_63Vdsmr9Qsq0",
        "companyToken": "comp_fxJJZhdcNMfRF9m",
        "customerToken": "cust_l513Z8XmSeXRy94tzGaQWfLQ",
        "orderToken": "ordr_O2tCzcOrPNJZMXLqhjXZp7JJ",
        "orderNumber": 100000255,
        "orderStatus": "os_awaiting_fulfillment",
        "checkoutObject": "{\"id\":30921,\"cartToken\":\"quoteCart_QZC2rh7f6HtxNtOa0bYMXKy6\",\"customerToken\":\"cs_lla3GWnCzC16YfMsPyI06sAoggU2TGHtcnld\",\"couponCodes\":[\"caltmann\"],\"addressToken\":\"\",\"shippingMethod\":\"\",\"shippingMethodId\":\"\",\"shippingAddressLabel\":\"\",\"shippingAddress\":{\"address\":\"12354 Main Street\",\"address2\":\"dont ship\",\"city\":\"Monsey\",\"state\":\"NY\",\"zip\":\"10952\",\"country\":\"\",\"phone\":\"\",\"mobile\":\"\",\"specialValues\":null},\"contactEmail\":\"awais+111t@evelt.com\",\"contactPhone\":\"123456789\",\"shippingMethodsJson\":{\"error\":\"Missing previous steps\"},\"contactFirstName\":\"Awais\",\"contactLastName\":\"Zafar\",\"companyName\":\"STYLE\",\"createdAt\":\"2023-11-08 16:11:30\",\"editedAt\":\"2023-11-08 17:20:11\",\"pricing\":{\"productsTotal\":74.85,\"origTotal\":74.85,\"subTotal\":74.85,\"totalCouponDiscount\":74.78,\"totalAfterCoupon\":0.07,\"shipping\":0,\"tax\":0,\"total\":0.07},\"couponCodesInfo\":[{\"name\":\"caltmann\",\"msg\":\"Successfully applied\",\"discountAmount\":74.78,\"status\":\"valid\"}]}",
        "customerObject": "{\"customerFirstName\":\"Awais\",\"customerLastName\":\"Zafar\",\"customerEmail\":\"awais+111t@evelt.com\",\"customerPhone\":\"123456789\",\"customerCompanyName\":\"STYLE\",\"source\":\"store\",\"customerStatus\":\"cs_approved\",\"customerTypes\":null,\"customerGroups\":null,\"isLoggedIn\":1,\"customerDocs\":null,\"taxExempt\":null,\"taxExemptID\":null,\"createdAt\":\"2023-10-28 11:43:26\"}",
        "dateCreated": 1699446014,
        "statusTermsData": {
            "processingStatus": "Processing",
            "shippingStatus": "Pending",
            "paymentStatus": "Closed",
            "orderStatus": "Open",
            "paymentTerms": "Website Payment Transaction",
            "postPaymentStatus": " NULL"
        }
    }
}
```

## Delete a Specific quote

### HTTP Request

`DELETE https://adminapi.csomni.com/quotes/{quoteToken}`

```shell
curl --location --request DELETE 'https://adminapidev.csomni.com/quotes/quote_9Uih2O4wb9Ys' \
--header 'token: site_123' \
--header 'customerToken: cs_123'
```

Response:

```json
{
  "token": "quote_SCOBBRFrfpXV",
  "deleted": "true"
}
```
