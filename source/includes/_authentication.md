#Authentication

## Sign up 

The sign up API is used for the user sign up. 

This is open API and auth-token is not required to be passed in the header section.   

```shell
curl -X POST \
  http://base_url/api/signup \
  -H 'accept: application/json' \
  -H 'cache-control: no-cache' \
  -H 'content-type: application/json' \
   -d '{
	"user": {
    		"name": "vikram",
    		"email": "vikramkanav@gmail.com",
    		"password": "xyzxyz",
    		"mobile_number": "9953055456"
    	}
}'
```

>The above command returns in JSON structure:

```json
{
	"user": {
		"name": "vikram",
		"email": "vikramkanav@gmail.com",
		"password": "xyzxyz",
		"mobile_number": "9953055456"
	},
	"refresh_token": "refreshtoken1",
	"auth_token": "authtoken1"
}
```

>The above command returns errors in JSON structure:

```json

  {
  	"errors": [{
  		"message": "Please enter the valid email address, password & mobile number"
  	}]
  }
```

### HTTP Request

`POST http://base_url/api/signup`
 
### Parameters

    Parameter | type | Description | Required 
    --------- | ------- | ----------- |-----------
    name  | string  | Name of the user  | true      
    email     | string  | Email address of the user | true 
    mobile_number | int | Mobile number of the user| true
    password    | string | Password of the user| true 
    
<aside class="success">Status Code :200 OK </aside>
<aside class="warning">Error Code  :422 Unprocessable entity</aside>


## Sign in

The sign in API is used for the user sign in.

This is open API and auth-token is not required to be passed in the header section. 

```shell
curl -X POST \
  http://base_url/api/signin \
  -H 'accept: application/json' \
  -H 'cache-control: no-cache' \
  -H 'content-type: application/json' \
  -d '{
	"user" :{
		 "email": "vikramkanav",
	      "password":"xyzxyz"
	  }
}'
```

>The above command return in JSON structure:

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
>The above command return errors in JSON structure:

```json
  {
  	"errors": [{
  		"message": "Please enter the valid email address and password"
  	}]
 
  }
```


### HTTP Request

`POST http://base_url/api/signin`
 
### Parameters

    Parameter | type | Description | Required 
    --------- | ------- | ----------- |-----------
    email  | string  | Email address of the user  |  true
    password  | string  | Password of the user   |  true


<aside class="success">Status Code :200 OK </aside>
<aside class="warning">Error Code  :422 Unprocessable entity</aside>
    
##Forget password 

This API is used to reset the password with forget password option with an email address.

This is open API and auth-token is not required to be passed in the header section. 


```shell
curl -X POST \
  http://base_url/api/forget \
  -H 'accept: application/json' \
  -H 'cache-control: no-cache' \
  -H 'content-type: application/json' \
  -d '{
	"user" :{
      "email": "vikramkanav@gmail.com"
	  }
}'
```

>The above command returns in JSON structure:

```json
 {
 	"message": "Password is send on your email address"
 }
```
>The above code returns errors in JSON structure 

```json
 {
 	"errors": [{
 		"message": "Please enter the correct email address"
 	}]
 }
```
### HTTP Request

`POST http://base_url/api/forget`

### Parameters

    Parameter | type | Description | Required 
    --------- | ------- | ----------- |-----------
    email | string | Email address of the user | true|
    
       
<aside class="success">Status Code :200 OK </aside>
<aside class="warning">Error code  :422 Unprocessable entity </aside>


##Retrieve access token 

This API is used for the retrieve the access token with help of refresh token.

```shell
curl -X POST \
  http://base_url/api/:id/refresh_token \
  -H 'accept: application/json' \
  -H 'authorization: Refresh Token:\"refreshtoken1\"' \
  -H 'cache-control: no-cache' \
  -H 'content-type: application/json' \
   {
   	"refresh_token":"refreshtoken1"
   }
```
>The above command returns in JSON structure:

```json
{
	"user": {
		"name": "vikram",
		"email": "vikramkanav@gmail.com",
		"password": "xyz",
		"mobile_number": "9953055456"
	},
	"refresh_token": "refreshtoken2",
	"auth_token": "authtoken2"
}
```
### HTTP Request

`POST http://base_url/api/:id/refresh_token`

### Parameters

    Parameter | type | Description | Required 
    --------- | ------- | ----------- |-----------
     refresh_token| string |Refresh token of the user|true               |           |