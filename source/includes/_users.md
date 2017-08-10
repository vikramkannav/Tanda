#Users

##Update profile

This API is used for the update profile by the user. 

```shell
curl -X PUT \
  http://base_url/users/:id \
  -H 'accept: application/json' \
  -H 'authorization: Token token:\"authtoken2\"' \
  -H 'cache-control: no-cache' \
  -H 'content-type: application/json' \
  -d '{
	"user": {
    	"name": "vikram",
    	"mobile_number": "9466205050",
    	"password": "xyzabc123",
    	"confirm_password": "xyzabc123",
    }
}'
```

>The above command returns in JSON structure:

```json
 {
 	"user": {
 		"name": "vikram",
 		"email": "vikramkanav@gmail.com",
 		"mobile_number": "9466205050",
 	 	}
 }
```
>The above code returns errors in JSON structure 

```json
 {
 	"errors": [{
 		"message": "Please enter the correct user name, mobile number & password"
 	}]
 }
```
### HTTP Request

`PUT http://base_url/users/:id`

### Parameters

    Parameter | type | Description | Required 
    --------- | ------- | ----------- |-----------
    name  | string  | Name of the user   |  true     
    mobile_number  | string  | Mobile number of the user  |  true     
    password  | string  | Password of the user   |  true     
    confirm_password | string  | Confirm password of the user   |  true     
    
<aside class="success">Status Code :200 OK </aside>
<aside class="warning">error code  :401 Unauthorized error </aside>
<aside class="warning">error code  :422 unprocessable entity </aside>


##Bank detail

This API is used for the submit the information of the bank with some details like account name, bank name, account number and state name.

```shell
curl -X POST \
  http://base_url/bankdetail/users/:id\
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

`POST http://base_url/bankdetail/users/:id`

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
    
## Invite users

This API is used to add user (send the request to the user) for the Tanda with the his/her mobile contact.

```shell
curl -X POST \
  http://base_url/tandas/:id/users \
  -H 'accept: application/json' \
  -H 'authorization: Token token:\"authtoken2\"' \
  -H 'cache-control: no-cache' \
  -H 'content-type: application/json' \
  "invite_users": {
  		      "mobile_number":"7838920202"
  		 	 	}
```    

>The above command returns in JSON structure: 

```json
   {
   	"invite_users": [{
   		"name": "Raj",
   		"mobile_number": "9898393362"
   	}, {
   		"name": "Parvesh",
   		"mobile": "9898367632"
   	}],
   
   
   	"users": [{
   		"name": "Shyam",
   		"mobile_number": "8393473877"
   	}, {
   		"name": "Jai",
   		"mobile_number": "7874738747"
   	}]
   }

``` 

### HTTP Request

`POST http://base_url/tandas/:id/users`

### Parameters

    Parameter | type | Description | Required 
    --------- | ------- | ----------- |-----------
    mobile_number     | string   | Mobile number in contact list   |           

<aside class="success">Status Code :200 OK </aside>
<aside class="warning">Error Code  :422 Unprocessable entity</aside>
    
## Tanda users

This API is used to list of user those are accepted and pending the acceptance of the this Tanda request.

```
shell
curl -X GET \
  http://base_url/tandas/:id/users \
  -H 'accept: application/json' \
  -H 'authorization: Token token:\"authtoken2\"' \
  -H 'cache-control: no-cache' \
  -H 'content-type: application/json' \
```    

>The above command returns in JSON structure:

```json
  {
  	"user": [{"name": "Breant Wells",
  			  "mobile_number": "411-906-6802",
  			  "status": "Accepted"},
       		{ "name": "Randy Gray",
  			  "mobile_number": "769-472-2464",
  			  "status": "Accepted"},
           	{"name": "Kenneth Chabers",
  			 "mobile_number": "452-702-8972",
  			 "status": "Pending"}]
  }
``` 

### HTTP Request

`GET http://base_url/tandas/:id/users`

### Parameters

    Parameter | type | Description | Required 
    --------- | ------- | ----------- |-----------
              |         |             |           

<aside class="success">Status Code :200 OK </aside>
<aside class="warning">Error Code  :401 Unauthorized error</aside>
