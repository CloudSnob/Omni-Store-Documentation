# Checkout

## Checkout Step 1 (email,address)
This endpoint adds the email and address information for part one of checkout. 
It returns the available shipping options for the data submitted

### HTTP Request
`POST https://storeapi.csomni.com/checkout/info`

### Header Parameters
| Parameter     | Required | Type   | Description      |
|---------------|----------|--------|------------------|
| customerToken | true     | string | Customer Token   |
| siteToken     | true     | string | Unique siteToken |


### Data Parameters
| Parameter        | Required | Type   | Unique | Description                       |
|------------------|----------|--------|--------|-----------------------------------|
| addressToken     | true     | string | -      | Customer Address refference token |
| contactEmail     | true     | string |        | Customer Email                    |
| contactPhone     | true     | string |        | Customer Phone                    |
| contactFirstName | false    | string | false  | Customer First Name               |
| contactLastName  | false    | string | false  | Customer Last Name                |
| companyName      | false    | string | false  | Customer Company Name             |

Sample in Shell:

```shell
curl --request POST \
  --url https://storeapi.csomni.com/checkout/info \
  --header 'token: site_xxxxxxxxxxx' \
  --header 'customerToken: cs_3C04TQd6OSkDNFa90UyYAUaD1Lq8NcQbHjQi' \
  --data '{
        "contactEmail" : "123456@test.com",
        "addressToken" : "adrs_hzle2kYXjQg1LGnPGtLwMs9m",
        "contactFirstName": "Sarah",
        "contactLastName": "Jones"
        }'

```

> The above command returns JSON structured like this

```json
{
  "id": 31109,
  "cartToken": "cart_kf4bA6ljiCf7RhWTnXDwq8On",
  "customerToken": "cs_3C04TQd6OSkDNFa90UyYAUaD1Lq8NcQbHjQi",
  "couponCodes": null,
  "addressToken": "adrs_hzle2kYXjQg1LGnPGtLwMs9m",
  "shippingMethod": "",
  "shippingMethodId": "",
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
  "contactEmail": "sharonjones@gmail.com",
  "contactPhone": "",
  "shippingMethodsJson": [
    {
      "carrier": "freeshipping",
      "description": "",
      "deliveryDateTime": null,
      "deliveryDays": null,
      "origRate": 0,
      "rate": 0,
      "id": "UO2S3uFr49zCBJGAZMRYanqh",
      "methodName": "Free Shipping"
    },
    {
      "carrier": "storepickup",
      "description": "",
      "deliveryDateTime": null,
      "deliveryDays": null,
      "origRate": 0,
      "rate": 0,
      "id": "KHC4UAucyBEnwTjOWFxPMGr7",
      "methodName": "Store Pickup"
    },
    {
      "carrier": "",
      "origRate": 0,
      "rate": 50,
      "id": "FDQxZnVyNYK8UiOsSlIX7dAm",
      "methodName": ""
    }
  ],
  "contactFirstName": "Sarah",
  "contactLastName": "Jones",
  "companyName": "",
  "createdAt": "2024-06-27 10:33:43",
  "editedAt": "2024-06-27 10:33:45",
  "pricing": {
    "productsTotal": 0.1,
    "origTotal": 0.1,
    "subTotal": 0.1,
    "totalCouponDiscount": 0,
    "totalAfterCoupon": 0.1,
    "shipping": 0,
    "tax": 0,
    "total": 0.1
  },
  "couponCodesInfo": []
}
```

## Checkout Step 2 - Choose shipping method
This API submits the chosen shipping method. The shipping method Id's are returned in the previous API call - Checkout Step 1, and returns the new total including any shipping charge

### HTTP Request
`POST https://storeapi.csomni.com/checkout/info`

### Header Parameters
| Parameter     | Required | Type   | Description      |
|---------------|----------|--------|------------------|
| customerToken | true     | string | Customer Token   |
| siteToken     | true     | string | Unique siteToken |

### Data Parameters

| Parameter        | Type   | Type   | Required | Description        |
|------------------|--------|--------|----------|--------------------|
| shippingMethodId | string | string | true     | Shipping method Id |

Sample in Shell:

```shell
curl --request POST \
  --url https://storeapi.csomni.com/checkout/shippingmethod \
  --header 'token: site_xxxxxxxxx' \
  -- header 'customerToken: cs_3C04TQd6OSkDNFa90UyYAUaD1Lq8NcQbHjQi' \
  --data '{
            "shippingMethodId" : "UO2S3uFr49zCBJGAZMRYanqh"
          }'

```

