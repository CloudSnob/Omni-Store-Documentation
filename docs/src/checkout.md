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


### Query Parameters

| Parameter        | Required | Type   | Unique | Description                       |
|------------------|----------|--------|--------|-----------------------------------|
| addressToken     | true     | string | -      | Customer Address refference token |
| contactEmail     | true     | string |        | Customer Email                    |
| contactPhone     | true     | string |        | Customer Phone                    |
| contactFirstName | false    | string | false  | Customer First Name               |
| contactLastName  | false    | string | false  | Customer Last Name                |
| companyName      | false    | string | false  | Customer Company Name             |


```shell
curl --request POST \
  --url https://storeapi.csomni.com/checkout/info \
  --header 'token: site_xxxxxxxxxxx' \
  --header 'customerToken: cs_xxxxxxxxxxx' \
  --data '{
        "contactEmail" : "123456@test.com",
        "addressToken" : "adrs_xxxxxxxxxxxxxx",
        "contactFirstName": "Sarah",
        "contactLastName": "Jones"
        }'

```

> The above command returns JSON structured like this

```json
{
  "id": 821,
  "cartToken": "cart_xxxxxxxxxxxxxxx",
  "customerToken": "cs_xxxxxxxxxxxxxxxx",
  "couponCodes": null,
  "addressToken": "adrs_xxxxxxxxxxxxxx",
  "shippingMethod": null,
  "shippingMethodId": "",
  "shippingAddressLabel": "",
  "shippingAddress": {
    "address": "abc",
    "address2": "",
    "city": "New York",
    "state": "New York",
    "zip": "71005",
    "country": "",
    "phone": "",
    "mobile": "",
    "specialValues": []
  },
  "contactEmail": "sjones1@gmail.com",
  "contactFirstName": "Sarah",
  "contactLastName": "Jones",
  "companyName": "",
  "contactPhone": "1233333",
  "shippingMethodsJson": [
    {
      "carrier": "freeshipping",
      "description": "",
      "deliveryDateTime": null,
      "deliveryDays": null,
      "origRate": 0,
      "rate": 0,
      "id": "xxxxxxxxxxxxxxxx",
      "methodName": "freeshipping"
    }
  ],
  "pricing": {
    "productsTotal": 9,
    "origTotal": 9,
    "subTotal": 9,
    "tax": 0.9,
    "totalCouponDiscount": 0,
    "totalAfterCoupon": 9.9,
    "total": 9.9
  },
  "couponCodesInfo": []
}
```

## Chekout Step 2 - Choose shipping method
This API submits the chosen shipping method. The shipping method Id's are returned in the previous API call - Checkout Step 1, and returns the new total including any shipping charge

### HTTP Request

`POST https://storeapi.csomni.com/checkout/info`

### Header Parameters
| Parameter     | Required | Type   | Description      |
|---------------|----------|--------|------------------|
| customerToken | true     | string | Customer Token   |
| siteToken     | true     | string | Unique siteToken |

### Data Parameters

| Parameter        | Type   | Type   |Required | Description        |
|------------------|--------|--------|----------|--------------------|
| shippingMethodId | string | string |true     | Shipping method Id |

```shell
curl --request POST \
  --url https://storeapi.csomni.com/checkout/shippingmethod \
  --header 'token: site_xxxxxxxxx' \
  -- header 'customerToken: cs_xxxxxxxxxxxxxx' \
  --data '{
          "shippingMethodId" : "123456789"
           }'

```

> The above command returns JSON structured like this

