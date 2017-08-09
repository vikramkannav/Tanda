# Tanda 

## Create Tanda

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
	    "date": "12/03/2016"
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
    date  | date   | Tanda create date   | | current date

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
			"name": "tanda1",
			"tanda_date": "12/03/2016"
		},
		{
			"name": "tanda2",
			"tanda_date": "11/08/2016"
		},
		{
			"name": "tanda3",
			"tanda_date": "11/09/2016"
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
              
## Tanda Users

This is used for the list of the Tanda list.

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
   "users":[
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
              
