# Tanda 

## Create Tanda

This API is used for the create Tanda.

User can create Tanda with some information like name, Amount, 
day (weekday) or date (month, date) of Tanda, type (weekly or monthly)

```shell
curl -X POST \
  http://base_url/tanda \
  -H 'accept: application/json' \
  -H 'authorization: Token token:\"authtoken2\"' \
  -H 'cache-control: no-cache' \
  -H 'content-type: application/json' \
  -d '{
	"tanda" :{
		"amount":"200",
		"day": "4",
	    "kind": "weekly",
	    "name": "Tanda 1",
	  }
}'
```

>The above command returns in JSON structure:

```json
{
	"tanda": {
		"amount": "200",
		"day": "4",
		"kind": "weekly",
		"name": "Tanda 1"
	}
}
``` 

### HTTP Request

`POST http://base_url/tanda`

### Parameters

    Parameter | type | Description | Required 
    --------- | ------- | ----------- |-----------
    amount| int   | Amount of Tanda  | true  
    day  | string  | Date (0-28)or day(0-6) | true  
    kind  | string | Tanda kind weekly or monthly | true 
    name  | string | Name of Tanda  | true  

<aside class="success">Status Code :200 OK </aside>
<aside class="warning">Error Code  :401 Unauthorized error</aside>

  
## Tanda list

The API is used to show the list of Tanda with Tanda name, 
Start date of the Tanda & total number of users in Tanda.

```shell
curl -X GET \
  http://base_url/tandas \
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

`GET http://base_url/tandas`

### Parameters

    Parameter | type | Description | Required 
    --------- | ------- | ----------- |-----------
              |         |             |           
<aside class="success">Status Code :200 OK </aside>
<aside class="warning">Error Code  :422 Unprocessable entity</aside>
               
## Tanda payment

This API is used to pay of the Tanda.

```shell
curl -X POST \
  http://base_url/tandas/:id/payment \
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

`POST http://base_url/tandas/:id/payment`

### Parameters

    Parameter | type | Description | Required 
    --------- | ------- | ----------- |-----------
              |         |             |           


<aside class="success">Status Code :200 OK </aside>
<aside class="warning">Error Code  :401 Unauthorized error</aside>
<aside class="warning">Error Code  :422 Unprocessable entity</aside>




