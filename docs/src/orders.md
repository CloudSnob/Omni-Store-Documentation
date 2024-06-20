# Orders

## Get all orders by customer

This endpoint retrieves orders for a specified customer


#### HTTP Request
`GET https://storeapi.csomni.com/orders`

### Header Parameters
| Parameter     | Required | Type   | Description       |
|---------------|----------|--------|-------------------|
| siteToken     | true     | string | Site ID token     |
| customerToken | true     | string | Customer ID token |


```shell
curl --request GET \
  --url https://storeapi.csomni.com/orders \
  --header 'token: cs_xxxxxxxxxxxxxxx'\
  --header 'token: site_xxxxxxxxxxxxxx
```

> The above command returns JSON structured like this:

```json
[
  {
    "orderToken": "ordr_4xCT42nj1QKZjSVbPvj6XE1X",
    "orderNumber": 100000479,
    "PO": "123-245jk",
    "quoteToken": "",
    "siteToken": "site_63Vdsmr9Qsq0",
    "customerToken": "cs_GWdE9xY2dcL9qqBmNKx7WXivTh73nJtGH4NK",
    "orderProducts": [
      {
        "cartToken": "cart_Q0eM8x84bURo3tPUmm8fBKsH",
        "cartProdToken": "cp_qkm6rKGV1qgGjZFNn1pYc6Bi",
        "cartProdQuantity": 1,
        "addOnToProdToken": "",
        "addOnProdTokens": null,
        "prodToken": "vrnt_EvonkJQsR6fRbDtm",
        "deleted": 0,
        "createdAt": "2024-06-19 10:04:42",
        "editedAt": "2024-06-19 10:04:42",
        "siteToken": "site_xxxxxxxxxx",
        "customerToken": "cs_4JRbcroAdSipjf5XQf7dnSn9xuYgnGUiQloz",
        "cartCreated": "1718791482",
        "cartLastTouched": "1718791482",
        "prodStaticCollections": [
          "clcs_DMtKEagwAAPjuKy7"
        ],
        "specialValues": [],
        "product": {
          "prodToken": "prod_Q73DQtIhj9IJzZ0y",
          "variantToken": "vrnt_EvonkJQsR6fRbDtm",
          "variantName": "",
          "variantImage": {
            "file": "11-25-2022\/1669391493868__30709__NS-35859.jpg",
            "type": "",
            "id": "srn5s4aj",
            "status": "poolImages"
          },
          "variantImages": [],
          "variantWeight": "1",
          "variantDimW": "0",
          "variantDimL": "0",
          "variantDimH": "0",
          "variantUpc": "",
          "variantNumber": "NS-35859",
          "manufacturerPartNumber": "",
          "variantPrice": 0.3,
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
          "google_variantCategory": "",
          "google_variantType": "",
          "google_variantCondition": "",
          "taxable": 1,
          "variantAllowCheckout": 0,
          "variantCheckInvetory": 0,
          "variantTrackInventory": 0,
          "inventoryCount": -16,
          "shippingProduct": 1,
          "variantMetaTitle": "",
          "variantMetaDescription": "",
          "variantBrand": "",
          "sortOrder": 0,
          "dateCreated": "1669391499",
          "deleted": 0,
          "backOrderWarning": 0,
          "createdAt": "2022-12-18 23:01:04",
          "editedAt": "2024-06-19 10:07:50",
          "variantInStock": true,
          "prodName": "3\/4 IN. O.D. SATIN NICKEL DRIVE-IN, SPRING LOADED, BALL STYLE, CABINET DOOR LATCH WITH STRIKE\t",
          "prodImage": {
            "file": "11-25-2022\/1669391493868__30709__NS-35859.jpg",
            "type": ""
          }
        },
        "addOnProducts": [],
        "pricing": {
          "total": 0.3
        },
        "shipping": {
          "totalWeight": 1
        }
      }
    ],
    "BillToName": "Sarah Jones",
    "BillToAddress": "{\"name\":\"Sarah Jones\",\"zip\":\"10952\",\"address\":\"123 Main street\",\"address2\":\"Unit 4\",\"city\":\"NY\",\"state\":\"NY\",\"country\":\"\",\"phone\":\"03356705565\",\"mobile\":\"\"}",
    "orderShippingMethod": {
      "carrier": "freeshipping",
      "description": "",
      "deliveryDateTime": null,
      "deliveryDays": null,
      "origRate": 0,
      "rate": 0,
      "id": "CXadfoscekBHyxDQKGW9ORUv",
      "methodName": "Free Shipping"
    },
    "orderShippingAddress": {
      "address": "123 Main street",
      "address2": "Unit 4",
      "city": "NY",
      "state": "NY",
      "zip": "10952",
      "country": "",
      "phone": "03356705565",
      "mobile": "",
      "specialValues": []
    },
    "orderTotal": "0.15",
    "orderTax": "",
    "orderTotalPaid": "0.15",
    "orderShipping": "",
    "orderStatus": "os_awaiting_fulfillment",
    "paymentStatus": null,
    "fullfilmentStatus": null,
    "shippingStatus": null,
    "customerObject": {
      "customerFirstName": "Morris12",
      "customerLastName": "Almey",
      "customerEmail": "chris@chris.com",
      "customerPhone": "",
      "customerCompanyName": "",
      "source": "store",
      "customerStatus": "",
      "customerTypes": null,
      "customerGroups": null,
      "isLoggedIn": 1,
      "customerDocs": "",
      "taxExempt": null,
      "taxExemptID": null,
      "createdAt": "2024-05-16 11:11:53"
    },
    "orderWeight": 1,
    "contactFirstName": "Sarah",
    "contactLastName": "Jones",
    "orderEmail": "chris@chris.com",
    "orderNotePublic": "",
    "cartToken": "cart_Q0eM8x84bURo3tPUmm8fBKsH",
    "orderPaymentMethod": "{\"xResult\":\"A\",\"xStatus\":\"Approved\",\"xError\":\"\",\"xErrorCode\":\"00000\",\"xRefNum\":\"10032644615\",\"xExp\":\"0126\",\"xAuthCode\":\"53783A\",\"xBatch\":\"5150840\",\"xAvsResultCode\":\"NNN\",\"xAvsResult\":\"Address: No Match & 5 Digit Zip: No Match\",\"xCvvResultCode\":\"\",\"xCvvResult\":\"No CVV data available\",\"xAuthAmount\":\"0.15\",\"xMaskedCardNumber\":\"#xxxxxxxxxxx####\",\"xCardType\":\"Visa\",\"xName\":\"Sarah Jones\",\"xToken\":\"xxxxxxxxxxxxxxxxxxxxx\",\"xMID\":\"xxxxxxxxxx####\",\"xTID\":\"xxxxx####\",\"xCurrency\":\"USD\",\"xDate\":\"6\\\/19\\\/2024 6:10:30 AM\",\"xEntryMethod\":\"Keyed\",\"cardToken\":\"cc_xxxxxxxxxxxxxxx\"}",
    "checkoutObject": {
      "id": 31083,
      "cartToken": "cart_Q0eM8x84bURo3tPUmm8fBKsH",
      "customerToken": "cs_4JRbcroAdSipjf5XQf7dnSn9xuYgnGUiQloz",
      "couponCodes": [
        "ca"
      ],
      "addressToken": "adrs_CJO9LkwmNJqSQmOBtaTsGE1w",
      "shippingMethod": {
        "carrier": "freeshipping",
        "description": "",
        "deliveryDateTime": null,
        "deliveryDays": null,
        "origRate": 0,
        "rate": 0,
        "id": "CXadfoscekBHyxDQKGW9ORUv",
        "methodName": "Free Shipping"
      },
      "shippingMethodId": "CXadfoscekBHyxDQKGW9ORUv",
      "shippingAddressLabel": "",
      "shippingAddress": {
        "address": "123 Main street",
        "address2": "Unit 4",
        "city": "NY",
        "state": "NY",
        "zip": "10952",
        "country": "",
        "phone": "03356705565",
        "mobile": "",
        "specialValues": []
      },
      "contactEmail": "chris@chris.com",
      "contactPhone": "",
      "shippingMethodsJson": [
        {
          "carrier": "freeshipping",
          "description": "",
          "deliveryDateTime": null,
          "deliveryDays": null,
          "origRate": 0,
          "rate": 0,
          "id": "CXadfoscekBHyxDQKGW9ORUv",
          "methodName": "Free Shipping"
        }
      ],
      "contactFirstName": "Sarah",
      "contactLastName": "Jones",
      "companyName": "",
      "createdAt": "2024-06-19 10:05:01",
      "editedAt": "2024-06-19 10:10:30",
      "pricing": {
        "productsTotal": 0.3,
        "origTotal": 0.3,
        "subTotal": 0.3,
        "totalCouponDiscount": 0.15,
        "totalAfterCoupon": 0.15,
        "shipping": 0,
        "tax": 0,
        "total": 0.15
      },
      "couponCodesInfo": [
        {
          "name": "ca",
          "msg": "Successfully applied",
          "discountAmount": 0.15,
          "status": "valid"
        }
      ]
    },
    "orderProdQuantity": "1",
    "paymentObject": {
      "xResult": "A",
      "xStatus": "Approved",
      "xError": "",
      "xErrorCode": "00000",
      "xRefNum": "10032644615",
      "xExp": "0126",
      "xAuthCode": "53783A",
      "xBatch": "5150840",
      "xAvsResultCode": "NNN",
      "xAvsResult": "Address: No Match & 5 Digit Zip: No Match",
      "xCvvResultCode": "",
      "xCvvResult": "No CVV data available",
      "xAuthAmount": "0.15",
      "xMaskedCardNumber": "4xxxxxxxxxxx####",
      "xCardType": "Visa",
      "xName": "Sarah Jones",
      "xToken": "xxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
      "xMID": "xxxxxxxxxx####",
      "xTID": "xxxxx####",
      "xCurrency": "USD",
      "xDate": "6\/19\/2024 6:10:30 AM",
      "xEntryMethod": "Keyed",
      "cardToken": "cc_xxxxxxxxxxxx"
    },
    "cardToken": "cc_xxxxxxxxxxxx",
    "orderIP": "00.000.00.00",
    "dateCreated": "1718791832",
    "deleted": "",
    "numberOfPackages": 0,
    "createdAt": "2024-06-19 10:10:32",
    "editedAt": "2024-06-19 10:10:32",
    "orderStatusValue": {
      "id": "os_awaiting_fulfillment",
      "name": "Awaiting Fulfillment",
      "color": "#ffc107"
    },
    "statusAndTerms": {
      "processingStatus": "Processing",
      "shippingStatus": "Pending",
      "paymentStatus": "Closed",
      "orderStatus": "Open",
      "paymentTerms": "Website Payment Transaction",
      "postPaymentStatus": " NULL"
    },
    "paymentHistory": [
      {
        "paymentHistoryToken": "pmth_nTjBOQKah8UuXCJKtBo0MzaLthnOREzS8pgR",
        "orderToken": "ordr_4xCT42nj1QKZjSVbPvj6XE1X",
        "amount": 0.15,
        "action": "charge",
        "transactionType": null,
        "transactionDetails": null,
        "dateTime": "1718791832",
        "paymentObject": "{\"xResult\":\"A\",\"xStatus\":\"Approved\",\"xError\":\"\",\"xErrorCode\":\"00000\",\"xRefNum\":\"10032644615\",\"xExp\":\"0126\",\"xAuthCode\":\"xxxxxx\",\"xBatch\":\"xxxxxxx\",\"xAvsResultCode\":\"NNN\",\"xAvsResult\":\"Address: No Match & 5 Digit Zip: No Match\",\"xCvvResultCode\":\"\",\"xCvvResult\":\"No CVV data available\",\"xAuthAmount\":\"0.15\",\"xMaskedCardNumber\":\"4xxxxxxxxxxx####\",\"xCardType\":\"Visa\",\"xName\":\"Sarah Jones\",\"xToken\":\"xxxxxxxxxxxxxxxxxxxxxxxxxxxx\",\"xMID\":\"xxxxxxxxxx####\",\"xTID\":\"xxxxx####\",\"xCurrency\":\"USD\",\"xDate\":\"6\\\/19\\\/2024 6:10:30 AM\",\"xEntryMethod\":\"Keyed\",\"cardToken\":\"cc_xxxxxxxxxxx\"}",
        "cardToken": "cc_xxxxxxxxxxxxxx",
        "void": 0,
        "userToken": "omni",
        "createdAt": "2024-06-19 10:10:32",
        "editedAt": "2024-06-19 10:10:32"
      }
    ]
  },
  {
    "orderToken": "ordr_yKCGjswUz7EVEvR9VyysfYlm",
    "orderNumber": 100000478,
    "PO": "123-P9ojd",
    "quoteToken": "",
    "siteToken": "site_63Vdsmr9Qsq0",
    "customerToken": "cs_GWdE9xY2dcL9qqBmNKx7WXivTh73nJtGH4NK",
    "orderProducts": [
      {
        "cartToken": "cart_V08cc9sR1v5HUz0s6d7gwz5m",
        "cartProdToken": "cp_Mybm0x4rWqjPHYmRS2KX2rRi",
        "cartProdQuantity": 1,
        "addOnToProdToken": "",
        "addOnProdTokens": null,
        "prodToken": "vrnt_EvonkJQsR6fRbDtm",
        "deleted": 0,
        "createdAt": "2024-06-19 10:00:43",
        "editedAt": "2024-06-19 10:00:43",
        "siteToken": "site_63Vdsmr9Qsq0",
        "customerToken": "cs_7F8C4Rs2P86TyUhuUnQr9QnBHVLC6F0x133T",
        "cartCreated": "1718791243",
        "cartLastTouched": "1718791243",
        "prodStaticCollections": [
          "clcs_DMtKEagwAAPjuKy7"
        ],
        "specialValues": [],
        "product": {
          "prodToken": "prod_Q73DQtIhj9IJzZ0y",
          "variantToken": "vrnt_EvonkJQsR6fRbDtm",
          "variantName": "",
          "variantImage": {
            "file": "11-25-2022\/1669391493868__30709__NS-35859.jpg",
            "type": ""
          },
          "variantImages": [],
          "variantWeight": "1",
          "variantDimW": "0",
          "variantDimL": "0",
          "variantDimH": "0",
          "variantUpc": "",
          "variantNumber": "NS-35859",
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
          "google_variantCategory": "",
          "google_variantType": "",
          "google_variantCondition": "",
          "taxable": 1,
          "variantAllowCheckout": 0,
          "variantCheckInvetory": 0,
          "variantTrackInventory": 0,
          "inventoryCount": -15,
          "shippingProduct": 1,
          "variantMetaTitle": "",
          "variantMetaDescription": "",
          "variantBrand": "",
          "sortOrder": 0,
          "dateCreated": "1669391499",
          "deleted": 0,
          "backOrderWarning": 0,
          "createdAt": "2022-12-18 23:01:04",
          "editedAt": "2024-06-19 09:55:42",
          "variantInStock": true,
          "prodName": "3\/4 IN. O.D. SATIN NICKEL DRIVE-IN, SPRING LOADED, BALL STYLE, CABINET DOOR LATCH WITH STRIKE\t",
          "prodImage": {
            "file": "11-25-2022\/1669391493868__30709__NS-35859.jpg",
            "type": ""
          }
        },
        "addOnProducts": [],
        "pricing": {
          "total": 0.1
        },
        "shipping": {
          "totalWeight": 1
        }
      }
    ],
    "BillToName": "Sarah Jones",
    "BillToAddress": "{\"name\":\"Sarah Jones\",\"address\":\"123 Main street\",\"address2\":\"Unit 4\",\"zip\":\"10952\",\"city\":\"NY\",\"state\":\"NY\",\"country\":\"\",\"mobile\":\"\",\"phone\":\"03356705565\"}",
    "orderShippingMethod": {
      "carrier": "freeshipping",
      "description": "",
      "deliveryDateTime": null,
      "deliveryDays": null,
      "origRate": 0,
      "rate": 0,
      "id": "rWFATgIfBdaxXYLZoKu2EGcH",
      "methodName": "Free Shipping"
    },
    "orderShippingAddress": {
      "address": "123 Main street",
      "address2": "Unit 4",
      "city": "NY",
      "state": "NY",
      "zip": "10952",
      "country": "",
      "phone": "03356705565",
      "mobile": "",
      "specialValues": []
    },
    "orderTotal": "0.1",
    "orderTax": "",
    "orderTotalPaid": "",
    "orderShipping": "",
    "orderStatus": "os_awaiting_fulfillment",
    "paymentStatus": null,
    "fullfilmentStatus": null,
    "shippingStatus": null,
    "customerObject": {
      "customerFirstName": "Morris12",
      "customerLastName": "Yoman",
      "customerEmail": "chris@chris.com",
      "customerPhone": "",
      "customerCompanyName": "",
      "source": "store",
      "customerStatus": "",
      "customerTypes": null,
      "customerGroups": null,
      "isLoggedIn": 1,
      "customerDocs": "",
      "taxExempt": null,
      "taxExemptID": null,
      "createdAt": "2024-05-16 11:11:53"
    }
  ] 
```


