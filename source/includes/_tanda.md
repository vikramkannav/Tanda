# Tanda 

## Create Tanda

This API is used for the  create Tanda. 

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

>The above code is return the json structure like 

```json
{
  "tanda" :{
  		"amount":"200",
  		"date": "sunday",
  	    "type": "weekly",
  	    "name": "Tanda 1"
  	  }
}
``` 

>The above code returns errors in JSON structure 

```json
```

### HTTP Request

`POST http://base_url/api/tanda`

### Parameters

    Parameter | type | Description | Required |	Default
    --------- | ------- | ----------- |-----------|---------
    amount| int   | Tanda amount | true  |
    tanda_day  | string  | Tanda date or day | true  |
    type  | string | Weekly or Monthly | true |
    name  | string | Tanda Name  | true  |
  
## Tanda List

This is used for the list of the Tanda list.

```shell
curl -X GET \
  http://base_url/api/tandas \
  -H 'accept: application/json' \
  -H 'authorization: Token token:\"authtoken2\"' \
  -H 'cache-control: no-cache' \
  -H 'content-type: application/json' \
```    

>The above code is return the json structure like 

```json
{
	"tanda_list": [{
			"name": "tanda1"
		},
		{
			"name": "tanda2"
		},
		{
			"name": "tanda3"
		}

	]
}
``` 

### HTTP Request

`GET http://base_url/api/tandas`

### Parameters

    Parameter | type | Description | Required |	Default
    --------- | ------- | ----------- |-----------|---------
              |         |             |           |
<aside class="success">Status Code :200 OK </aside>
<aside class="warning">Error Code  :422 Unprocessable entity</aside>

              
## Tanda Users

This API is used for the list of the Tanda users.

```shell
curl -X GET \
  http://base_url/api/tanda/:id/users \
  -H 'accept: application/json' \
  -H 'authorization: Token token:\"authtoken2\"' \
  -H 'cache-control: no-cache' \
  -H 'content-type: application/json' \
```    

>The above code is return the json structure like 

```json
  {
   "user":[
       {
       "name":"Breant Wells",
       "mobile_number":"411-906-6802",
       "status": "Accepted"
       },
       
      {
        "name":"Randy Gray",
        "mobile_number": "769-472-2464",
        "status": "Accepted"
       },
       
       {
        "name":"Kenneth Chabers",
        "mobile_number":"452-702-8972",
        "status": "Pending"
        }
        ]
   }
``` 

### HTTP Request

`GET http://base_url/api/tanda/:id/users`

### Parameters

    Parameter | type | Description | Required |	Default
    --------- | ------- | ----------- |-----------|---------
              |         |             |           |

<aside class="success">Status Code :200 OK </aside>
<aside class="warning">Error Code  :401 Unauthorized error</aside>
              
## Tanda Payment

This is API used for the list of the Tanda list.

```shell
curl -X POST \
  http://base_url/api/tanda/:id/payment \
  -H 'accept: application/json' \
  -H 'authorization: Token token:\"authtoken2\"' \
  -H 'cache-control: no-cache' \
  -H 'content-type: application/json' \
```    

>The above code is return the json structure like 

```json
{
 "message" :"Payement is done Successfully"
}

``` 

### HTTP Request

`POST http://base_url/api/tanda/:id/payment`

### Parameters

    Parameter | type | Description | Required |	Default
    --------- | ------- | ----------- |-----------|---------
              |         |             |           |
<aside class="success">Status Code :200 OK </aside>
<aside class="warning">Error Code  :401 Unauthorized error</aside>
<aside class="warning">Error Code  :422 Unprocessable entity</aside>



## Tanda Add user

This is API used  for add user in Tanda.

```shell
curl -X POST \
  http://base_url/api/tanda/:id/users \
  -H 'accept: application/json' \
  -H 'authorization: Token token:\"authtoken2\"' \
  -H 'cache-control: no-cache' \
  -H 'content-type: application/json' \
```    

>The above code is return the json structure like 

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

    Parameter | type | Description | Required |	Default
    --------- | ------- | ----------- |-----------|---------
              |         |             |           |

<aside class="success">Status Code :200 OK </aside>
<aside class="warning">Error Code  :422 Unprocessable entity</aside>
    