```json
{
  "id": 821,
  "cartToken": "cart_xxxxxxxxxxxxxxxxx",
  "customerToken": "cs_xxxxxxxxxxxxxxxxx",
  "couponCodes": null,
  "addressToken": "adrs_xxxxxxxxxxxxxxx",
  "shippingMethod": null,
  "shippingMethodId": "",
  "shippingAddressLabel": "",
  "shippingAddress": {
    "address": "abc",
    "address2": "",
    "city": "New York",
    "state": "New York",
    "zip": "71005",
    "country": "",
    "phone": "",
    "mobile": "",
    "specialValues": []
  },
  "contactEmail": "test@gmail.com",
  "contactFirstName": "Sarah",
  "contactLastName": "Jones",
  "companyName": "",
  "contactPhone": "1234567890",
  "shippingMethodsJson": [
    {
      "carrier": "freeshipping",
      "description": "",
      "deliveryDateTime": null,
      "deliveryDays": null,
      "origRate": 0,
      "rate": 0,
      "id": "123456789",
      "methodName": "freeshipping"
    }
  ],
  "pricing": {
    "productsTotal": 9,
    "origTotal": 9,
    "subTotal": 9,
    "tax": 0.9,
    "totalCouponDiscount": 0,
    "totalAfterCoupon": 9.9,
    "total": 9.9
  },
  "couponCodesInfo": []
}
```

## Chekout Step 3: OPTION 1: Pay NOW

This endpoint processes payment for a cart and creates an order. 
The data is expected to include all the card details, or reference a cardToken that has already been saved for this customer

### HTTP Request

`POST https://storeapi.csomni.com/checkout/payment`

