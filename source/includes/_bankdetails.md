#Bank detail

##Bank detail

This API is used for the submit the information of the bank with some details like account name, bank name, account number and state name.

```shell
curl -X POST \
  http://base_url/api/bankdetail\
  -H 'accept: application/json' \
  -H 'authorization: Token token:\"authtoken2\"' \
  -H 'cache-control: no-cache' \
  -H 'content-type: application/json' \
  -d '{
	"bankdetail": {
		"account_name": "vikram sharma",
		"bank_name":"SBI",
		"account_number":"1204",
		"state_name":"Haryana"
	}
}'
```   

>The above command returns in JSON structure:

```json
{
	"bankdetail": {
		"account_name": "vikram sharma",
		"bank_name": "SBI",
		"account_number": "1204",
		"state_name": "Harayana"
	}
}
```
>The above code returns errors in JSON structure 

```json
 {
 	"errors": [{
 		"message": "Please enter the correct account holder name ,bank name, account number & state name"
 	}]
 }
```
### HTTP Request

`POST http://base_url/api/bankdetail`

### Parameters

    Parameter | type | Description | Required 
    --------- | ------- | ----------- |-----------
    account_name  | string  | Account name of the user   |  true
    bank_name  | string  | Bank name of the user   |  true
    account_number  | int  | Account number of the user   |  true
    state_name  | string  | State name of the user  |  true     |
    
<aside class="success">Status Code :200 OK </aside>
<aside class="warning">Error Code  :401 Unauthorized error</aside>
<aside class="warning">Error Code  :422 Unprocessable entity</aside>
    
