#Authentication

## Sign up 

This API is used for the sign up.In this API not required to be passed in header section.

```shell
curl -X POST \
  http://base_url/signup \
  -H 'accept: application/json' \
  -H 'cache-control: no-cache' \
  -H 'content-type: application/json' \
   -d '{
	"user": {
		"name": "vikram",
		"email": "vikramkanav@gmail.com",
		"password": "xyz",
		"mobile_number": "9953055456"
	}
}'
```
>The above command returns JSON structured like this:

```json

{
    "user": {
      "name":"vikram",
      "email":"vikramkanav@gmail.com",
      "password":"xyz",
      "mobile_number":"9953055456"
    },
    "refresh_token":"refreshtoken1",
    "auth_token" :"authtoken1"
}
```

>The above command return the errors in json structure

```json

  {
  "errors":{
    "message" : "Please enter the valid email address, password & mobile number"
  }
 }
```

### HTTP Request

`POST http://base_url/api/signup`
 
### Parameters

    Parameter | type | Description | Required |	Default
    --------- | ------- | ----------- |-----------|---------
    name  | string  | User Name  | true      |
    email     | string  | Email address of the user | true |
    mobile_number | int | user mobile Number | true |
    password    | string | Password of the user     | true | 
    
<aside class="success">Status Code :200 OK </aside>
<aside class="warning">Error Code  :422 Unprocessable entity</aside>

## Sign In

This API is used for the Sign In. This is open API auth token is not to berequired to passed in Header

```shell
curl -X POST \
  http://base_url/signin \
  -H 'accept: application/json' \
  -H 'cache-control: no-cache' \
  -H 'content-type: application/json' \
  -d '{
	"user" :{
		 "email": "vikramkanav",
	      "password":"xyz",
	  }
}'
```

>The above command returns JSON structured like this:

```json

{
    "user": {
      "name":"vikram",
      "email":"vikramkanav@gmail.com",
      "password":"xyz",
      "mobile_number":"9953055456"
    },
    "refresh_token":"refreshtoken1",
    "auth_token" :"authtoken1"
}

```
> This returns the errors message in json  structured like this:

```json
  {
  	"errors": {
  		"message": "Please enter the valid email address and password"
  	}
  }
```


### HTTP Request

`POST http://base_url/api/signin`
 
### Parameters

    Parameter | type | Description | Required |	Default
    --------- | ------- | ----------- |-----------|---------
    email  | string  | email address of the user name   |  true     |
    password  | string  | User password   |  true     |


<aside class="success">Status Code :200 OK </aside>
<aside class="warning">Error Code  :422 Unprocessable entity</aside>
    
##Update Profile

This API is used for the update profile 

```shell
curl -X PUT \
  http://base_url/signup \
  -H 'accept: application/json' \
  -H 'authorization: Token token:\"authtoken2\"' \
  -H 'cache-control: no-cache' \
  -H 'content-type: application/json' \
  -d '{
	"user" :{
		 "user_name" :"vikram",
		"mobile_number": "9466205050",
	    "password":"xyzabc",
	  }
}'
```

>The above command returns JSON structured like this:

```json
 {
   "user": {
     "name":"vikram",
     "email": "vikramkanav@gmail.com",
     "mobile_number":"9466205050",
     "password": "abcxyz"  
     },
   }
```
>The above code returns errors in JSON structure 

```json
 {
   "errors": {
     "message":"Please enter the correct user name, mobile number & password"
      }
  }
```
### HTTP Request

`PUT http://base_url/api/user`

### Parameters

    Parameter | type | Description | Required |	Default
    --------- | ------- | ----------- |-----------|---------
    name  | string  | User name of the user   |  true     |
    mobile_number  | string  | Mobile number of the user   |  true     |
    password  | string  | password of the user   |  true     |
    password | string  | confirm password of the user   |  true     |
    
<aside class="success">Status Code :200 OK </aside>
<aside class="warning">error code  :401 unauthrized error </aside>
<aside class="warning">error code  :422 unprocessable entity </aside>


##Forget Password 

This API is used for the update profile 

```shell
curl -X POST \
  http://base_url/api/user/forget \
  -H 'accept: application/json' \
  -H 'cache-control: no-cache' \
  -H 'content-type: application/json' \
  -d '{
	"user" :{
      "email_address": "vikramkanav@gmail.com"
	  }
}'
```

>The above command returns JSON structured like this:

```json
 {
  "message":"Password is send on your email address"
  }
```
>The above code returns errors in JSON structure 

```json
 {
   "errors": {
     "message":"Please enter the correct email address" 
      }
  }
```
### HTTP Request

`POST http://base_url/api/user/forget`

### Parameters

    Parameter | type | Description | Required |	Default
    --------- | ------- | ----------- |-----------|---------
    email | string | user email address | true|
    
     
<aside class="success">Status Code :200 OK </aside>
<aside class="warning">Error code  :422 Unprocessable entity </aside>