> The above command returns JSON structured like this

```json
{
  "id": 31109,
  "cartToken": "cart_kf4bA6ljiCf7RhWTnXDwq8On",
  "customerToken": "cs_3C04TQd6OSkDNFa90UyYAUaD1Lq8NcQbHjQi",
  "couponCodes": null,
  "addressToken": "adrs_hzle2kYXjQg1LGnPGtLwMs9m",
  "shippingMethod": {
    "carrier": "freeshipping",
    "description": "",
    "deliveryDateTime": null,
    "deliveryDays": null,
    "origRate": 0,
    "rate": 0,
    "id": "UO2S3uFr49zCBJGAZMRYanqh",
    "methodName": "Free Shipping"
  },
  "shippingMethodId": "UO2S3uFr49zCBJGAZMRYanqh",
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
  "contactEmail": "sharondoe@gmail.com",
  "contactPhone": "",
  "shippingMethodsJson": [
    {
      "carrier": "freeshipping",
      "description": "",
      "deliveryDateTime": null,
      "deliveryDays": null,
      "origRate": 0,
      "rate": 0,
      "id": "UO2S3uFr49zCBJGAZMRYanqh",
      "methodName": "Free Shipping"
    }
  ],
  "contactFirstName": "Sarah",
  "contactLastName": "Jones",
  "companyName": "",
  "createdAt": "2024-06-27 10:33:43",
  "editedAt": "2024-06-27 10:35:01",
  "pricing": {
    "productsTotal": 0.1,
    "origTotal": 0.1,
    "subTotal": 0.1,
    "totalCouponDiscount": 0,
    "totalAfterCoupon": 0.1,
    "shipping": 0,
    "tax": 0,
    "total": 0.1
  },
  "couponCodesInfo": []
}
```

## Checkout Step 3: OPTION 1: Pay NOW

This endpoint processes payment for a cart and creates an order. 
The data is expected to include all the card details, or reference a cardToken that has already been saved for this customer

### HTTP Request
`POST https://storeapi.csomni.com/checkout/payment`

### Data Parameters - to pay with a new card
| Parameter           | Required | Type   | Unique | Description                                                                                                                                                                                              |
|---------------------|----------|--------|--------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| expMonth            | true     | string | false  | Card Exp Month                                                                                                                                                                                           |
| expYear             | true     | string | false  | Card Exp Year                                                                                                                                                                                            |
| cvv                 | true     | string | false  | Card CVV                                                                                                                                                                                                 |
| billingAddressLine2 | false    | string | false  | Billing Address Line 2                                                                                                                                                                                   |
| billingZip          | false    | string | false  | Billing Address Zip                                                                                                                                                                                      |
| billingAddress      | false    | string | false  | Billing Address                                                                                                                                                                                          |
| billingCity         | false    | string | false  | Billing Address City                                                                                                                                                                                     |
| billingState        | false    | string | false  | Billing Address State                                                                                                                                                                                    |
| billingName         | false    | string | false  | Billing Address Name                                                                                                                                                                                     |
| billingPhone        | false    | string | false  | Billing Phone Number                                                                                                                                                                                     |
| billingMobile       | false    | string | false  | Billing Mobile Number                                                                                                                                                                                    |
| billingCountry      | false    | string | false  | Billing Address Country                                                                                                                                                                                  |
| sameAsShipping      | true     | bool   | false  | Sets billing address to same as shipping even if cardToken is provided (see above)                                                                                                                       |
| billingAddressToken | false    | string | false  | Billing Address Token                                                                                                                                                                                    |
| PO                  | false    | string | false  | Customer facing Purchase Order Number. Can include digits, letters (which will be converted to upper case), dashes and dots. All other characters will not be processed and will return an error message |
| orderNotePublic     | false    | string | false  | Order Note submitted by the customer which will be visible to the customer                                                                                                                               |

Sample in Shell:

```shell
curl --request POST \
  --url https://storeapi.csomni.com/checkout/payment \
  --header 'token: site_xxxxxxxxxxx' \
  --data '{
            "cardNumbers" : "1234567890789654321", 
            "expMonth" : "12", 
            "expYear" : "2025", 
            "cvv" : "123", 
            "po" : "PO-123456", 
            "nameOnCard": "Mr Frances Chiwa", 
            "billingPhone": "8455225252",
            "billingAddress": "25 Apple Tree Ave",
            "billingCity": "Bala Cynwyd", 
            "billingState": "Pennsylvania", 
            "billingZip": "19004", 
            "orderNotePublic" :"" 
          }'

```
### Query Parameters - to pay with a saved card

