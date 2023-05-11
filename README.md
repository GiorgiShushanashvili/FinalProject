# FinalProject

This is application for loans that have its users and accountants as well.
API to a Loan-Api Model.

The entire application is contained within the `app.rb` file.

`config.ru` is a minimal Rack configuration for unicorn.
used fluentvalidation

## Install

    nuget packages:
    serilog
    entity framework
    jwt bearer

## Run the app

    unicorn -p 7000

## Run the tests

    

# REST API

The REST API to the example app is described below.

## Get list of Things

### Request

`GET /thing/`

    curl -i -H 'Accept: application/json' http://localhost:7000/thing/

### Response

    HTTP/1.1 200 OK
    Date: Thu, 11 Feb 2023 11:36:30 GMT
    Status: 200 OK
    Connection: close
    Content-Type: application/json
    Content-Length: 2

    []

## Create a new Thing

### Request

`POST /thing/`

    curl -i -H 'Accept: application/json' -d 'name=Foo&status=new' (https://localhost:7014/api/controller/login/accountant?)

### Response

    HTTP/1.1 201 Created
    Date: Thu, 24 Feb 2011 12:36:30 GMT
    Status: 201 Created
    Connection: close
    Content-Type: application/json
    Location: /thing/1
    Content-Length: 36

    {"id":1,"name":"Foo","status":"new"}
    
    
### Request

`Put /thing/`

    curl -i -H 'Accept: application/json' -d 'name=Foo&status=new' https://localhost:7014/api/controller/delete/loan

### Response

    HTTP/1.1 201 Created
    Date: Thu, 24 Feb 2011 12:36:30 GMT
    Status: 201 Created
    Connection: close
    Content-Type: application/json
    Location: /thing/1
    Content-Length: 36

    {"id":1,"name":"Foo","status":"new"}
    

### Request

`GET /thing/id`

    curl -i -H 'Accept: application/json' [http://localhost:7000/thing/1](https://localhost:7014/api/controller/getloan/1)

### Response

    HTTP/1.1 200 OK
    Date: Thu, 24 Feb 2011 12:36:31 GMT
    Status: 200 OK
    Connection: close
    Content-Type: application/json
    Content-Length: 40

    {"id":1,"name":"Foo","status":"changed"}



### Response

    HTTP/1.1 200 OK
    Date: Thu, 24 Feb 2011 12:36:32 GMT
    Status: 200 OK
    Connection: close
    Content-Type: application/json
    Content-Length: 41

    {"id":1,"name":"Foo","status":"changed4"}

## Change a Thing using the _method hack in the url

### Request

`POST /thing/:id?_method=POST`

    curl -i -H 'Accept: application/json' -X POST -d 'name=Qux' https://localhost:7014/api/controller/update/user

### Response

    HTTP/1.1 404 Not Found
    Date: Thu, 24 Feb 2011 12:36:32 GMT
    Status: 404 Not Found
    Connection: close
    Content-Type: text/html;charset=utf-8
    Content-Length: 35

    {"status":404,"reason":"Not found"}

### Request

`GET /thing/1`

    curl -i -H 'Accept: application/json' https://localhost:7014/api/controller/getuser/1

### Response

    HTTP/1.1 404 Not Found
    Date: Thu, 11 May 2023 12:36:33 GMT
    Status: 404 Not Found
    Connection: close
    Content-Type: application/json
    Content-Length: 35

    {"status":404,"reason":"Not found"}

## Delete a Thing using the _method hack

### Request

`DELETE /thing/id`

    curl -i -H 'Accept: application/json' -X Patch -d'_method=DELETE' https://localhost:7014/api/controller/delete/loan

### Response

    HTTP/1.1 204 No Content
    Date: Thu, 24 Feb 2011 12:36:33 GMT
    Status: 204 No Content
    Connection: close