### Query Parameters - to pay with a new card

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
        "cartToken": "cart_xxxxxxxxxxxxxx",
        "cartProdToken": "cp_xxxxxxxxxxxxxxx",
        "addOnToProdToken": "",
        "cartProdQuantity": 1,
        "addOnProdTokens": null,
        "prodToken": "vrnt_xxxxxxxxxxxxxxx",
        "deleted": 0,
        "siteToken": "site_xxxxxxxxxxxx",
        "customerToken": "cs_xxxxxxxxxxxxxxxx",
        "cartCreated": "1638443146",
        "cartLastTouched": "1638443146",
        "prodStaticCollections": ["clcs_xxxxxxxxxxx"],
        "specialValues": [],
        "product": {
          "prodToken": "prod_xxxxxxxxxxxxxxxxx",
          "variantToken": "vrnt_xxxxxxxxxxxxx",
          "variantName": "Red Ball",
          "variantImage": {
            "file": "[]"
          },
          "variantImages": [],
          "variantWeight": "55",
          "variantDimW": "76",
          "variantDimL": "3",
          "variantDimH": "4",
          "variantUpc": "",
          "variantNumber": "UHNK-4567",
          "manufacturerPartNumber": "1234567888",
          "variantPrice": 9,
          "variantMapPrice": 0,
          "variantMsrpPrice": 0,
          "variantDisplayPrice": 21,
          "variantDescription": "",
          "variantAlert": "",
          "variantLowlevel": "46",
          "variantSlug": "placeat-aut-consequ",
          "variantVisible": 1,
          "variantAllowCheckout": 0,
          "variantCheckInvetory": 0,
          "variantTrackInventory": 0,
          "taxType": "",
          "taxable": 1,
          "inventoryCount": "4",
          "shippingProduct": 0,
          "variantMetaTitle": "",
          "variantMetaDescription": "",
          "variantBrand": "",
          "google_variantCategory": "",
          "google_variantType": "",
          "google_variantCondition": "",
          "hideGoogleData": 0,
          "sortOrder": 0,
          "dateCreated": "1620318552",
          "deleted": 0,
          "backOrderWarning": 0,
          "variantInStock": true,
          "prodName": "Balls",
          "prodImage": {
            "file": ""
          }
        },
        "addOnProducts": [],
        "pricing": {
          "total": 9
        },
        "shipping": {
          "totalWeight": 55
        }
      }
    ],
    "orderEmail": "example@gmail.com",
    "orderShippingMethod": {
      "carrier": "freeshipping",
      "description": "",
      "deliveryDateTime": null,
      "deliveryDays": null,
      "origRate": 0,
      "rate": 0,
      "id": "123456",
      "methodName": "freeshipping"
    },
    "orderTotal": 9.9,
    "orderTax": 0.9,
    "orderShipping": 0,
    "orderWeight": 55,
    "orderShippingAddress": "{\"address\":\"abc\",\"address2\":\"\",\"city\":\"New York\",\"state\":\"New York\",\"zip\":\"1234567\",\"country\":\"\",\"phone\":\"\",\"mobile\":\"\",\"specialValues\":[]}",
    "orderPaymentMethod": {
      "xResult": "A",
      "xStatus": "Approved",
      "xError": "",
      "xErrorCode": "00000",
      "xRefNum": "xxxxxxxx",
      "xExp": "xxxx",
      "xAuthCode": "xxxxxxx",
      "xBatch": "xxxxxxx",
      "xAvsResultCode": "NNN",
      "xAvsResult": "Address: No Match & 5 Digit Zip: No Match",
      "xCvvResultCode": "",
      "xCvvResult": "No CVV data available",
      "xAuthAmount": "9.90",
      "xMaskedCardNumber": "4xxxxxxxxxxx4242",
      "xCardType": "Visa",
      "xName": "Sarah Jones",
      "xToken": "123456",
      "xMID": "xxxxxxxxxx1234",
      "xTID": "xxxxx1234",
      "xCurrency": "USD",
      "xDate": "12/2/2021 6:19:14 AM",
      "xEntryMethod": "Keyed",
      "cardToken": "cc_xxxxxxxxxx"
    },
    "contactLastName": "Jones",
    "contactFirstName": "Sarah",
    "orderProdQuantity": 1,
    "paymentObject": "{\"xResult\":\"A\",\"xStatus\":\"Approved\",\"xError\":\"\",\"xErrorCode\":\"00000\",\"xRefNum\":\"xxxxxxxxx\",\"xExp\":\"0123\",\"xAuthCode\":\"xxxxxxxx\",\"xBatch\":\"5150840\",\"xAvsResultCode\":\"NNN\",\"xAvsResult\":\"Address: No Match & 5 Digit Zip: No Match\",\"xCvvResultCode\":\"\",\"xCvvResult\":\"No CVV data available\",\"xAuthAmount\":\"9.90\",\"xMaskedCardNumber\":\"4xxxxxxxxxxx1234\",\"xCardType\":\"Visa\",\"xName\":\"Sarah Jones\",\"xToken\":\"123456\",\"xMID\":\"xxxxxxxxxx9999\",\"xTID\":\"xxxxx6789\",\"xCurrency\":\"USD\",\"xDate\":\"12\\/2\\/2021 6:19:14 AM\",\"xEntryMethod\":\"Keyed\",\"cardToken\":\"cc_xxxxxxxxxxxxxx\"}",
    "cardToken": "cc_xxxxxxxxxxxxx",
    "orderIP": "000.000.000.00",
    "cartToken": "cart_xxxxxxxxxxxxx",
    "po": "",
    "BillToName": "Sarah Jones",
    "BillToAddress": "{\"name\":\"Sarah Jones\",\"address\":\"abc\",\"address2\":\"\",\"zip\":\"71005\",\"city\":\"New York\",\"state\":\"New York\",\"country\":\"\",\"mobile\":\"\",\"phone\":\"\"}",
    "orderNotePublic": "",
    "siteToken": "site_xxxxxxxxxxxxxx",
    "customerToken": "cs_xxxxxxxxxxxxxxxx",
    "orderToken": "ordr_xxxxxxxxxxxx",
    "orderNumber": 117,
    "orderStatus": "os_awaiting_fulfillment",
    "checkoutObject": "{\"id\":821,\"cartToken\":\"cart_xxxxxxxxxxx\",\"customerToken\":\"cs_xxxxxxxxxxxx\",\"couponCodes\":null,\"addressToken\":\"adrs_xxxxxxxxxxxxx\",\"shippingMethod\":{\"carrier\":\"freeshipping\",\"description\":\"\",\"deliveryDateTime\":null,\"deliveryDays\":null,\"origRate\":0,\"rate\":0,\"id\":\"123456\",\"methodName\":\"freeshipping\"},\"shippingMethodId\":\"123456\",\"shippingAddressLabel\":\"\",\"shippingAddress\":{\"address\":\"abc\",\"address2\":\"\",\"city\":\"New York\",\"state\":\"New York\",\"zip\":\"71005\",\"country\":\"\",\"phone\":\"\",\"mobile\":\"\",\"specialValues\":[]},\"contactEmail\":\"123456@gmail.com\",\"contactFirstName\":\"Sarah\",\"contactLastName\":\"Jones\",\"companyName\":\"\",\"contactPhone\":\"1233333\",\"shippingMethodsJson\":[{\"carrier\":\"freeshipping\",\"description\":\"\",\"deliveryDateTime\":null,\"deliveryDays\":null,\"origRate\":0,\"rate\":0,\"id\":\"uC6tjBvFKAlrzb5Rh21nVmkG\",\"methodName\":\"freeshipping\"}],\"pricing\":{\"productsTotal\":9,\"origTotal\":9,\"subTotal\":9,\"tax\":0.9,\"totalCouponDiscount\":0,\"totalAfterCoupon\":9.9,\"total\":9.9},\"couponCodesInfo\":[]}",
    "customerObject": "{\"id\":0,\"customerFirstName\":\"Sarah \",\"customerLastName\":\"Jones\",\"customerEmail\":\"sjones1@gmail.com\",\"customerPhone\":\"0313445214\",\"customerCompanyName\":\"abcd\",\"dateCreated\":\"1635837718\",\"customerStatus\":\"\",\"customerTypes\":null,\"customerGroups\":null,\"isLoggedIn\":0,\"customerDocs\":null,\"taxExempt\":null,\"taxExemptID\":null,\"createdAt\":\"2021-11-02 07:21:58\",\"editedAt\":\"2021-11-02 12:04:02\"}"
  }
}
```



## Checkout Step 3 OPTION 2: Pay Later - Process as a PO
This endpoint allows customers to process their order without payment. 
This endpoint is only accessible if the company and/or site settings are set to allow checkout with PO

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


```shell
curl --request POST \
  --url https://storeapi.csomni.com/checkout/po \
  --header 'token: site_xxxxxxxxx' \
  --header 'customerToken: cs_xxxxxxxxxxxxxxx' \
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
                "cartToken": "cart_xxxxxxxxxxxx",
                "cartProdToken": "cp_xxxxxxxxxx",
                "cartProdQuantity": 1,
                "addOnToProdToken": "",
                "addOnProdTokens": null,
                "prodToken": "vrnt_xxxxxxxxxxxx",
                "deleted": 0,
                "createdAt": "2022-12-08 12:34:27",
                "editedAt": "2022-12-08 12:34:27",
                "siteToken": "site_xxxxxxxxxxxxxxxx",
                "customerToken": "cust_xxxxxxxxxxxxxxxxxxxxx",
                "cartCreated": "1670502867",
                "cartLastTouched": "1670502867",
                "prodStaticCollections": [],
                "specialValues": [],
                "product": {
                    "prodToken": "prod_xxxxxxxxxxxxxxx",
                    "variantToken": "vrnt_xxxxxxxxxxxxxxxx",
                    "variantName": "viral",
                    "variantImage": [],
                    "variantImages": [],
                    "variantWeight": "",
                    "variantDimW": "",
                    "variantDimL": "",
                    "variantDimH": "",
                    "variantUpc": "",
                    "variantNumber": "",
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
                    "inventoryCount": -2,
                    "shippingProduct": 0,
                    "variantMetaTitle": "",
                    "variantMetaDescription": "",
                    "variantBrand": "",
                    "sortOrder": 0,
                    "dateCreated": "1667771464",
                    "deleted": 0,
                    "backOrderWarning": 0,
                    "createdAt": "2022-11-06 21:51:04",
                    "editedAt": "2022-12-08 11:43:32",
                    "variantInStock": true,
                    "prodName": "Soft Pretzel",
                    "prodImage": {
                        "file": "magni-quaerat-et"
                    }
                },
                "addOnProducts": [],
                "pricing": {
                    "total": 0.1
                },
                "shipping": {
                    "totalWeight": 0
                }
            }
        ],
        "orderEmail": "sarah@gmail.com",
        "orderShippingMethod": {
            "carrier": "freeshipping",
            "description": "",
            "deliveryDateTime": null,
            "deliveryDays": null,
            "origRate": 0,
            "rate": 0,
            "id": "123456",
            "methodName": ""
        },
        "orderTotal": 0.1,
        "orderTotalPaid": 0,
        "orderTax": 0,
        "orderShipping": 0,
        "orderWeight": 0,
        "orderShippingAddress": "{\"address\":\"12354 Main Street\",\"address2\":\"\",\"city\":\"Monsey\",\"state\":\"NY\",\"zip\":\"10952\",\"country\":\"\",\"phone\":\"\",\"mobile\":\"\",\"specialValues\":[]}",
        "orderPaymentMethod": null,
        "contactLastName": "Jones",
        "contactFirstName": "Sarah",
        "orderProdQuantity": 1,
        "paymentObject": null,
        "cardToken": null,
        "orderIP": "00.000.000.000",
        "cartToken": "cart_xxxxxxxxxxxxxxx",
        "PO": "123-P9ojd",
        "BillToName": "Sarah  Jones ",
        "BillToAddress": "{\"name\":\"Sarah Jones \",\"address\":\"12354 Main Street\",\"address2\":\"\",\"zip\":\"10952\",\"city\":\"Monsey\",\"state\":\"NY\",\"country\":\"\",\"mobile\":\"\",\"phone\":\"\"}",
        "orderNotePublic": "order processed through PO pathway",
        "siteToken": "site_xxxxxxxxxxxxxxx",
        "companyToken": "comp_xxxxxxxxxxxxxxx",
        "customerToken": "cs_Xxxxxxxxxxx",
        "orderToken": "ordr_xxxxxxxxxxxxxxx",
        "orderNumber": "xxxxxxxxxx",
        "orderStatus": "os_awaiting_fulfillment",
        "checkoutObject": "{\"id\":30557,\"cartToken\":\"cart_xxxxxxxxxxxxxxx\",\"customerToken\":\"cs_xxxxxxxxxxxxxxx\",\"couponCodes\":null,\"addressToken\":\"adrs_xxxxxxxxxxxx\",\"shippingMethod\":{\"carrier\":\"freeshipping\",\"description\":\"\",\"deliveryDateTime\":null,\"deliveryDays\":null,\"origRate\":0,\"rate\":0,\"id\":\"123456\",\"methodName\":\"\"},\"shippingMethodId\":\"BQRJmVECcNaT37w5Aq8h2fot\",\"shippingAddressLabel\":\"\",\"shippingAddress\":{\"address\":\"12354 Main Street\",\"address2\":\"\",\"city\":\"Monsey\",\"state\":\"NY\",\"zip\":\"10952\",\"country\":\"\",\"phone\":\"\",\"mobile\":\"\",\"specialValues\":[]},\"contactEmail\":\"sjones1@gmail.com\",\"contactPhone\":\"925-755-7647\",\"shippingMethodsJson\":[{\"carrier\":\"freeshipping\",\"description\":\"\",\"deliveryDateTime\":null,\"deliveryDays\":null,\"origRate\":0,\"rate\":0,\"id\":\"123456\",\"methodName\":\"\"}],\"contactFirstName\":\"Sarah - shippingName\",\"contactLastName\":\"Jones - shippingName\",\"companyName\":\"Tyrell Corp,\",\"createdAt\":\"2022-12-08 12:34:38\",\"editedAt\":\"2022-12-08 12:34:46\",\"pricing\":{\"productsTotal\":0.1,\"origTotal\":0.1,\"subTotal\":0.1,\"tax\":0,\"totalCouponDiscount\":0,\"totalAfterCoupon\":0.1,\"total\":0.1},\"couponCodesInfo\":[]}",
        "customerObject": "{\"id\":53237,\"customerFirstName\":\"Sarah\",\"customerLastName\":\"Jones\",\"customerEmail\":\"sjones1@gmail.com\",\"customerPhone\":\"925-755-7647\",\"customerCompanyName\":\"Tyrell Corp\",\"dateCreated\":\"1670502805\",\"customerStatus\":\"cs_approved\",\"customerTypes\":null,\"customerGroups\":null,\"isLoggedIn\":1,\"customerDocs\":null,\"taxExempt\":null,\"taxExemptID\":null,\"createdAt\":\"2022-12-08 12:33:25\",\"editedAt\":\"2022-12-08 12:34:55\"}",
        "dateCreated": 1670502895
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