| Parameter       | Required | Type   | Unique | Description                                                                                                                                                                                              |
|-----------------|----------|--------|--------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| cardToken       | true     | string | true   | Saved card reference token                                                                                                                                                                               |
| sameAsShipping  | false    | bool   | false  | The default billing address is taken from the shipping address. To use the cards saved billing address, set this property to 'false'                                                                     |
| PO              | false    | string | false  | Customer facing Purchase Order Number. Can include digits, letters (which will be converted to upper case), dashes and dots. All other characters will not be processed and will return an error message |
| orderNotePublic | false    | string | false  | Order Note submitted by the customer which will be visible to the customer                                                                                                                               |

Sample in Shell:
|
```shell
curl --request POST \
  --url https://storeapi.csomni.com/checkout/payment \
  --header 'token: site_xxxxxxxxxx' \
  --data '{
            "cardToken" : "cc_xxxxxxxxxxxxxx"
            "po" : "PO-123456", 
            "sameAsShipping" : "false",
            "orderNotePublic" :"this is a note submitted by the customer at payment" 
          }'

```

> The above command returns JSON structured like this
```json
{
  "status": "success",
  "order": {
    "orderProducts": [
      {
        "cartToken": "cart_0dlVuUpVQEuRbkB92eMseToh",
        "cartProdToken": "cp_4T8dqlwPUN25Gu75Fp8CLptY",
        "cartProdQuantity": 1,
        "addOnToProdToken": "",
        "addOnProdTokens": null,
        "prodToken": "vrnt_EvonkJQsR6fRbDtm",
        "deleted": 0,
        "createdAt": "2024-06-19 10:15:14",
        "editedAt": "2024-06-19 10:15:14",
        "siteToken": "site_63Vdsmr9Qsq0",
        "customerToken": "cs_GWdE9xY2dcL9qqBmNKx7WXivTh73nJtGH4NK",
        "cartCreated": "1718792114",
        "cartLastTouched": "1718792114",
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
          "inventoryCount": -17,
          "shippingProduct": 1,
          "variantMetaTitle": "",
          "variantMetaDescription": "",
          "variantBrand": "",
          "sortOrder": 0,
          "dateCreated": "1669391499",
          "deleted": 0,
          "backOrderWarning": 0,
          "createdAt": "2022-12-18 23:01:04",
          "editedAt": "2024-06-19 10:10:30",
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
      },
      {
        "cartToken": "cart_0dlVuUpVQEuRbkB92eMseToh",
        "cartProdToken": "cp_tvZnIK2TOyuJPhGL5YD6q1Iw",
        "cartProdQuantity": 1,
        "addOnToProdToken": "",
        "addOnProdTokens": null,
        "prodToken": "vrnt_k2BdGbMqyFoopAhO",
        "deleted": 0,
        "createdAt": "2024-06-19 10:15:14",
        "editedAt": "2024-06-19 10:15:14",
        "siteToken": "site_63Vdsmr9Qsq0",
        "customerToken": "cs_GWdE9xY2dcL9qqBmNKx7WXivTh73nJtGH4NK",
        "cartCreated": "1718792114",
        "cartLastTouched": "1718792114",
        "prodStaticCollections": [],
        "specialValues": [],
        "product": {
          "prodToken": "prod_4398Buqqstztncng",
          "variantToken": "vrnt_k2BdGbMqyFoopAhO",
          "variantName": "interface",
          "variantImage": [],
          "variantImages": [],
          "variantWeight": "1",
          "variantDimW": null,
          "variantDimL": null,
          "variantDimH": null,
          "variantUpc": null,
          "variantNumber": "JSON 5",
          "manufacturerPartNumber": null,
          "variantPrice": 0.1,
          "variantMapPrice": null,
          "variantMsrpPrice": null,
          "variantDisplayPrice": null,
          "variantDescription": null,
          "variantAlert": null,
          "variantLowlevel": null,
          "variantSlug": null,
          "variantVisible": 1,
          "taxType": null,
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
          "variantMetaTitle": null,
          "variantMetaDescription": null,
          "variantBrand": null,
          "sortOrder": 2,
          "dateCreated": "1717576258",
          "deleted": 0,
          "backOrderWarning": 0,
          "createdAt": "2024-06-05 08:30:58",
          "editedAt": "2024-06-26 09:49:53",
          "variantInStock": true,
          "prodName": "Generic Plastic SoapBike",
          "prodImage": {
            "file": ""
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
    "orderEmail": "sara@jones.com",
    "orderShippingMethod": "{\"carrier\":\"freeshipping\",\"description\":\"\",\"deliveryDateTime\":null,\"deliveryDays\":null,\"origRate\":0,\"rate\":0,\"id\":\"RlV1xCXpAr3SBaMwcZd9j5FQ\",\"methodName\":\"Free Shipping\"}",
    "orderTotal": 0.41,
    "orderTax": 0.01,
    "orderTotalPaid": "0.41",
    "orderShipping": 0,
    "orderWeight": 2,
    "orderShippingAddress": "{\"address\":\"123 Main street\",\"address2\":\"Unit 4\",\"city\":\"NY\",\"state\":\"NY\",\"zip\":\"10952\",\"country\":\"\",\"phone\":\"03356705565\",\"mobile\":\"\",\"specialValues\":[]}",
    "orderPaymentMethod": {
      "xResult": "A",
      "xStatus": "Approved",
      "xError": "",
      "xErrorCode": "00000",
      "xRefNum": "10038240703",
      "xExp": "xxxx",
      "xAuthCode": "xxxxxxxxxx",
      "xBatch": "xxxxxxxxxxxxxx",
      "xAvsResultCode": "NNN",
      "xAvsResult": "Address: No Match & 5 Digit Zip: No Match",
      "xCvvResultCode": "",
      "xCvvResult": "No CVV data available",
      "xAuthAmount": "0.41",
      "xMaskedCardNumber": "4xxxxxxxxxxx1234",
      "xCardType": "Visa",
      "xName": "Sarah Jones",
      "xToken": "xxxxxxxxxxxxxxxxxxxxxxx",
      "xMID": "xxxxxxxxxx1234",
      "xTID": "xxxxx7894",
      "xCurrency": "USD",
      "xDate": "6\/26\/2024 6:07:43 AM",
      "xEntryMethod": "Keyed",
      "cardToken": "cc_xxxxxxxxxxxxx"
    },
    "contactLastName": "Jones",
    "contactFirstName": "Sarah",
    "orderProdQuantity": 2,
    "paymentObject": "{\"xResult\":\"A\",\"xStatus\":\"Approved\",\"xError\":\"\",\"xErrorCode\":\"00000\",\"xRefNum\":\"10038240703\",\"xExp\":\"0126\",\"xAuthCode\":\"xxxxxxxx\",\"xBatch\":\"xxxxxx\",\"xAvsResultCode\":\"NNN\",\"xAvsResult\":\"Address: No Match & 5 Digit Zip: No Match\",\"xCvvResultCode\":\"\",\"xCvvResult\":\"No CVV data available\",\"xAuthAmount\":\"0.41\",\"xMaskedCardNumber\":\"4xxxxxxxxxxx1234\",\"xCardType\":\"Visa\",\"xName\":\"Sarah Jones\",\"xToken\":\"xxxxxxxxxxxxxxxxxxxxxxxxxxxx\",\"xMID\":\"xxxxxxxxxx9999\",\"xTID\":\"xxxxx4567\",\"xCurrency\":\"USD\",\"xDate\":\"6\\\/26\\\/2024 6:07:43 AM\",\"xEntryMethod\":\"Keyed\",\"cardToken\":\"cc_xxxxxxxxxxxx\"}",
    "cardToken": "cc_xxxxxxxxxxxx",
    "orderIP": "00.000.000.00",
    "cartToken": "cart_0dlVuUpVQEuRbkB92eMseToh",
    "PO": "123-245jk",
    "BillToName": "Sarah Jones",
    "BillToAddress": "{\"name\":\"Sarah Jones\",\"address\":\"123 Main street\",\"address2\":\"Unit 4\",\"zip\":\"10952\",\"city\":\"NY\",\"state\":\"NY\",\"country\":\"\",\"mobile\":\"\",\"phone\":\"03356705565\"}",
    "orderNotePublic": "",
    "quoteToken": "",
    "siteToken": "site_63Vdsmr9Qsq0",
    "customerToken": "cs_GWdE9xY2dcL9qqBmNKx7WXivTh73nJtGH4NK",
    "orderToken": "ordr_VOnbeilit2gwfSyTb05Vattf",
    "orderNumber": 100000492,
    "orderStatus": "os_awaiting_fulfillment",
    "checkoutObject": "{\"id\":31085,\"cartToken\":\"cart_0dlVuUpVQEuRbkB92eMseToh\",\"customerToken\":\"cs_GWdE9xY2dcL9qqBmNKx7WXivTh73nJtGH4NK\",\"couponCodes\":[],\"addressToken\":\"adrs_CJO9LkwmNJqSQmOBtaTsGE1w\",\"shippingMethod\":{\"carrier\":\"freeshipping\",\"description\":\"\",\"deliveryDateTime\":null,\"deliveryDays\":null,\"origRate\":0,\"rate\":0,\"id\":\"RlV1xCXpAr3SBaMwcZd9j5FQ\",\"methodName\":\"Free Shipping\"},\"shippingMethodId\":\"RlV1xCXpAr3SBaMwcZd9j5FQ\",\"shippingAddressLabel\":\"\",\"shippingAddress\":{\"address\":\"123 Main street\",\"address2\":\"Unit 4\",\"city\":\"NY\",\"state\":\"NY\",\"zip\":\"10952\",\"country\":\"\",\"phone\":\"03356705565\",\"mobile\":\"\",\"specialValues\":[]},\"contactEmail\":\"sarahjones@gmail.com\",\"contactPhone\":\"\",\"shippingMethodsJson\":[{\"carrier\":\"freeshipping\",\"description\":\"\",\"deliveryDateTime\":null,\"deliveryDays\":null,\"origRate\":0,\"rate\":0,\"id\":\"RlV1xCXpAr3SBaMwcZd9j5FQ\",\"methodName\":\"Free Shipping\"}],\"contactFirstName\":\"Sarah\",\"contactLastName\":\"Jones\",\"companyName\":\"\",\"createdAt\":\"2024-06-19 10:15:21\",\"editedAt\":\"2024-06-26 10:05:36\",\"pricing\":{\"productsTotal\":0.4,\"origTotal\":0.4,\"subTotal\":0.4,\"totalCouponDiscount\":0,\"totalAfterCoupon\":0.4,\"shipping\":0,\"tax\":0.01,\"total\":0.41},\"couponCodesInfo\":[]}",
    "customerObject": "{\"customerFirstName\":\"Sarah\",\"customerLastName\":\"Jones\",\"customerEmail\":\"sarah@jones.com\",\"customerPhone\":\"\",\"customerCompanyName\":\"\",\"source\":\"store\",\"customerStatus\":\"\",\"customerTypes\":null,\"customerGroups\":null,\"isLoggedIn\":1,\"customerDocs\":\"\",\"taxExempt\":null,\"taxExemptID\":null,\"createdAt\":\"2024-05-16 11:11:53\"}",
    "dateCreated": 1719396465,
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



## Checkout Step 3 OPTION 2: Pay Later - Process as a PO
Enable PO module through company settings.
This endpoint processes an order without payment. 

### HTTP Request
`POST https://storeapi.csomni.com/checkout/po`

