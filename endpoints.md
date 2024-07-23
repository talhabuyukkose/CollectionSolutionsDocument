<h1 align="center">RestApi EndPoints</h1>

## Contents 
*
*
*

## Activity

### Get an Activity using spesific Guid

| Parameter | Type | Description |
| :--- | :--- | :--- |
| `guid` | `string` | **Required** |

#### Request

`GET Activity/GetByGuid?guid`


    curl -i -H 'Accept: text/plain' 'http://home.ermanseneren.com:7020/api/v3/Activity/GetByGuid?guid=3fa85f64-5717-4562-b3fc-2c963f66afa6'


#### Response

     status: 200 OK
     content-type: application/json; charset=utf-8 
     date: Tue,23 Jul 2024 07:56:33 GMT 
     server: Kestrel 
     transfer-encoding: chunked 

### Get an Activity using spesific LoanAccount Guid

| Parameter | Type | Description |
| :--- | :--- | :--- |
| `guid` | `string` | **Required** |
| `offset`| `integer`||
| `limit`| `integer`||
| `activityTypeEnum`| `string`||
### Request

`GET Activity/GetByLoanAccountGuid?guid&Offset&Limit&activityTypeEnum`

    curl -i -H 'accept: text/plain' 'http://home.ermanseneren.com:7020/api/v3/Activity/GetByLoanAccountGuid?guid=c31ee961-9f19-49a0-a0cc-6a52f1ea303a&Offset=15&Limit=20&activityTypeEnum=CREATE'


### Response

     status: 200 OK
     content-type: application/json; charset=utf-8 
     date: Tue,23 Jul 2024 08:19:42 GMT 
     server: Kestrel 
     transfer-encoding: chunked
