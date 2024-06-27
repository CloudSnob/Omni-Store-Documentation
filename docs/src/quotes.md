# QUOTES

> Enable shipping quotes in company settings
> Shipping quotes is a feature that allows customers to request a shipping quote for items in their cart.
> The quote moves through phases until the customer completes the quote by processing with payment or by PO.
> 
> Step 1 - OMNI STORE:
> Customer creates Quote through the cart
> 
> Step 2 - OMNI ADMIN: 
> Admin adds shipping options to the quote. One option or multiple can be added.
> 
> Step 3 - OMNI STORE:
> Customer reviews shipping options and selects one. 
> 
> Step 4 - OMNI STORE:
> Customer confirms by processing with Pay Now, or Pay Later options.
> New order associated to the quote is created.

## Step 1: Create new Shipping Quote Request
This endpoint creates a new shipping quote request. The quote is created with the status 'waiting-response'. Once Admin has added shipping options to the quote, the quote's status change to 'quoted'. 

### HTTP Request

`POST https://storeapi.csomni.com/quotes`

### Header Parameters
| Parameter     | Type   | Required | Description       |
|---------------|--------|----------|-------------------|
| token         | string | true     | Site Token ID     |
| customerToken | string | true     | Customer Token ID |

Sample in Shell:

```shell

curl --location --request POST 'https://storeapi.csomni.com/quotes' \
--header 'token: site_xxxxxxxxxxxx' \
--header 'customerToken: cs_GWdE9xY2dcL9qqBmNKx7WXivTh73nJtGH4NK' \
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
        "email": "sharondoe@gmail.com",
        "phoneNumber": "78945678945",
        "companyName": "Techo"
    }
}'
```

Response:

```json
{
  "quoteToken": "quote_0vq9tiG0xNbf",
  "customerToken": "cs_GWdE9xY2dcL9qqBmNKx7WXivTh73nJtGH4NK",
  "quoteFiles": "",
  "status": "waiting-response",
  "deleted": 0,
  "dateCreated": "2024-06-24 20:53:48",
  "dateUpdated": "2024-06-24 20:53:49",
  "variantsTotal": 1.1,
  "shippingTotal": 0,
  "taxTotal": 0,
  "itemsCount": 2,
  "itemsQuantity": 4,
  "combinedTotal": null,
  "quoteNumber": "Q50166",
  "variantDetails": [
    {
      "quote_variantsToken": "quoteVariant_f23QCHKjg91K",
      "variantToken": "vrnt_EvonkJQsR6fRbDtm",
      "quantity": 2,
      "itemPrice": 0.3,
      "itemTax": 0,
      "lineTotal": 0.6,
      "fullDetails": {
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
        "prodName": "3\/4 IN. O.D. SATIN NICKEL DRIVE-IN, SPRING LOADED, BALL STYLE, CABINET DOOR LATCH WITH STRIKE\t"
      }
    },
    {
      "quote_variantsToken": "quoteVariant_XRtqphtqEtxU",
      "variantToken": "vrnt_OYIwevfBUfxErFG3",
      "quantity": 2,
      "itemPrice": 0.25,
      "itemTax": 0,
      "lineTotal": 0.5,
      "fullDetails": {
        "prodToken": "prod_FgNybasFJG4YUJ4h",
        "variantToken": "vrnt_OYIwevfBUfxErFG3",
        "variantName": "31\" WHITE CHINA SINK",
        "variantImage": {
          "file": "10-2-2022\/1664742840284__7264__VE3118W.jpg",
          "type": ""
        },
        "variantImages": [],
        "variantWeight": "0",
        "variantDimW": "0",
        "variantDimL": "0",
        "variantDimH": "0",
        "variantUpc": "",
        "variantNumber": "VE3118W",
        "manufacturerPartNumber": "",
        "variantPrice": 0.25,
        "variantMapPrice": 0,
        "variantMsrpPrice": 0,
        "variantDisplayPrice": 0,
        "variantDescription": "",
        "variantAlert": "",
        "variantLowlevel": "",
        "variantSlug": "31-white-china-sink",
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
        "inventoryCount": 180,
        "shippingProduct": 0,
        "variantMetaTitle": "",
        "variantMetaDescription": "",
        "variantBrand": "",
        "sortOrder": 0,
        "dateCreated": "1661531956",
        "deleted": 0,
        "backOrderWarning": 0,
        "createdAt": "2022-12-18 23:01:04",
        "editedAt": "2024-06-20 08:41:56",
        "variantInStock": true,
        "prodName": "31\" WHITE CHINA SINK"
      }
    }
  ],
  "shippingAddress": {
    "addressToken": "adrs_CJO9LkwmNJqSQmOBtaTsGE1w",
    "addressLabel": "Home Address",
    "address": "123 Main street",
    "address2": "Unit 4",
    "addressCity": "NY",
    "addressState": "NY",
    "addressZip": "10952",
    "addressFirstName": "Jane",
    "addressLastName": "Foster",
    "phoneNumber": "03356705565",
    "mobileNumber": "45678945666",
    "addressCountry": "United States",
    "addressDefault": 0,
    "createdAt": "2024-06-19 09:32:49",
    "editedAt": "2024-06-19 09:32:49",
    "specialValues": []
  },
  "contactDetails": {
    "quote_ContactToken": "quoteContact_dOV6xkMAQxIM",
    "firstName": "Sharon",
    "lastName": "Doe",
    "email": "sharondoe@gmail.com",
    "phoneNumber": "78945678945",
    "companyName": "Techo"
  },
  "shippingQuote": []
}
```