### Header Parameters
| Parameter     | Required | Type   | Description       |
|---------------|----------|--------|-------------------|
| customerToken | true     | string | Customer Token    |
| siteToken     | true     | string | Unique siteToken  |

### Data Parameters
| Parameter           | Required | Type   | Unique | Description                                                                                                                                                                                              |
|---------------------|----------|--------|--------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| PO                  | false    | string | false  | Customer facing Purchase Order Number. Can include digits, letters (which will be converted to upper case), dashes and dots. All other characters will not be processed and will return an error message |
| billingName         | true     | string | false  | Billing Address Name                                                                                                                                                                                     |
| billingAddress      | true     | string | false  | Billing Address                                                                                                                                                                                          |
| billingAddressLine2 | false    | string | false  | Billing Address Line 2                                                                                                                                                                                   |
| billingCity         | true     | string | false  | Billing Address City                                                                                                                                                                                     |
| billingState        | true     | string | false  | Billing Address State                                                                                                                                                                                    |
| billingZip          | true     | string | false  | Billing Address Zip                                                                                                                                                                                      |
| billingCountry      | true     | string | false  | Billing Address Country                                                                                                                                                                                  |
| billingMobile       | false    | string | false  | Billing Mobile Number                                                                                                                                                                                    |
| billingPhone        | true     | string | false  | Billing Phone Number                                                                                                                                                                                     |
| orderNotePublic     | false    | string | false  | Order Note submitted by the customer which will be visible to the customer                                                                                                                               |

