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

If the given guid is valid, it returns all the activities that match this guid. (Such as CREATE, CALL_AUTO, CALL_INBOUND, CALL_MANUAL, CALL_TRANSFER, CALL_CLOSE, ACT_MOVE, MEMO, SMS, EMAIL, PUSH, IVN)  
If this guid does not exist, it gives not found message with statusCode: 400.

#### Request

`GET Activity/GetByGuid?guid`


    curl -i -H 'Accept: text/plain' 'http://home.ermanseneren.com:7020/api/v3/Activity/GetByGuid?guid=3fa85f64-5717-4562-b3fc-2c963f66afa6'


#### Response

     status: 200 OK
     content-type: application/json; charset=utf-8 
     date: Tue,23 Jul 2024 07:56:33 GMT 
     server: Kestrel 
     transfer-encoding: chunked 
&nbsp;

     {
     "statusCode": 200,
     "message": "Activities have been get by guid(5dd3cec1-7aff-4b0e-b6f1-1e53e7d283c5)",
     "dateTime": "2024-07-23T08:56:16.5042445Z",
     "data": {...}
     }

### Get an Activity using spesific LoanAccount Guid

| Parameter | Type | Description |
| :--- | :--- | :--- |
| `guid` | `string` | **Required** |
| `offset`| `integer`||
| `limit`| `integer`||
| `activityTypeEnum`| `string`||

If the given loan guid is valid, it returns all the activities that match this guid. (Such as CREATE, CALL_AUTO, CALL_INBOUND, CALL_MANUAL, CALL_TRANSFER, CALL_CLOSE, ACT_MOVE, MEMO, SMS, EMAIL, PUSH, IVN)  
If this loan guid does not exist, it gives not found message with statusCode: 400.

### Request

`GET Activity/GetByLoanAccountGuid?guid&Offset&Limit&activityTypeEnum`

    curl -i -H 'accept: text/plain' 'http://home.ermanseneren.com:7020/api/v3/Activity/GetByLoanAccountGuid?guid=c31ee961-9f19-49a0-a0cc-6a52f1ea303a&Offset=15&Limit=20&activityTypeEnum=CREATE'


### Response

     status: 200 OK
     content-type: application/json; charset=utf-8 
     date: Tue,23 Jul 2024 08:19:42 GMT 
     server: Kestrel 
     transfer-encoding: chunked

&nbsp;

    {
    "totalRowCount": 0,
    "totalPageCount": 1,
    "offset": 0,
    "limit": 10,
    "statusCode": 400,
    "message": "Loan Account not found",
    "dateTime": "2024-07-23T10:45:14.6594402Z",
    "data": null
    }
     