## Step 2: Add shipping options
> Not listed here because this action is done without the Admin portal


## Step 3: Select shipping option
This endpoint selects one shipping option to apply to the quote

### HTTP Request
`POST https://storeapi.csomni.com/quotes/{shippingQuoteToken}/approve-shipping`

### URL Parameters
| Parameter          | Type   | Description             |
|--------------------|--------|-------------------------|
| shippingQuoteToken | string | Shipping Quote Token ID |

### Header Parameters
| Parameter     | Type   | Description       |
|---------------|--------|-------------------|
| token         | string | Site Token ID     |
| customerToken | string | Customer Token ID |

### Data Parameters
| Parameter  | Type              | Description              |
|------------|-------------------|--------------------------|
| approved   | bool (true/false) | Setting approved to true |
| approvedBy | string            | Customer Name for record |

Sample in Shell:

```shell
curl --location --request POST 'https://storeapi.com/quotes/shippingQuoteToken_3yw8DHZYCYvk/approve-shipping' \
--header 'token: site_xxxxxxxxxxxx' \
--header 'customerToken: cs_GWdE9xY2dcL9qqBmNKx7WXivTh73nJtGH4NK'
--header 'Content-Type: application/json' \
--data-raw '{
    "approved": true,
    "approvedBy": "Sharon Doe"  
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

## Step 4 OPTION 1: Checkout - Pay Now with CC
This endpoint submits payment details for a quote and creates an order for the quote.

## HTTP Request

`POST https://storeapi.csomni.com/checkout/payment/{quoteToken}`

### Header Parameters
| Parameter     | Type   | Required | Description       |
|---------------|--------|----------|-------------------|
| token         | string | true     | Site Token ID     |
| customerToken | string | true     | Customer Token ID |

### URL Parameters
| Parameter  | Type   | Required | Description |
|------------|--------|----------|-------------|
| quoteToken | string | true     | Quote Token |

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

curl --location --request POST 'https://storeapi.csomni.com/checkout/payment/quote_t0pLilkf4jPt' \
--header 'token: site_xxxxxxxxxxxx' \
--header 'customerToken: cs_GWdE9xY2dcL9qqBmNKx7WXivTh73nJtGH4NK' \
--data-raw '{
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

