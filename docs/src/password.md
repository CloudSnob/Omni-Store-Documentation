# Password Reset

## Forgot Password
This endpoint triggers a reset email to the customers email address. The email contains a link to reset the password
Be careful, it always returns success even if email is not in our system vd"l

### HTTP Request

`POST https://storeapi.csomni.com/password/forgot`

### Header Parameters
| Parameter     | Required | Type   | Description       |
|---------------|----------|--------|-------------------|
| siteToken     | true     | string | Site ID token     |

### Data Parameters
| Parameter     | Required | Type   | Description                        |
|---------------|----------|--------|------------------------------------|
| customerEmail | true     | string | Email of account to reset password |
| siteToken     | true     | string | Site ID token                      |


```shell
curl --request POST \
  --url https://storeapi.csomni.com/password/forgot \
  --header 'token: site_xxxxxxxxx' \
  --data '{
            "customerEmail" : "test@gmail.com",
          }'
```

> The above command returns JSON structured like this:

```json
{
  "status": "success"
}
```

## Restore Password (from hash)
This endpoint resets a customers password. It requires a unique hash that is sent in the initial reset email

### HTTP Request

`POST https://storeapi.csomni.com/restorepassword`

### Header Parameters
| Parameter     | Required | Type   | Description       |
|---------------|----------|--------|-------------------|
| siteToken     | true     | string | Site ID token     |

### Data Parameters
| Parameter     | Required | Type   | Description                        |
|---------------|----------|--------|------------------------------------|
| customerEmail | true     | string | Email of account to reset password |
| siteToken     | true     | string | Site ID token                      |

```shell
curl --request POST \
  --url https://storeapi.csomni.com/restorepassword \
  --header 'token: site_xxxxxxxxx' \
  --data '{ 
            hash" : "pass_xxxxxxxxxxxxxxx", 
            "newPassword" : "test123!" 
          }'
```

> The above command returns JSON structured like this:

```json
{
  "status": "success"
}
```