## Get a specific order by order token
This endpoint retrieves a specific order by order token


### HTTP Request
`GET https://storeapi.csomni.com/orders/{orderToken]}

### Header Parameters
| Parameter     | Required | Type   | Description          |
|---------------|----------|--------|----------------------|
| siteToken     | true     | string | Unique siteToken     |
| customerToken | true     | string | Unique customerToken |

### URL Parameters
| Parameter  | Description                        |
|------------|------------------------------------|
| orderToken | ID token of the Order to retrieve. |

```shell
curl --request GET \
  --url https://storeapi.csomni.com/orders/{orderToken} \
  --header 'token: site_xxxxxxxxxx', 'customerToken: cs_xxxxxxxxxxx'/
```

> The above command returns JSON structured like this:

```json
{
  "orderToken": "ordr_4xCT42nj1QKZjSVbPvj6XE1X",
  "orderNumber": 100000479,
  "PO": "123-245jk",
  "quoteToken": "",
  "siteToken": "site_xxxxxxxxxxx",
  "customerToken": "cs_GWdE9xY2dcL9qqBmNKx7WXivTh73nJtGH4NK",
  "orderProducts": [
    {
      "cartToken": "cart_Q0eM8x84bURo3tPUmm8fBKsH",
      "cartProdToken": "cp_qkm6rKGV1qgGjZFNn1pYc6Bi",
      "cartProdQuantity": 1,
      "addOnToProdToken": "",
      "addOnProdTokens": null,
      "prodToken": "vrnt_EvonkJQsR6fRbDtm",
      "deleted": 0,
      "createdAt": "2024-06-19 10:04:42",
      "editedAt": "2024-06-19 10:04:42",
      "siteToken": "site_63Vdsmr9Qsq0",
      "customerToken": "cs_4JRbcroAdSipjf5XQf7dnSn9xuYgnGUiQloz",
      "cartCreated": "1718791482",
      "cartLastTouched": "1718791482",
      "prodStaticCollections": [
        "clcs_DMtKEagwAAPjuKy7"
      ],
      "specialValues": [],
      "product": {
        "prodToken": "prod_Q73DQtIhj9IJzZ0y",
        "variantToken": "vrnt_EvonkJQsR6fRbDtm",
        "variantName": "",
        "variantImage": {
          "file": "11-25-2022\/1669391493868__30709__NS-35859.jpg",
          "type": "",
          "id": "srn5s4aj",
          "status": "poolImages"
        },
        "variantImages": [],
        "variantWeight": "1",
        "variantDimW": "0",
        "variantDimL": "0",
        "variantDimH": "0",
        "variantUpc": "",
        "variantNumber": "NS-35859",
        "manufacturerPartNumber": "",
        "variantPrice": 0.3,
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
        "google_variantCategory": "",
        "google_variantType": "",
        "google_variantCondition": "",
        "taxable": 1,
        "variantAllowCheckout": 0,
        "variantCheckInvetory": 0,
        "variantTrackInventory": 0,
        "inventoryCount": -16,
        "shippingProduct": 1,
        "variantMetaTitle": "",
        "variantMetaDescription": "",
        "variantBrand": "",
        "sortOrder": 0,
        "dateCreated": "1669391499",
        "deleted": 0,
        "backOrderWarning": 0,
        "createdAt": "2022-12-18 23:01:04",
        "editedAt": "2024-06-19 10:07:50",
        "variantInStock": true,
        "prodName": "3\/4 IN. O.D. SATIN NICKEL DRIVE-IN, SPRING LOADED, BALL STYLE, CABINET DOOR LATCH WITH STRIKE\t",
        "prodImage": {
          "file": "11-25-2022\/1669391493868__30709__NS-35859.jpg",
          "type": ""
        }
      },
      "addOnProducts": [],
      "pricing": {
        "total": 0.3
      },
      "shipping": {
        "totalWeight": 1
      }
    }
  ],
  "BillToName": "Sarah Jones",
  "BillToAddress": "{\"name\":\"Sarah Jones\",\"zip\":\"10952\",\"address\":\"123 Main street\",\"address2\":\"Unit 4\",\"city\":\"NY\",\"state\":\"NY\",\"country\":\"\",\"phone\":\"03356705565\",\"mobile\":\"\"}",
  "orderShippingMethod": {
    "carrier": "freeshipping",
    "description": "",
    "deliveryDateTime": null,
    "deliveryDays": null,
    "origRate": 0,
    "rate": 0,
    "id": "CXadfoscekBHyxDQKGW9ORUv",
    "methodName": "Free Shipping"
  },
  "orderShippingAddress": {
    "address": "123 Main street",
    "address2": "Unit 4",
    "city": "NY",
    "state": "NY",
    "zip": "10952",
    "country": "",
    "phone": "03356705565",
    "mobile": "",
    "specialValues": []
  },
  "orderTotal": "0.15",
  "orderTax": "",
  "orderTotalPaid": "0.15",
  "orderShipping": "",
  "orderStatus": "os_awaiting_fulfillment",
  "paymentStatus": null,
  "fullfilmentStatus": null,
  "shippingStatus": null,
  "customerObject": {
    "customerFirstName": "Morris12",
    "customerLastName": "Altmann",
    "customerEmail": "cchris@chris.com",
    "customerPhone": "",
    "customerCompanyName": "",
    "source": "store",
    "customerStatus": "",
    "customerTypes": null,
    "customerGroups": null,
    "isLoggedIn": 1,
    "customerDocs": "",
    "taxExempt": null,
    "taxExemptID": null,
    "createdAt": "2024-05-16 11:11:53"
  },
  "orderWeight": 1,
  "contactFirstName": "Sarah",
  "contactLastName": "Jones",
  "orderEmail": "chris@chris.com",
  "orderNotePublic": "",
  "cartToken": "cart_Q0eM8x84bURo3tPUmm8fBKsH",
  "orderPaymentMethod": "{\"xResult\":\"A\",\"xStatus\":\"Approved\",\"xError\":\"\",\"xErrorCode\":\"00000\",\"xRefNum\":\"10032644615\",\"xExp\":\"0126\",\"xAuthCode\":\"xxxxxxx\",\"xBatch\":\"xxxxxxxx\",\"xAvsResultCode\":\"NNN\",\"xAvsResult\":\"Address: No Match & 5 Digit Zip: No Match\",\"xCvvResultCode\":\"\",\"xCvvResult\":\"No CVV data available\",\"xAuthAmount\":\"0.15\",\"xMaskedCardNumber\":\"4xxxxxxxxxxxxxxxx\",\"xCardType\":\"Visa\",\"xName\":\"Sarah Jones\",\"xToken\":\"xxxxxxxxxxxxxxxxxxxxxxxxxxx\",\"xMID\":\"xxxxxxxxxxxxxx\",\"xTID\":\"xxxxxxxxx\",\"xCurrency\":\"USD\",\"xDate\":\"6\\\/19\\\/2024 6:10:30 AM\",\"xEntryMethod\":\"Keyed\",\"cardToken\":\"cc_FJDJ7aboPYqH\"}",
  "checkoutObject": {
    "id": 31083,
    "cartToken": "cart_Q0eM8x84bURo3tPUmm8fBKsH",
    "customerToken": "cs_4JRbcroAdSipjf5XQf7dnSn9xuYgnGUiQloz",
    "couponCodes": [
      "ca"
    ],
    "addressToken": "adrs_CJO9LkwmNJqSQmOBtaTsGE1w",
    "shippingMethod": {
      "carrier": "freeshipping",
      "description": "",
      "deliveryDateTime": null,
      "deliveryDays": null,
      "origRate": 0,
      "rate": 0,
      "id": "CXadfoscekBHyxDQKGW9ORUv",
      "methodName": "Free Shipping"
    },
    "shippingMethodId": "CXadfoscekBHyxDQKGW9ORUv",
    "shippingAddressLabel": "",
    "shippingAddress": {
      "address": "123 Main street",
      "address2": "Unit 4",
      "city": "NY",
      "state": "NY",
      "zip": "10952",
      "country": "",
      "phone": "03356705565",
      "mobile": "",
      "specialValues": []
    },
    "contactEmail": "chris@chris.com",
    "contactPhone": "",
    "shippingMethodsJson": [
      {
        "carrier": "freeshipping",
        "description": "",
        "deliveryDateTime": null,
        "deliveryDays": null,
        "origRate": 0,
        "rate": 0,
        "id": "CXadfoscekBHyxDQKGW9ORUv",
        "methodName": "Free Shipping"
      }
    ],
    "contactFirstName": "Sarah",
    "contactLastName": "Jones",
    "companyName": "",
    "createdAt": "2024-06-19 10:05:01",
    "editedAt": "2024-06-19 10:10:30",
    "pricing": {
      "productsTotal": 0.3,
      "origTotal": 0.3,
      "subTotal": 0.3,
      "totalCouponDiscount": 0.15,
      "totalAfterCoupon": 0.15,
      "shipping": 0,
      "tax": 0,
      "total": 0.15
    },
    "couponCodesInfo": [
      {
        "name": "ca",
        "msg": "Successfully applied",
        "discountAmount": 0.15,
        "status": "valid"
      }
    ]
  },
  "orderProdQuantity": "1",
  "paymentObject": {
    "xResult": "A",
    "xStatus": "Approved",
    "xError": "",
    "xErrorCode": "00000",
    "xRefNum": "10032644615",
    "xExp": "0126",
    "xAuthCode": "53783A",
    "xBatch": "5150840",
    "xAvsResultCode": "NNN",
    "xAvsResult": "Address: No Match & 5 Digit Zip: No Match",
    "xCvvResultCode": "",
    "xCvvResult": "No CVV data available",
    "xAuthAmount": "0.15",
    "xMaskedCardNumber": "4xxxxxxxxxxxxxxx",
    "xCardType": "Visa",
    "xName": "Sarah Jones",
    "xToken": "xxxxxxxxxxxxxxxxxxxxxxxxx",
    "xMID": "xxxxxxxxxxxxxxxxxx",
    "xTID": "xxxxxxxxx",
    "xCurrency": "USD",
    "xDate": "6\/19\/2024 6:10:30 AM",
    "xEntryMethod": "Keyed",
    "cardToken": "cc_xxxxxxxxxxxxxxx"
  },
  "cardToken": "cc_xxxxxxxxxxxxxx",
  "orderIP": "86.132.15.37",
  "dateCreated": "1718791832",
  "deleted": "",
  "numberOfPackages": 0,
  "createdAt": "2024-06-19 10:10:32",
  "editedAt": "2024-06-19 10:10:32",
  "orderStatusValue": {
    "id": "os_awaiting_fulfillment",
    "name": "Awaiting Fulfillment",
    "color": "#ffc107"
  },
  "statusAndTerms": {
    "processingStatus": "Processing",
    "shippingStatus": "Pending",
    "paymentStatus": "Closed",
    "orderStatus": "Open",
    "paymentTerms": "Website Payment Transaction",
    "postPaymentStatus": " NULL"
  },
  "paymentHistory": [
    {
      "paymentHistoryToken": "pmth_nTjBOQKah8UuXCJKtBo0MzaLthnOREzS8pgR",
      "orderToken": "ordr_4xCT42nj1QKZjSVbPvj6XE1X",
      "amount": 0.15,
      "action": "charge",
      "transactionType": null,
      "transactionDetails": null,
      "dateTime": "1718791832",
      "paymentObject": "{\"xResult\":\"A\",\"xStatus\":\"Approved\",\"xError\":\"\",\"xErrorCode\":\"00000\",\"xRefNum\":\"10032644615\",\"xExp\":\"0126\",\"xAuthCode\":\"53783A\",\"xBatch\":\"5150840\",\"xAvsResultCode\":\"NNN\",\"xAvsResult\":\"Address: No Match & 5 Digit Zip: No Match\",\"xCvvResultCode\":\"\",\"xCvvResult\":\"No CVV data available\",\"xAuthAmount\":\"0.15\",\"xMaskedCardNumber\":\"4xxxxxxxxxxx2438\",\"xCardType\":\"Visa\",\"xName\":\"Sarah Jones\",\"xToken\":\"3hnqh1559n21007288643251pn17h5m4\",\"xMID\":\"xxxxxxxxxx9999\",\"xTID\":\"xxxxx6789\",\"xCurrency\":\"USD\",\"xDate\":\"6\\\/19\\\/2024 6:10:30 AM\",\"xEntryMethod\":\"Keyed\",\"cardToken\":\"cc_FJDJ7aboPYqH\"}",
      "cardToken": "cc_xxxxxxxxxxxxxxxx",
      "void": 0,
      "userToken": "omni",
      "createdAt": "2024-06-19 10:10:32",
      "editedAt": "2024-06-19 10:10:32"
    }
  ]
}
```