> The above command returns JSON structured like this
```json
{
  "status": "success",
  "order": {
    "orderProducts": [
      {
        "cartToken": "quoteCart_a78ukPKYcq9Ou6M2moupIJuI",
        "cartProdToken": "cp_7bUsR8vGGbyIEHR8lgeC1VMh",
        "cartProdQuantity": 2,
        "prodToken": "vrnt_k2BdGbMqyFoopAhO",
        "created_at": "2024-06-26 08:46:08",
        "updated_at": "2024-06-26 08:46:08",
        "deleted": 0,
        "deleted_at": null,
        "siteToken": "site_63Vdsmr9Qsq0",
        "quoteToken": "quote_t0pLilkf4jPt",
        "quoteCartToken": "quoteCart_a78ukPKYcq9Ou6M2moupIJuI",
        "customerToken": "cs_GWdE9xY2dcL9qqBmNKx7WXivTh73nJtGH4NK",
        "addOnProdTokens": "",
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
          "inventoryCount": 98,
          "shippingProduct": 0,
          "variantMetaTitle": null,
          "variantMetaDescription": null,
          "variantBrand": null,
          "sortOrder": 2,
          "dateCreated": "1717576258",
          "deleted": 0,
          "backOrderWarning": 0,
          "createdAt": "2024-06-05 08:30:58",
          "editedAt": "2024-06-25 22:23:00",
          "variantInStock": true,
          "prodName": "Generic Plastic SoapBike",
          "prodImage": {
            "file": ""
          }
        },
        "addOnProducts": [],
        "pricing": {
          "total": 0.2
        },
        "shipping": {
          "totalWeight": 2
        }
      }
    ],
    "orderEmail": "Sharon@gmail.com",
    "orderShippingMethod": {
      "id": "shippingQuoteToken_zLM4jUXMRcFo",
      "quote_shippingQuoteToken": "shippingQuoteToken_zLM4jUXMRcFo",
      "quoteToken": "quote_t0pLilkf4jPt",
      "carrier": "UPS",
      "methodName": "Next Day Air",
      "origRate": null,
      "rate": "0.01",
      "deliveryDateTime": null,
      "deliveryDays": "0.1",
      "description": null,
      "approved": 1,
      "approvedBy": "Sharon Doe"
    },
    "orderTotal": 0.21,
    "orderTax": 0,
    "orderTotalPaid": "0.21",
    "orderShipping": 0.01,
    "orderWeight": 2,
    "orderShippingAddress": "{\"address\":\"123 Main street\",\"address2\":\"Unit 4\",\"city\":\"NY\",\"state\":\"NY\",\"zip\":\"10952\",\"country\":\"United States\",\"phone\":\"0789456123654\",\"mobile\":\"45678945666\",\"specialValues\":null}",
    "orderPaymentMethod": {
      "xResult": "A",
      "xStatus": "Approved",
      "xError": "",
      "xErrorCode": "00000",
      "xRefNum": "10038227975",
      "xExp": "0126",
      "xAuthCode": "14563A",
      "xBatch": "5150840",
      "xAvsResultCode": "NNN",
      "xAvsResult": "Address: No Match & 5 Digit Zip: No Match",
      "xCvvResultCode": "",
      "xCvvResult": "No CVV data available",
      "xAuthAmount": "0.21",
      "xMaskedCardNumber": "4xxxxxxxxxxx1234",
      "xCardType": "Visa",
      "xName": "Sharon Doe",
      "xToken": "xxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
      "xMID": "xxxxxxxxxxxxxx",
      "xTID": "xxxxxxxxx",
      "xCurrency": "USD",
      "xDate": "6\/26\/2024 4:46:11 AM",
      "xEntryMethod": "Keyed",
      "cardToken": "quoteCart_a78ukPKYcq9Ou6M2moupIJuI"
    },
    "contactLastName": "Doe",
    "contactFirstName": "Sharon",
    "orderProdQuantity": 2,
    "paymentObject": "{\"xResult\":\"A\",\"xStatus\":\"Approved\",\"xError\":\"\",\"xErrorCode\":\"00000\",\"xRefNum\":\"xxxxxxxxxxxxxxx\",\"xExp\":\"xxxx\",\"xAuthCode\":\"xxxxxxx\",\"xBatch\":\"xxxxxxxx\",\"xAvsResultCode\":\"NNN\",\"xAvsResult\":\"Address: No Match & 5 Digit Zip: No Match\",\"xCvvResultCode\":\"\",\"xCvvResult\":\"No CVV data available\",\"xAuthAmount\":\"0.21\",\"xMaskedCardNumber\":\"4xxxxxxxxxxx1234\",\"xCardType\":\"Visa\",\"xName\":\"Sharon Doe\",\"xToken\":\"xxxxxxxxxxxxxxxxxxxxx\",\"xMID\":\"xxxxxxxxxx9999\",\"xTID\":\"xxxxx1234\",\"xCurrency\":\"USD\",\"xDate\":\"6\\\/26\\\/2024 4:46:11 AM\",\"xEntryMethod\":\"Keyed\",\"cardToken\":\"quoteCart_a78ukPKYcq9Ou6M2moupIJuI\"}",
    "cardToken": "quoteCart_a78ukPKYcq9Ou6M2moupIJuI",
    "orderIP": "81.151.213.25",
    "cartToken": "quoteCart_a78ukPKYcq9Ou6M2moupIJuI",
    "PO": "1234",
    "BillToName": "Sharon Doe",
    "BillToAddress": "{\"name\":\"Sharon Doe\",\"address\":\"10 Orange Drive\",\"address2\":\"\",\"zip\":\"105478\",\"city\":\"Airmont\",\"state\":\"NY\",\"country\":\"United States\",\"mobile\":\"\",\"phone\":\"000000\"}",
    "orderNotePublic": "",
    "quoteToken": "quote_t0pLilkf4jPt",
    "siteToken": "site_63Vdsmr9Qsq0",
    "customerToken": "cs_GWdE9xY2dcL9qqBmNKx7WXivTh73nJtGH4NK",
    "orderToken": "ordr_SYFvgMHFohF7u67PLrPmMnyl",
    "orderNumber": 100000485,
    "orderStatus": "os_awaiting_fulfillment",
    "checkoutObject": "{\"id\":31100,\"cartToken\":\"quoteCart_a78ukPKYcq9Ou6M2moupIJuI\",\"customerToken\":\"cs_GWdE9xY2dcL9qqBmNKx7WXivTh73nJtGH4NK\",\"couponCodes\":null,\"addressToken\":\"adrs_CJO9LkwmNJqSQmOBtaTsGE1w\",\"shippingMethod\":{\"id\":\"shippingQuoteToken_zLM4jUXMRcFo\",\"quote_shippingQuoteToken\":\"shippingQuoteToken_zLM4jUXMRcFo\",\"quoteToken\":\"quote_t0pLilkf4jPt\",\"carrier\":\"UPS\",\"methodName\":\"Next Day Air\",\"origRate\":null,\"rate\":\"0.01\",\"deliveryDateTime\":null,\"deliveryDays\":\"0.1\",\"description\":null,\"approved\":1,\"approvedBy\":\"Sharon Doe\"},\"shippingMethodId\":\"shippingQuoteToken_zLM4jUXMRcFo\",\"shippingAddressLabel\":\"\",\"shippingAddress\":{\"address\":\"123 Main street\",\"address2\":\"Unit 4\",\"city\":\"NY\",\"state\":\"NY\",\"zip\":\"10952\",\"country\":\"United States\",\"phone\":\"03356705565\",\"mobile\":\"45678945666\",\"specialValues\":null},\"contactEmail\":\"sarahjones@gmail.com\",\"contactPhone\":\"987657489\",\"shippingMethodsJson\":[{\"id\":\"shippingQuoteToken_zLM4jUXMRcFo\",\"quote_shippingQuoteToken\":\"shippingQuoteToken_zLM4jUXMRcFo\",\"quoteToken\":\"quote_t0pLilkf4jPt\",\"carrier\":\"UPS\",\"methodName\":\"Next Day Air\",\"origRate\":null,\"rate\":\"0.01\",\"deliveryDateTime\":null,\"deliveryDays\":\"0.1\",\"description\":null,\"approved\":1,\"approvedBy\":\"Sharon Doe\"},{\"id\":\"shippingQuoteToken_XxR2DdbIWPym\",\"quote_shippingQuoteToken\":\"shippingQuoteToken_XxR2DdbIWPym\",\"quoteToken\":\"quote_t0pLilkf4jPt\",\"carrier\":\"Fedex\",\"methodName\":\"Ground Express\",\"origRate\":null,\"rate\":\"0.02\",\"deliveryDateTime\":null,\"deliveryDays\":\"0.2\",\"description\":null,\"approved\":null,\"approvedBy\":null}],\"contactFirstName\":\"Sharon\",\"contactLastName\":\"Doe\",\"companyName\":\"Techo\",\"createdAt\":\"2024-06-26 08:46:09\",\"editedAt\":\"2024-06-26 08:46:09\",\"pricing\":{\"productsTotal\":0.2,\"origTotal\":0.2,\"subTotal\":0.2,\"totalCouponDiscount\":0,\"totalAfterCoupon\":0.2,\"shipping\":0.01,\"tax\":0,\"total\":0.21},\"couponCodesInfo\":[]}",
    "customerObject": "{\"customerFirstName\":\"Sharon Doe\",\"customerLastName\":\"Altmann\",\"customerEmail\":\"sarahjones@gmail.com\",\"customerPhone\":\"\",\"customerCompanyName\":\"\",\"source\":\"store\",\"customerStatus\":\"\",\"customerTypes\":null,\"customerGroups\":null,\"isLoggedIn\":1,\"customerDocs\":\"\",\"taxExempt\":null,\"taxExemptID\":null,\"createdAt\":\"2024-05-16 11:11:53\"}",
    "dateCreated": 1719391572,
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

## Step 4 OPTION 2: Checkout - Pay Later with PO
This endpoint submits PO details for a quote and creates an order for the quote.

## HTTP Request

`POST https://storeapi.csomni.com/checkout/po/{quoteToken}`