Sample in Shell:

```shell
curl --request POST \
  --url https://storeapi.csomni.com/checkout/po \
  --header 'token: site_xxxxxxxxx' \
  --header 'customerToken: cs_3C04TQd6OSkDNFa90UyYAUaD1Lq8NcQbHjQi' \
  --header '{
               "po": "123-P9ojd",
               "billingName": "431 Systems LLC",
                "billingAddress": "10 Eros Drive",
                "billingCity": "Airmont",
                "billingState": "NY",
                "billingZip": "10952",
                "billingCountry": "United States",
                "billingPhone": "000000",
                "orderNotePublic": ""
            }'
```

> The above command returns JSON structured like this

```json
{
  "status": "success",
  "order": {
    "orderProducts": [
      {
        "cartToken": "cart_FT583q6GuFBGwC2whG0mnaKF",
        "cartProdToken": "cp_bTLWzL9aPPGKVqMF96hSAiUG",
        "cartProdQuantity": 1,
        "addOnToProdToken": "",
        "addOnProdTokens": null,
        "prodToken": "vrnt_k2BdGbMqyFoopAhO",
        "deleted": 0,
        "createdAt": "2024-06-26 10:12:15",
        "editedAt": "2024-06-26 10:12:15",
        "siteToken": "site_63Vdsmr9Qsq0",
        "customerToken": "cs_3C04TQd6OSkDNFa90UyYAUaD1Lq8NcQbHjQi",
        "cartCreated": "1719396735",
        "cartLastTouched": "1719396735",
        "prodStaticCollections": [],
        "specialValues": [],
        "product": {
          "prodToken": "prod_4398Buqqstztncng",
          "variantToken": "vrnt_k2BdGbMqyFoopAhO",
          "variantName": "interface",
          "variantImage": [],
          "variantImages": [],
          "variantWeight": "1",
          "variantDimW": null,
          "variantDimL": null,
          "variantDimH": null,
          "variantUpc": null,
          "variantNumber": "JSON 5",
          "manufacturerPartNumber": null,
          "variantPrice": 0.1,
          "variantMapPrice": null,
          "variantMsrpPrice": null,
          "variantDisplayPrice": null,
          "variantDescription": null,
          "variantAlert": null,
          "variantLowlevel": null,
          "variantSlug": null,
          "variantVisible": 1,
          "taxType": null,
          "hideGoogleData": 0,
          "google_variantCategory": null,
          "google_variantType": null,
          "google_variantCondition": null,
          "taxable": 1,
          "variantAllowCheckout": 0,
          "variantCheckInvetory": 0,
          "variantTrackInventory": 0,
          "inventoryCount": 83,
          "shippingProduct": 0,
          "variantMetaTitle": null,
          "variantMetaDescription": null,
          "variantBrand": null,
          "sortOrder": 2,
          "dateCreated": "1717576258",
          "deleted": 0,
          "backOrderWarning": 0,
          "createdAt": "2024-06-05 08:30:58",
          "editedAt": "2024-06-26 10:07:43",
          "variantInStock": true,
          "prodName": "Generic Plastic SoapBike",
          "prodImage": {
            "file": ""
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
    "orderEmail": "sarahjones@gmail.com",
    "orderShippingMethod": "{\"carrier\":\"freeshipping\",\"description\":\"\",\"deliveryDateTime\":null,\"deliveryDays\":null,\"origRate\":0,\"rate\":0,\"id\":\"itqDLvaPN5JM3cBA7zOfbCxn\",\"methodName\":\"Free Shipping\"}",
    "orderTotal": 0.1,
    "orderTotalPaid": 0,
    "orderTax": 0,
    "orderShipping": 0,
    "orderWeight": 1,
    "orderShippingAddress": "{\"address\":\"123 Main street\",\"address2\":\"Unit 4\",\"city\":\"NY\",\"state\":\"NY\",\"zip\":\"10952\",\"country\":\"\",\"phone\":\"03356705565\",\"mobile\":\"\",\"specialValues\":[]}",
    "orderPaymentMethod": null,
    "contactLastName": "Jones",
    "contactFirstName": "Sarah",
    "orderProdQuantity": 1,
    "paymentObject": null,
    "cardToken": null,
    "orderIP": "81.151.213.25",
    "cartToken": "cart_FT583q6GuFBGwC2whG0mnaKF",
    "PO": "123-P9ojd",
    "BillToName": "Sarah Jones",
    "BillToAddress": "{\"name\":\"Sarah Jones\",\"address\":\"123 Main street\",\"address2\":\"Unit 4\",\"zip\":\"10952\",\"city\":\"NY\",\"state\":\"NY\",\"country\":\"\",\"mobile\":\"\",\"phone\":\"03356705565\"}",
    "orderNotePublic": "order processed through PO pathway",
    "quoteToken": "",
    "siteToken": "site_63Vdsmr9Qsq0",
    "customerToken": "cs_GWdE9xY2dcL9qqBmNKx7WXivTh73nJtGH4NK",
    "orderToken": "ordr_BZoD7Y38awuVg5wnzBxBnbrz",
    "orderNumber": 100000493,
    "orderStatus": "os_awaiting_fulfillment",
    "checkoutObject": "{\"id\":31107,\"cartToken\":\"cart_FT583q6GuFBGwC2whG0mnaKF\",\"customerToken\":\"cs_GWdE9xY2dcL9qqBmNKx7WXivTh73nJtGH4NK\",\"couponCodes\":null,\"addressToken\":\"adrs_CJO9LkwmNJqSQmOBtaTsGE1w\",\"shippingMethod\":{\"carrier\":\"freeshipping\",\"description\":\"\",\"deliveryDateTime\":null,\"deliveryDays\":null,\"origRate\":0,\"rate\":0,\"id\":\"itqDLvaPN5JM3cBA7zOfbCxn\",\"methodName\":\"Free Shipping\"},\"shippingMethodId\":\"itqDLvaPN5JM3cBA7zOfbCxn\",\"shippingAddressLabel\":\"\",\"shippingAddress\":{\"address\":\"123 Main street\",\"address2\":\"Unit 4\",\"city\":\"NY\",\"state\":\"NY\",\"zip\":\"10952\",\"country\":\"\",\"phone\":\"03356705565\",\"mobile\":\"\",\"specialValues\":[]},\"contactEmail\":\"sarahjones@gmail.com\",\"contactPhone\":\"\",\"shippingMethodsJson\":[{\"carrier\":\"freeshipping\",\"description\":\"\",\"deliveryDateTime\":null,\"deliveryDays\":null,\"origRate\":0,\"rate\":0,\"id\":\"itqDLvaPN5JM3cBA7zOfbCxn\",\"methodName\":\"Free Shipping\"}],\"contactFirstName\":\"Sarah\",\"contactLastName\":\"Jones\",\"companyName\":\"\",\"createdAt\":\"2024-06-26 10:12:21\",\"editedAt\":\"2024-06-26 10:12:28\",\"pricing\":{\"productsTotal\":0.1,\"origTotal\":0.1,\"subTotal\":0.1,\"totalCouponDiscount\":0,\"totalAfterCoupon\":0.1,\"shipping\":0,\"tax\":0,\"total\":0.1},\"couponCodesInfo\":[]}",
    "customerObject": "{\"customerFirstName\":\"Sharon\",\"customerLastName\":\"Dolar\",\"customerEmail\":\"sharondollar@gmail.com\",\"customerPhone\":\"\",\"customerCompanyName\":\"\",\"source\":\"store\",\"customerStatus\":\"\",\"customerTypes\":null,\"customerGroups\":null,\"isLoggedIn\":1,\"customerDocs\":\"\",\"taxExempt\":null,\"taxExemptID\":null,\"createdAt\":\"2024-05-16 11:11:53\"}",
    "dateCreated": 1719396754,
    "statusTermsData": {
      "processingStatus": "Processing",
      "shippingStatus": "Pending",
      "paymentStatus": "Open",
      "orderStatus": "Open",
      "paymentTerms": "Purchase Order",
      "postPaymentStatus": " NULL"
    }
  }
}
```

