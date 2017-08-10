# Tanda 

## Create Tanda

This API is used for the create Tanda.

User can create Tanda with some information like name, Amount, 
day (weekday) or date (month, date) of Tanda, type (weekly or monthly)

```shell
curl -X POST \
  http://base_url/api/tanda \
  -H 'accept: application/json' \
  -H 'authorization: Token token:\"authtoken2\"' \
  -H 'cache-control: no-cache' \
  -H 'content-type: application/json' \
  -d '{
	"tanda" :{
		"amount":"200",
		"tanda_day": "sunday",
	    "type": "weekly",
	    "name": "Tanda 1",
	  }
}'
```

>The above command returns in JSON structure:

```json
{
	"tanda": {
		"amount": "200",
		"date": "sunday",
		"type": "weekly",
		"name": "Tanda 1"
	}
}
``` 

### HTTP Request

`POST http://base_url/api/tanda`

### Parameters

    Parameter | type | Description | Required 
    --------- | ------- | ----------- |-----------
    amount| int   | Amount of Tanda  | true  
    tanda_day  | string  | Date or day of the Tanda | true  
    type  | string | Tanda type weekly or monthly | true 
    name  | string | Name of Tanda  | true  

<aside class="success">Status Code :200 OK </aside>
<aside class="warning">Error Code  :401 Unauthorized error</aside>

  
## Tanda list

The API is used to show the list of Tanda with Tanda name, 
Start date of the Tanda & total number of users in Tanda.

```shell
curl -X GET \
  http://base_url/api/tandas \
  -H 'accept: application/json' \
  -H 'authorization: Token token:\"authtoken2\"' \
  -H 'cache-control: no-cache' \
  -H 'content-type: application/json' \
```    

>TThe above command returns in JSON structure:

```json
{
  "tanda_list":   [{"name": "tanda1"},
				   {"name": "tanda2"},
		           {"name": "tanda3"}]
}
``` 

### HTTP Request

`GET http://base_url/api/tandas`

### Parameters

    Parameter | type | Description | Required 
    --------- | ------- | ----------- |-----------
              |         |             |           
<aside class="success">Status Code :200 OK </aside>
<aside class="warning">Error Code  :422 Unprocessable entity</aside>

              
## Tanda users

This API is used to list of user those are accepted and pending the acceptance of the this Tanda request.

```
shell
curl -X GET \
  http://base_url/api/tanda/:id/users \
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

`GET http://base_url/api/tanda/:id/users`

### Parameters

    Parameter | type | Description | Required 
    --------- | ------- | ----------- |-----------
              |         |             |           

<aside class="success">Status Code :200 OK </aside>
<aside class="warning">Error Code  :401 Unauthorized error</aside>
               
## Tanda payment

This API is used to pay of the Tanda.

```shell
curl -X POST \
  http://base_url/api/tanda/:id/payment \
  -H 'accept: application/json' \
  -H 'authorization: Token token:\"authtoken2\"' \
  -H 'cache-control: no-cache' \
  -H 'content-type: application/json' \
```    

>The above command returns in JSON structure:

```json
{
 "message" :"Payment is done successfully"
}

``` 

### HTTP Request

`POST http://base_url/api/tanda/:id/payment`

### Parameters

    Parameter | type | Description | Required 
    --------- | ------- | ----------- |-----------
              |         |             |           


<aside class="success">Status Code :200 OK </aside>
<aside class="warning">Error Code  :401 Unauthorized error</aside>
<aside class="warning">Error Code  :422 Unprocessable entity</aside>



## Tanda add user

This API is used to add user (send the request to the user) for the Tanda with the his/her mobile contact.

```shell
curl -X POST \
  http://base_url/api/tanda/:id/users \
  -H 'accept: application/json' \
  -H 'authorization: Token token:\"authtoken2\"' \
  -H 'cache-control: no-cache' \
  -H 'content-type: application/json' \
```    

>The above command returns in JSON structure: 

```json
   {
   	"invite_user": [{
   		"name": "Raj",
   		"mobile_number": "9898393362"
   	}, {
   		"name": "Parvesh",
   		"mobile": "9898367632"
   	}]
   } 
   {
      	"user": [{
   		"name": "Shyam",
   		"mobile_number": "8393473877"
   	} {
   		"name": "Jai",
   		"mobile_number": "7874738747"
   	}]
   }

``` 

### HTTP Request

`POST http://base_url/api/tanda/:id/users`

### Parameters

    Parameter | type | Description | Required 
    --------- | ------- | ----------- |-----------
              |         |             |           

<aside class="success">Status Code :200 OK </aside>
<aside class="warning">Error Code  :422 Unprocessable entity</aside>
    