### Header Parameters
| Parameter     | Type   | Required | Description       |
|---------------|--------|----------|-------------------|
| token         | string | true     | Site Token ID     |
| customerToken | string | true     | Customer Token ID |

### URL Parameters
| Parameter  | Type   | Required | Description |
|------------|--------|----------|-------------|
| quoteToken | string | true     | Quote Token |

### Data Parameters - to processes as a PO
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
  --url https://storeapi.csomni.com/checkout/po/{quoteToken} \
  --header 'token: site_xxxxxxxxx' \
  --header 'customerToken: cs_GWdE9xY2dcL9qqBmNKx7WXivTh73nJtGH4NK' \
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
        "cartToken": "quoteCart_bvYa8z0JcOJEYnvput1SSwmP",
        "cartProdToken": "cp_ZSFhPBVPDkokVZQlmDfN491x",
        "cartProdQuantity": 2,
        "prodToken": "vrnt_k2BdGbMqyFoopAhO",
        "created_at": "2024-06-26 09:45:36",
        "updated_at": "2024-06-26 09:45:36",
        "deleted": 0,
        "deleted_at": null,
        "siteToken": "site_63Vdsmr9Qsq0",
        "quoteToken": "quote_fX60mOi9kdhV",
        "quoteCartToken": "quoteCart_bvYa8z0JcOJEYnvput1SSwmP",
        "customerToken": "cs_GWdE9xY2dcL9qqBmNKx7WXivTh73nJtGH4NK",
        "addOnProdTokens": "",
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
          "inventoryCount": 88,
          "shippingProduct": 0,
          "variantMetaTitle": null,
          "variantMetaDescription": null,
          "variantBrand": null,
          "sortOrder": 2,
          "dateCreated": "1717576258",
          "deleted": 0,
          "backOrderWarning": 0,
          "createdAt": "2024-06-05 08:30:58",
          "editedAt": "2024-06-26 09:44:02",
          "variantInStock": true,
          "prodName": "Generic Plastic SoapBike",
          "prodImage": {
            "file": ""
          }
        },
        "addOnProducts": [],
        "pricing": {
          "total": 0.2
        },
        "shipping": {
          "totalWeight": 2
        }
      }
    ],
    "orderEmail": "sharondoe@gmail.com",
    "orderShippingMethod": {
      "id": "shippingQuoteToken_jQ0Wvls4uKLW",
      "quote_shippingQuoteToken": "shippingQuoteToken_jQ0Wvls4uKLW",
      "quoteToken": "quote_fX60mOi9kdhV",
      "carrier": "UPS",
      "methodName": "Next Day Air",
      "origRate": null,
      "rate": "0.01",
      "deliveryDateTime": null,
      "deliveryDays": "0.1",
      "description": null,
      "approved": 1,
      "approvedBy": "Sharon Doe"
    },
    "orderTotal": 0.21,
    "orderTotalPaid": 0,
    "orderTax": 0,
    "orderShipping": 0.01,
    "orderWeight": 2,
    "orderShippingAddress": "{\"address\":\"123 Main street\",\"address2\":\"Unit 4\",\"city\":\"NY\",\"state\":\"NY\",\"zip\":\"10952\",\"country\":\"United States\",\"phone\":\"03356705565\",\"mobile\":\"45678945666\",\"specialValues\":null}",
    "orderPaymentMethod": null,
    "contactLastName": "Doe",
    "contactFirstName": "Sharon",
    "orderProdQuantity": 2,
    "paymentObject": null,
    "cardToken": null,
    "orderIP": "127.0.0.1",
    "cartToken": "quoteCart_bvYa8z0JcOJEYnvput1SSwmP",
    "PO": "123-P9ojd",
    "BillToName": "431 Systems LLC",
    "BillToAddress": "{\"name\":\"431 Systems LLC\",\"address\":\"10 Seller Drive\",\"address2\":\"\",\"zip\":\"10952\",\"city\":\"Airmont\",\"state\":\"NY\",\"country\":\"United States\",\"mobile\":\"\",\"phone\":\"000000\"}",
    "orderNotePublic": "",
    "quoteToken": "quote_fX60mOi9kdhV",
    "siteToken": "site_63Vdsmr9Qsq0",
    "customerToken": "cs_GWdE9xY2dcL9qqBmNKx7WXivTh73nJtGH4NK",
    "orderToken": "ordr_HX41vFcOkhP8XCyF6ZQIdHch",
    "orderNumber": 100000490,
    "orderStatus": "os_awaiting_fulfillment",
    "checkoutObject": "{\"id\":31105,\"cartToken\":\"quoteCart_bvYa8z0JcOJEYnvput1SSwmP\",\"customerToken\":\"cs_GWdE9xY2dcL9qqBmNKx7WXivTh73nJtGH4NK\",\"couponCodes\":null,\"addressToken\":\"adrs_CJO9LkwmNJqSQmOBtaTsGE1w\",\"shippingMethod\":{\"id\":\"shippingQuoteToken_jQ0Wvls4uKLW\",\"quote_shippingQuoteToken\":\"shippingQuoteToken_jQ0Wvls4uKLW\",\"quoteToken\":\"quote_fX60mOi9kdhV\",\"carrier\":\"UPS\",\"methodName\":\"Next Day Air\",\"origRate\":null,\"rate\":\"0.01\",\"deliveryDateTime\":null,\"deliveryDays\":\"0.1\",\"description\":null,\"approved\":1,\"approvedBy\":\"Sharon Doe\"},\"shippingMethodId\":\"shippingQuoteToken_jQ0Wvls4uKLW\",\"shippingAddressLabel\":\"\",\"shippingAddress\":{\"address\":\"123 Main street\",\"address2\":\"Unit 4\",\"city\":\"NY\",\"state\":\"NY\",\"zip\":\"10952\",\"country\":\"United States\",\"phone\":\"03356705565\",\"mobile\":\"45678945666\",\"specialValues\":null},\"contactEmail\":\"sarahjones@gmail.com\",\"contactPhone\":\"987657489\",\"shippingMethodsJson\":[{\"id\":\"shippingQuoteToken_jQ0Wvls4uKLW\",\"quote_shippingQuoteToken\":\"shippingQuoteToken_jQ0Wvls4uKLW\",\"quoteToken\":\"quote_fX60mOi9kdhV\",\"carrier\":\"UPS\",\"methodName\":\"Next Day Air\",\"origRate\":null,\"rate\":\"0.01\",\"deliveryDateTime\":null,\"deliveryDays\":\"0.1\",\"description\":null,\"approved\":1,\"approvedBy\":\"Sharon Doe\"},{\"id\":\"shippingQuoteToken_JOPMbo7bcBbp\",\"quote_shippingQuoteToken\":\"shippingQuoteToken_JOPMbo7bcBbp\",\"quoteToken\":\"quote_fX60mOi9kdhV\",\"carrier\":\"Fedex\",\"methodName\":\"Ground Express\",\"origRate\":null,\"rate\":\"0.02\",\"deliveryDateTime\":null,\"deliveryDays\":\"0.2\",\"description\":null,\"approved\":null,\"approvedBy\":null}],\"contactFirstName\":\"Sharon\",\"contactLastName\":\"Doe\",\"companyName\":\"Techo\",\"createdAt\":\"2024-06-26 09:45:39\",\"editedAt\":\"2024-06-26 09:45:39\",\"pricing\":{\"productsTotal\":0.2,\"origTotal\":0.2,\"subTotal\":0.2,\"totalCouponDiscount\":0,\"totalAfterCoupon\":0.2,\"shipping\":0.01,\"tax\":0,\"total\":0.21},\"couponCodesInfo\":[]}",
    "customerObject": "{\"customerFirstName\":\"Sharon\",\"customerLastName\":\"Jones\",\"customerEmail\":\"sharon@jones.com\",\"customerPhone\":\"\",\"customerCompanyName\":\"\",\"source\":\"store\",\"customerStatus\":\"\",\"customerTypes\":null,\"customerGroups\":null,\"isLoggedIn\":1,\"customerDocs\":\"\",\"taxExempt\":null,\"taxExemptID\":null,\"createdAt\":\"2024-05-16 11:11:53\"}",
    "dateCreated": 1719395153,
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