## Checkout Apply Coupon
This endpoint applies a coupon code to a cart

### HTTP Request

`POST https://storeapi.csomni.com/checkout/applycoupon`

### Header Parameters
| Parameter     | Required | Type   | Description       |
|---------------|----------|--------|-------------------|
| customerToken | true     | string | Customer Token    |
| siteToken     | true     | string | Unique siteToken  |

### Data Parameters
| Parameter  | Required | Type   | Description                  |
|------------|----------|--------|------------------------------|
| couponCode | true     | string | Name of coupon to be applied |

Sample in Shell:

```shell
curl --request POST \
  --url https://storeapi.csomni.com/checkout/applycoupon \
  --header 'token: site_xxxxxxxxxxxxx' \
  --header 'customerToken: cs_3C04TQd6OSkDNFa90UyYAUaD1Lq8NcQbHjQi' \
  --data '{"couponCode" : "SUMMER20"}'

```

> The above command returns JSON structured like this:
> Note: The address properties (addressToken, shippingAddress object, and shippingMethodsJson)  will only have a value if the coupon call is made for a cart with shipping/address details.
> If address details are not known, the address related properties will return as an empty string.

```json
{
  "id": 31109,
  "cartToken": "cart_kf4bA6ljiCf7RhWTnXDwq8On",
  "customerToken": "cs_3C04TQd6OSkDNFa90UyYAUaD1Lq8NcQbHjQi",
  "couponCodes": [
    "ca"
  ],
  "addressToken": "adrs_hzle2kYXjQg1LGnPGtLwMs9m",
  "shippingMethod": {
    "carrier": "freeshipping",
    "description": "",
    "deliveryDateTime": null,
    "deliveryDays": null,
    "origRate": 0,
    "rate": 0,
    "id": "UO2S3uFr49zCBJGAZMRYanqh",
    "methodName": "Free Shipping"
  },
  "shippingMethodId": "UO2S3uFr49zCBJGAZMRYanqh",
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
  "contactEmail": "sharondoe@gmail.com",
  "contactPhone": "",
  "shippingMethodsJson": [
    {
      "carrier": "freeshipping",
      "description": "",
      "deliveryDateTime": null,
      "deliveryDays": null,
      "origRate": 0,
      "rate": 0,
      "id": "UO2S3uFr49zCBJGAZMRYanqh",
      "methodName": "Free Shipping"
    }
  ],
  "contactFirstName": "Sarah",
  "contactLastName": "Jones",
  "companyName": "",
  "createdAt": "2024-06-27 10:33:43",
  "editedAt": "2024-06-27 10:38:31",
  "pricing": {
    "productsTotal": 0.1,
    "origTotal": 0.1,
    "subTotal": 0.1,
    "totalCouponDiscount": 0.05,
    "totalAfterCoupon": 0.05,
    "shipping": 0,
    "tax": 0,
    "total": 0.05
  },
  "couponCodesInfo": [
    {
      "name": "ca",
      "msg": "Successfully applied",
      "discountAmount": 0.05,
      "status": "valid"
    }
  ],
  "couponCodeInfo": []
}
```



