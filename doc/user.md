# User API Spec

## Register User

Endpoint : POST /api/users

Request Body :

```json
{
    "username" : "arya",
    "passoword" : "rahasia",
    "name" : "Arya Perdana Irawan"
}
```

Response Body (Success) :

```json
{
    "data" : {
        "username" : "arya",
        "name" : "Arya Perdana Irawan"
    }
}
```

Response Body (Failed) :

```json
{
    "errors" : "Username must not blank, ..."
}
```

## Login User

Endpoint : POST /api/users/login

Request Body :

```json
{
    "username" : "arya",
    "passoword" : "rahasia",
}
```

Response Body (Success) :

```json
{
    "data" : {
        "username" : "arya",
        "name" : "Arya Perdana Irawan",
        "token" : "uuid"
    }
}
```

Response Body (Failed) :

```json
{
    "errors" : "Username or password wrong, ..."
}
```


## Get User

Endpoint : GET /api/users/current

Request Body :

```json
{
    "username" : "arya",
    "passoword" : "rahasia",
    "name" : "Arya Perdana Irawan"
}
```

Response Body (Success) :

```json
{
    "data" : {
        "username" : "arya",
        "name" : "Arya Perdana Irawan"
    }
}
```

Response Body (Failed) :

```json
{
    "errors" : "Username must not blank, ..."
}
```

## Update User

Endpoint : PATCH /api/users/login

Request Header :
- X-API-TOKEN : token

Request Body :

```json
{
    "passoword" : "rahasia", // tidak wajib
    "name" : "Arya Perdana Irawan", // tidak wajib
}
```

Response Body (Success) :

```json
{
    "data" : {
        "username" : "arya",
        "name" : "Arya Perdana Irawan",
    }
}
```

Response Body (Failed) :

```json
{
    "errors" : "Unauthorized, ..."
}
```

## Logout User

Endpoint : DELETE /api/users/login

Request Header :
- X-API-TOKEN : token

Response Body (Success) :

```json
{
    "data" : "OK"
}
```

Response Body (Failed) :

```json
{
    "errors" : "Unauthorized, ..."
}
```