## Get All Quotes by Customer
This endpoint retrieves a list of quotes for a customer

### HTTP Request
`GET https://storeapi.csomni.com/checkout/po/{quoteToken}`

### Header Parameters
| Parameter     | Type   | Description       |
|---------------|--------|-------------------|
| token         | string | Site Token ID     |
| customerToken | string | Customer Token ID |

Sample in Shell:

```shell

curl --location --request GET 'https://storeapi.csomni.com/quotes/' \
--header 'token: site_xxxxxxxxxxxxxxxxxxx' \
--header 'customerToken: cs_GWdE9xY2dcL9qqBmNKx7WXivTh73nJtGH4NK'

```

Response:

```json
[
    {
        "quoteToken": "quote_bWFkhPpaL56P",
        "customerToken": "cs_GWdE9xY2dcL9qqBmNKx7WXivTh73nJtGH4NK",
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
            "customerToken": "cs_GWdE9xY2dcL9qqBmNKx7WXivTh73nJtGH4NK",
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
This endpoint searches by quote token and returns the single quote
### HTTP Request

`GET https://storeapi.csomni.com/quotes/{quoteToken}`

### URL Parameters
| Parameter     | Type   | Description       |
|---------------|--------|-------------------|
| quoteToken    | string | Quote Token ID    |

