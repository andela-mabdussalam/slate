---
title: API Reference

language_tabs:
  - javascript

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Document Management System

Welcome to the DocManager API. You can use our API to access various endpoints to create, edit and delete documents.

Endpoints data is returned in JSON format and error messages are displayed when there are errors with the request.

Pls report any errors or concerns

# Roles

## CREATE A ROLE

```javascript
curl -i -X POST https://docmanager1.herokuapp.com/api/roles” \
-H "token: dfsa09gmkdsglkdsg343242a32a.xlkdsfiosdf"
```

> The above command returns JSON structured like this:

```json
{
    "id": 3,
    "title": "elder",
    "updatedAt": "2017-04-10T21:39:22.166Z",
    "createdAt": "2017-04-10T21:39:22.166Z"
}
```

This endpoint returns all roles in the database.

### HTTP Request

`GET https://docmanager1.herokuapp.com/api/roles`

### Verbs, Response
GET ,  201

### Headers

Header    | Description
--------- | -------
token | valid user token

### Note
Only admin users are allowed to hit this endpoint, Unauthorized users get a 401 response

<aside class="success">
token should be added in the format 'authorization: token'
</aside>

## GET ALL ROLES

```javascript
curl -i -X GET https://docmanager1.herokuapp.com/api/roles” \
-H "token: dfsa09gmkdsglkdsg343242a32a.xlkdsfiosdf"
```

> The above command returns JSON structured like this:

```json
[
    {
        "id": 1,
        "title": "admin",
        "createdAt": "2017-04-10T19:29:41.367Z",
        "updatedAt": "2017-04-10T19:29:41.367Z"
    },
    {
        "id": 2,
        "title": "regular",
        "createdAt": "2017-04-10T19:29:41.367Z",
        "updatedAt": "2017-04-10T19:29:41.367Z"
    }
]
```

This endpoint returns all roles in the database.

### HTTP Request

`GET https://docmanager1.herokuapp.com/api/roles`

### Verbs, Response
GET ,  201

### Headers

Header    | Description
--------- | -------
token | valid user token

### Note
Only admin users are allowed to hit this endpoint, Unauthorized users get a 401 response

<aside class="success">
token should be added in the format 'authorization: token'
</aside>

## GET ONE ROLE

```javascript
curl -i -X GET https://docmanager1.herokuapp.com/api/roles/:id” \
-H "token: dfsa09gmkdsglkdsg343242a32a.xlkdsfiosdf"

```

> The above command returns JSON structured like this:

```json
{
    "id": 1,
    "title": "admin",
    "createdAt": "2017-04-10T19:29:41.367Z",
    "updatedAt": "2017-04-10T19:29:41.367Z"
}
```

This endpoint returns all the role with the specified id

### HTTP Request

`GET https://docmanager1.herokuapp.com/api/roles/:id`

### Verbs, Response
GET ,  201

### Headers

Header    | Description
--------- | -------
token | valid user tokens

### Query Parameters

Parameter    | Required | Description
--------- | -------  | ----------
id     | yes  |  id of the role to be retrieved

### Note
Only admin users are allowed to hit this endpoint

<aside class="success">
token should be added in the format 'authorization: token'
</aside>

## EDIT A ROLE

```javascript
curl -i -X PUT -d "title=king" https://docmanager1.herokuapp.com/api/roles/2 \
-H "token: dfsa09gmkdsglkdsg343242a32a.xlkdsfiosdf"
```

> The above command returns JSON structured like this:

```json
{
    "id": 2,
    "title": "king",
    "createdAt": "2017-04-10T19:29:41.367Z",
    "updatedAt": "2017-04-10T21:31:19.798Z"
}
```

This endpoint returns all the role with the specified id

### HTTP Request

`PUT https://docmanager1.herokuapp.com/api/roles/:id`

### Verbs, Response
PUT ,  201

### Headers

Header    | Description
--------- | -------
token | valid user tokens

### Query Parameters

Parameter    | Required | Description
--------- | -------  | ----------
id     | yes  |  id of the role to be edited

### Note
Only admin users are allowed to hit this endpoint

<aside class="success">
token should be added in the format 'authorization: token'
</aside>

## DELETE A ROLE

```javascript
curl -i -X PUT -d "title=king" https://docmanager1.herokuapp.com/api/roles/3 \
-H "token: dfsa09gmkdsglkdsg343242a32a.xlkdsfiosdf"
```

> The above command returns JSON structured like this:

```json
{
    "message": "Succesfully deleted role"
}
```