## Checkout Remove Coupon
This endpoint removes a coupon from a cart

### HTTP Request
`POST https://storeapi.csomni.com/checkout/removecoupon`

### Header Parameters
| Parameter     | Required | Type   | Description       |
|---------------|----------|--------|-------------------|
| customerToken | true     | string | Customer Token    |
| siteToken     | true     | string | Unique siteToken  |

### Data Parameters
| Parameter  | Required | Type   | Description                  |
|------------|----------|--------|------------------------------|
| couponCode | true     | string | Name of coupon to be removed |

Sample in Shell:

```shell
curl --request POST \
  --url https://storeapi.csomni.com/checkout/removecoupon \
  --header 'token: site_xxxxxxxxx' \
  --header 'customerToken: cs_3C04TQd6OSkDNFa90UyYAUaD1Lq8NcQbHjQi' \
  --data '{"couponCode" : "SUMMER20"}'

```

> The above command returns JSON structured like this

```json
{
  "id": 31109,
  "cartToken": "cart_kf4bA6ljiCf7RhWTnXDwq8On",
  "customerToken": "cs_3C04TQd6OSkDNFa90UyYAUaD1Lq8NcQbHjQi",
  "couponCodes": [],
  "addressToken": "adrs_hzle2kYXjQg1LGnPGtLwMs9m",
  "shippingMethod": {
    "carrier": "freeshipping",
    "description": "",
    "deliveryDateTime": null,
    "deliveryDays": null,
    "origRate": 0,
    "rate": 0,
    "id": "UO2S3uFr49zCBJGAZMRYanqh",
    "methodName": "Free Shipping"
  },
  "shippingMethodId": "UO2S3uFr49zCBJGAZMRYanqh",
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
  "contactEmail": "sharondoe@gmail.com",
  "contactPhone": "",
  "shippingMethodsJson": [
    {
      "carrier": "freeshipping",
      "description": "",
      "deliveryDateTime": null,
      "deliveryDays": null,
      "origRate": 0,
      "rate": 0,
      "id": "UO2S3uFr49zCBJGAZMRYanqh",
      "methodName": "Free Shipping"
    }
  ],
  "contactFirstName": "Sarah",
  "contactLastName": "Jones",
  "companyName": "",
  "createdAt": "2024-06-27 10:33:43",
  "editedAt": "2024-06-27 10:41:54",
  "pricing": {
    "productsTotal": 0.1,
    "origTotal": 0.1,
    "subTotal": 0.1,
    "totalCouponDiscount": 0,
    "totalAfterCoupon": 0.1,
    "shipping": 0,
    "tax": 0,
    "total": 0.1
  },
  "couponCodesInfo": []
}
```