### Header Parameters
| Parameter     | Type   | Description       |
|---------------|--------|-------------------|
| token         | string | Site Token ID     |
| customerToken | string | Customer Token ID |

Sample in Shell:

```shell
curl --location --request GET 'https://storeapi.csomni.com/quotes/quote_bWFkhPpaL56P' \
--header 'token: site_xxxxxxxxxxxxxx' \
--header 'customerToken: cs_GWdE9xY2dcL9qqBmNKx7WXivTh73nJtGH4NK'
```

> The above command returns JSON structured like this:

```json
{
  "quoteToken": "quote_0vq9tiG0xNbf",
  "customerToken": "cs_GWdE9xY2dcL9qqBmNKx7WXivTh73nJtGH4NK",
  "quoteFiles": "",
  "status": "waiting-response",
  "deleted": 0,
  "dateCreated": "2024-06-24 20:53:48",
  "dateUpdated": "2024-06-24 20:53:49",
  "variantsTotal": 1.1,
  "shippingTotal": 0,
  "taxTotal": 0,
  "itemsCount": 2,
  "itemsQuantity": 4,
  "combinedTotal": null,
  "quoteNumber": "Q50166",
  "variantDetails": [
    {
      "quote_variantsToken": "quoteVariant_f23QCHKjg91K",
      "variantToken": "vrnt_EvonkJQsR6fRbDtm",
      "quantity": 2,
      "itemPrice": 0.3,
      "itemTax": 0,
      "lineTotal": 0.6,
      "fullDetails": {
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
        "prodName": "3\/4 IN. O.D. SATIN NICKEL DRIVE-IN, SPRING LOADED, BALL STYLE, CABINET DOOR LATCH WITH STRIKE\t"
      }
    },
    {
      "quote_variantsToken": "quoteVariant_XRtqphtqEtxU",
      "variantToken": "vrnt_OYIwevfBUfxErFG3",
      "quantity": 2,
      "itemPrice": 0.25,
      "itemTax": 0,
      "lineTotal": 0.5,
      "fullDetails": {
        "prodToken": "prod_FgNybasFJG4YUJ4h",
        "variantToken": "vrnt_OYIwevfBUfxErFG3",
        "variantName": "31\" WHITE CHINA SINK",
        "variantImage": {
          "file": "10-2-2022\/1664742840284__7264__VE3118W.jpg",
          "type": ""
        },
        "variantImages": [],
        "variantWeight": "0",
        "variantDimW": "0",
        "variantDimL": "0",
        "variantDimH": "0",
        "variantUpc": "",
        "variantNumber": "VE3118W",
        "manufacturerPartNumber": "",
        "variantPrice": 0.25,
        "variantMapPrice": 0,
        "variantMsrpPrice": 0,
        "variantDisplayPrice": 0,
        "variantDescription": "",
        "variantAlert": "",
        "variantLowlevel": "",
        "variantSlug": "31-white-china-sink",
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
        "inventoryCount": 180,
        "shippingProduct": 0,
        "variantMetaTitle": "",
        "variantMetaDescription": "",
        "variantBrand": "",
        "sortOrder": 0,
        "dateCreated": "1661531956",
        "deleted": 0,
        "backOrderWarning": 0,
        "createdAt": "2022-12-18 23:01:04",
        "editedAt": "2024-06-20 08:41:56",
        "variantInStock": true,
        "prodName": "31\" WHITE CHINA SINK"
      }
    }
  ],
  "shippingAddress": {
    "addressToken": "adrs_CJO9LkwmNJqSQmOBtaTsGE1w",
    "addressLabel": "Home Address",
    "address": "123 Main street",
    "address2": "Unit 4",
    "addressCity": "NY",
    "addressState": "NY",
    "addressZip": "10952",
    "addressFirstName": "Jane",
    "addressLastName": "Foster",
    "phoneNumber": "03356705565",
    "mobileNumber": "45678945666",
    "addressCountry": "United States",
    "addressDefault": 0,
    "createdAt": "2024-06-19 09:32:49",
    "editedAt": "2024-06-19 09:32:49",
    "specialValues": []
  },
  "contactDetails": {
    "quote_ContactToken": "quoteContact_dOV6xkMAQxIM",
    "firstName": "Sharon",
    "lastName": "Doe",
    "email": "sharondoe@gmail.com",
    "phoneNumber": "987657489",
    "companyName": "Techo"
  },
  "shippingQuote": []
}
```

## Delete a Specific quote
This endpoint deletes a quote

### HTTP Request
`DELETE https://storeapi.csomni.com/quotes/{quoteToken}`

Sample in Shell:

```shell
curl --location --request DELETE 'https://storeapi.csomni.com/quotes/quote_9Uih2O4wb9Ys' \
--header 'token: site_xxxxxxxxxxxxx' \
--header 'customerToken: cs_GWdE9xY2dcL9qqBmNKx7WXivTh73nJtGH4NK'
```

Response:

```json
{
  "token": "quote_9Uih2O4wb9Ys",
  "deleted": "true"
}
```