This endpoint returns all the role with the specified id

### HTTP Request

`DELETE https://docmanager1.herokuapp.com/api/roles/:id`

### Verbs, Response
DELETE ,  201

### Headers

Header    | Description
--------- | -------
token | valid user tokens

### Query Parameters

Parameter    | Required | Description
--------- | -------  | ----------
id     | yes  |  id of the role to be deleted

### Note
Only admin users are allowed to hit this endpoint

<aside class="success">
token should be added in the format 'authorization: token'
</aside>

# Users

## CREATE A USER

```javascript
curl -i -X POST -d "userName=joys&firstName=ekums&lastName=toriolal&email=ekumtoriolau \
@gmail.comekumtoriolau@gmail.com&password=1234567890&passwordConfirm=1234567890&roleId=2 \
https://docmanager1.herokuapp.com/users \
```

> The above command returns JSON structured like this:

```json
{
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VyTmFtZSI6ImpveXMiLCJlbWFpbCI6ImVrdW10b3Jpb2xhdUBnbWFpbC5jb20iLCJ1c2VyUm9sZUlkIjoyLCJ1c2VySWQiOjQsImlhdCI6MTQ5MTg2MjIxNiwiZXhwIjoxNDkxOTQ4NjE2fQ.RzPj4JhAso79iYexfrY5O0m10vbIrpTX-_Hi1SHu3Rw",
    "expiresIn": 86400,
    "user": {
        "id": 4,
        "userName": "joys",
        "firstName": "ekums",
        "lastName": "toriolal",
        "email": "ekumtoriolau@gmail.com",
        "userRoleId": 2,
        "createdAt": "2017-04-10T22:10:16.040Z"
    }
}
```

This endpoint returns all the role with the specified id

### HTTP Request

`POST https://docmanager1.herokuapp.com/api/users`

### Verbs, Response
GET ,  201

### Query Parameters

Parameter    | Required | Description
--------- | -------  | ----------
userName     | yes  |  a valid name
firstName    | yes  |  a valid firstname
lastName     | yes  |  a valid lastname
email        | yes  |  a valid email
password     | yes  |  a valid passowrd(must be at least 8 characters)
passwordConfirm | yes | must be same as the password
roleId       | no   | If not specified, defaults to regular


<aside class="success">
Success message would be received on successful login
</aside>

## USER LOGIN

```javascript
curl -i -X POST -d "identifier=ekumtoriolau@gmail.com&password=1234567890" \
https://docmanager1.herokuapp.com/users/login \
```

> The above command returns JSON structured like this:

```json
{
    "usertoken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOjQsInVzZXJOYW1lIjoiam95cyIsInVzZXJSb2xlSWQiOjIsImlhdCI6MTQ5MTg2Mjc2OSwiZXhwIjoxNDkxOTQ5MTY5fQ.MDH52uGpOazUWUs0YgYjFzYpvDMX_5O-WXQyS2y7MX8",
    "message": "Login Successful"
}
```

This endpoint returns all the role with the specified id

### HTTP Request

`GET https://docmanager1.herokuapp.com/api/roles/:id`

### Verbs, Response
GET ,  201

### Headers

Parameter    | Required | Description
--------- | -------  | ----------
identifier     | yes  |  the email or the username
password    | yes  |  password

### Note
Only admin users are allowed to hit this endpoint

<aside class="success">
token should be added in the format 'authorization: token'
</aside>

## USER LOGOUT

```javascript
curl -i -X POST https://docmanager1.herokuapp.com/users/logout
```

> The above command returns JSON structured like this:

```json
{
 "message": "User logged out"
}
```

This endpoint returns logouts a user

### HTTP Request

`POST https://docmanager1.herokuapp.com/api/users/logout`

### Verbs, Response
POST ,  201

### Headers

Header    | Description
--------- | -------
token | valid user token

### Note
Only admin users are allowed to hit this endpoint

<aside class="success">
token should be added in the format 'authorization: token'
</aside>

## GET ALL USERS

```javascript
curl -i -X GET https://docmanager1.herokuapp.com/users
```

> The above command returns JSON structured like this:

```json
{
    "users": [
        {
            "id": 1,
            "userName": "Izaiah93",
            "firstName": "Flavio",
            "lastName": "Gusikowski",
            "email": "Dianna_Windler@hotmail.com",
            "roleId": 1,
            "createdAt": "2017-04-10T19:29:41.437Z",
            "updatedAt": "2017-04-10T19:29:41.437Z",
            "Role": {
                "title": "admin"
            }
        },
        {
            "id": 4,
            "userName": "joys",
            "firstName": "ekums",
            "lastName": "toriolal",
            "email": "ekumtoriolau@gmail.com",
            "roleId": 2,
            "createdAt": "2017-04-10T22:10:16.040Z",
            "updatedAt": "2017-04-10T22:10:16.040Z",
            "Role": {
                "title": "king"
            }
        },
        {
            "id": 3,
            "userName": "London.Hamill51",
            "firstName": "Reta",
            "lastName": "Rau",
            "email": "Birdie_Spinka78@yahoo.com",
            "roleId": 2,
            "createdAt": "2017-04-10T19:29:41.722Z",
            "updatedAt": "2017-04-10T19:29:41.722Z",
            "Role": {
                "title": "king"
            }
        },
        {
            "count": 3
        }
    ]
}
```

This endpoint returns all the users

### HTTP Request

`GET https://docmanager1.herokuapp.com/users/?limit={integer}&offset={integer}`

### Verbs, Response
GET ,  201

### Headers

Header    | Description
--------- | -------
token | valid user tokens

### Note
Only admin users are allowed to hit this endpoint

<aside class="success">
token should be added in the format 'authorization: token'
</aside>

## GET ONE USER

```javascript
curl -i -X POST https://docmanager1.herokuapp.com/users/logout
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint returns all the role with the specified id

### HTTP Request

`GET https://docmanager1.herokuapp.com/api/roles/:id`

### Verbs, Response
GET ,  201

### Headers

Header    | Description
--------- | -------
token | valid user tokens

### Note
Only admin users are allowed to hit this endpoint

<aside class="success">
token should be added in the format 'authorization: token'
</aside>

## EDIT A USER

```javascript
curl -i -X PUT -d "firstName=mark" https://docmanager1.herokuapp.com/users/:id \
-H "token: dfsa09gmkdsglkdsg343242a32a.xlkdsfiosdf"
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint returns all the role with the specified id

### HTTP Request

`GET https://docmanager1.herokuapp.com/api/roles/:id`

### Verbs, Response
GET ,  201

### Headers

Header    | Description
--------- | -------
token | valid user tokens

### Note
Only admin users are allowed to hit this endpoint

<aside class="success">
token should be added in the format 'authorization: token'
</aside>

## DELETE A USER

```javascript
curl -i -X PUT -d "firstName=mark" https://docmanager1.herokuapp.com/users/:id \
-H "token: dfsa09gmkdsglkdsg343242a32a.xlkdsfiosdf"
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint deletes the user with the specified id

### HTTP Request

`GET https://docmanager1.herokuapp.com/api/roles/:id`

### Verbs, Response
GET ,  201

### Headers

Header    | Description
--------- | -------
token | valid user tokens

### Note
Only admin users are allowed to hit this endpoint

<aside class="success">
token should be added in the format 'authorization: token'
</aside>

# Document

## Create a Document

```javascript
curl -i -X PUT -d "firstName=mark" https://docmanager1.herokuapp.com/users/:id \
-H "token: dfsa09gmkdsglkdsg343242a32a.xlkdsfiosdf"
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint retrieves all kittens.

### HTTP Request

`GET http://example.com/api/kittens`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.


## Edit a document

```javascript
curl -i -X PUT -d "content=gkmdkgdfkgkd" https://docmanager1.herokuapp.com/api/documents/:id \
-H "token: dfsa09gmkdsglkdsg343242a32a.xlkdsfiosdf"
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint returns all the role with the specified id

### HTTP Request

`GET https://docmanager1.herokuapp.com/api/roles/:id`

### Verbs, Response
GET ,  201

### Headers

Header    | Description
--------- | -------
token | valid user tokens

### Note
Only admin users are allowed to hit this endpoint

<aside class="success">
token should be added in the format 'authorization: token'
</aside>

## Delete a document

```javascript
curl -i -X PUT -d "name=Have a baby" https://antbucket.herokuapp.com/api/v1/bucket_lists/1 \
-H "token: 029kdfsa0932a.xlkdsfiosdfds"
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint returns all the role with the specified id

### HTTP Request

`GET https://docmanager1.herokuapp.com/api/roles/:id`

### Verbs, Response
GET ,  201

### Headers

Header    | Description
--------- | -------
token | valid user tokens

### Note
Only admin users are allowed to hit this endpoint

<aside class="success">
token should be added in the format 'authorization: token'
</aside>