```shell
curl --request POST \
  --url https://storeapi.csomni.com/checkout/applycoupon \
  --header 'token: site_xxxxxxxxxxxxx' \
  --header 'customerToken: cs_xxxxxxxxxxxxxxxxx' \
  --data '{"couponCode" : "SUMMER20"}'

```

> The above command returns JSON structured like this:
> Note: The address properties (addressToken, shippingAddress object, and shippingMethodsJson)  will only have a value if the coupon call is made for a cart with shipping/address details.
> If address details are not known, the address related properties will return as an empty string.

```json
{
  "id": "117",
  "cartToken": "cart_xxxxxxxxxxx",
  "customerToken": "cs_xxxxxxxxxxxxxx",
  "couponCodes": ["SUMMER50"],
  "addressToken": "adrs_xxxxxxxxxxxxxx",
  "shippingMethod": "",
  "shippingMethodId": "",
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
  "shippingAddress2": "",
  "shippingZip": "",
  "shippingState": "",
  "shippingCity": "",
  "contactEmail": "",
  "contactFirstName": "",
  "contactLastName": "",
  "companyName": "",
  "contactPhone": "",
  "shippingMethodsJson": [
    {
      "carrier": "freeshipping",
      "description": "",
      "deliveryDateTime": null,
      "deliveryDays": null,
      "origRate": 0,
      "rate": 0,
      "id": "5gcIaksdpf3vbSArCKPjwEBh",
      "methodName": "Free Shipping"
    },
    {
      "carrier": "storepickup",
      "description": "",
      "deliveryDateTime": null,
      "deliveryDays": null,
      "origRate": 0,
      "rate": 0,
      "id": "xXpZObCDte8J2F6TkVSQY7qy",
      "methodName": "Store Pickup"
    },
    {
      "carrier": "",
      "origRate": 0,
      "rate": 50,
      "id": "ZYoaWGmhU5CgsNJdcqe3FAw0",
      "methodName": ""
    }
  ],
  "pricing": {
    "productsTotal": 329.95,
    "origTotal": 329.95,
    "totalCouponDiscount": 164.975,
    "totalAfterCoupon": 164.98,
    "tax": 0,
    "subTotal": 164.98,
    "total": 164.98
  },
  "couponCodesInfo": [
    {
      "name": "SUMMER50",
      "msg": "Successfully applied",
      "status": "valid"
    }
  ]
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

```shell
curl --request POST \
  --url https://storeapi.csomni.com/checkout/removecoupon \
  --header 'token: site_xxxxxxxxx' \
  --header 'customerToken: cs_xxxxxxxxxxxxxxx' \
  --data '{"couponCode" : "SUMMER20"}'

```

> The above command returns JSON structured like this

```json
{
  "id": "117",
  "cartToken": "cart_xxxxxxxxxxxxxxxxxx",
  "customerToken": "cs_xxxxxxxxxxxxxxxx",
  "couponCodes": [],
  "addressToken": "",
  "shippingMethod": "",
  "shippingMethodId": "",
  "shippingAddress": "",
  "shippingAddress2": "",
  "shippingZip": "",
  "shippingState": "",
  "shippingCity": "",
  "contactEmail": "",
  "contactFirstName": "",
  "contactLastName": "",
  "companyName": "",
  "contactPhone": "",
  "shippingMethodsJson": "",
  "pricing": {
    "productsTotal": 329.95,
    "origTotal": 329.95,
    "totalCouponDiscount": null,
    "totalAfterCoupon": 329.95,
    "tax": 0,
    "subTotal": 329.95,
    "total": 329.95
  },
  "couponCodesInfo": []
}
```
