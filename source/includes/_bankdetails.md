#Bank Detail

##Bank Detail

This API is used for submit the Bank information.

```shell
curl -X POST \
  http://base_url/bankdetail \
  -H 'accept: application/json' \
  -H 'authorization: Token token:\"authtoken2\"' \
  -H 'cache-control: no-cache' \
  -H 'content-type: application/json' \
  -d '{
	"bankDetails": {
		"account_name": "vikram",
		"bank_name":"SBI",
		"account_number":"1204",
		"state_name":"Paris"
	}
}'
```   

>The above command returns JSON structured like this:

```json
{
	"bankDetails": {
		"account_name": "vikram",
		"bank_name":"SBI",
		"account_number":"1204",
		"state_name":"Paris"
		}
}
```
>The above code returns errors in JSON struture 

```json
 {
   "errors": {
     "message":"Please enter the correct account holder name ,bank name, account number & state name"
      }
  }
```
### HTTP Request

`POST http://base_url/api/bankdetail`

### Parameters

    Parameter | type | Description | Required |	Default
    --------- | ------- | ----------- |-----------|---------
    account_name  | string  | User bank account name   |  true     |
    bank_name  | string  | User bank name   |  true     |
    account_number  | int  | User Account Number   |  true     |
    state_name  | string  | User state name   |  true     |
    
<aside class="success">Status Code :200 OK </aside>
<aside class="warning">Error Code  :401 Unauthrized error</aside>
<aside class="warning">Error Code  :422 Unprocessable entity</aside>
    
