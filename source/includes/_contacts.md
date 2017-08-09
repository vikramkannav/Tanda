#Contacts

##Contact List 

This API is used for the list of the contacts in mobile.

```shell
curl -X GET \
  http://base_url/api/contacts \
  -H 'accept: application/json' \
  -H 'authorization: Token token:\"authtoken2\"' \
  -H 'cache-control: no-cache' \
  -H 'content-type: application/json' \

```
>The above command returns JSON structured like this:

```json
  {
  	"contacts": [{
  			"name": "smith",
  			"mobile_number": "8739303033"
  		},
  		{
  			"name": "rsath",
  			"mobile_number": "7437030364"
  		},
  		{
  			"name": "john",
  			"mobile_number": "9747830364"
  		},
  		{
  			"name": "david",
  			"mobile_number": "8789030364"
  		}
  	]
  }

```

>The above command return the errors in json structure

```json

```

### HTTP Request

`GET http://base_url/api/contacts`
 
### Parameters

    Parameter | type | Description | Required |	Default
    --------- | ------- | ----------- |-----------|---------
    
<aside class="success">Status Code :200 OK </aside>
<aside class="warning"> </aside>

