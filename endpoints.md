<h1 align="center">RestApi EndPoints</h1>

## Contents 
*
*
*

## Activity

### Get Activities using spesific Guid

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
&nbsp;

    {
    "statusCode": 400,
    "message": "Entity with guid 5dd3cec1-7aff-4b0e-b6f1-1e53e7d283c7 not found.",
    "dateTime": "2024-07-23T11:32:52.4112969Z",
    "data": null
    }

### Get Activities using spesific LoanAccount Guid

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

### Get Activities using spesific Person Guid

| Parameter | Type | Description |
| :--- | :--- | :--- |
| `guid` | `string` | **Required** |
| `offset`| `integer`||
| `limit`| `integer`||
| `activityTypeEnum`| `string`||

If the given person guid is valid, it returns all the activities that match this guid. (Such as CREATE, CALL_AUTO, CALL_INBOUND, CALL_MANUAL, CALL_TRANSFER, CALL_CLOSE, ACT_MOVE, MEMO, SMS, EMAIL, PUSH, IVN)  
If this person guid does not exist, it gives not found message with statusCode: 400.


### Request

`GET GetByPersonGuid?guid&Offset&Limit&activityTypeEnum`

    curl -X 'GET' \
    'http://home.ermanseneren.com:7020/api/v3/Activity/GetByPersonGuid?guid=b746b5a2-252a-4895-9669-a32f4e806637&Offset=5&Limit=15&activityTypeEnum=CALL_AUTO' \
    -H 'accept: text/plain'

### Response

    status:200 OK
    content-type: application/json; charset=utf-8 
    date: Tue,23 Jul 2024 11:38:38 GMT 
    server: Kestrel 
    transfer-encoding: chunked 

&nbsp;

    {
    "totalRowCount": 6,
    "totalPageCount": 1,
    "offset": 5,
    "limit": 15,
    "statusCode": 200,
    "message": "Activities have been get by person guid(b746b5a2-252a-4895-9669-a32f4e806637)",
    "dateTime": "2024-07-23T11:38:39.0089014Z",
    "data": [...]

&nbsp;

    {
    "totalRowCount": 0,
    "totalPageCount": 1,
    "offset": 0,
    "limit": 10,
    "statusCode": 400,
    "message": "Person not found",
    "dateTime": "2024-07-23T11:45:40.1641403Z",
    "data": null
    }

### Get Activities using spesific WorkAction Guid

| Parameter | Type | Description |
| :--- | :--- | :--- |
| `guid` | `string` | **Required** |
| `offset`| `integer`||
| `limit`| `integer`||
| `activityTypeEnum`| `string`||
| `isShowSystemUsersActivity`| `boolean` ||

If the given workAction guid is valid, it returns all the activities that match this guid. (Such as CREATE, CALL_AUTO, CALL_INBOUND, CALL_MANUAL, CALL_TRANSFER, CALL_CLOSE, ACT_MOVE, MEMO, SMS, EMAIL, PUSH, IVN)  
If this workAction guid does not exist, it gives not found message with statusCode: 400.

### Request

`GET Activity/GetByWorkActionGuid?guid&Offset&Limit&activityTypeEnum&IsShowSystemUsersActivity`

    curl -X 'GET' \
    'http://home.ermanseneren.com:7020/api/v3/Activity/GetByWorkActionGuid?guid=431ad283-441b-4cb0-a731-be329e628c01&Offset=3&Limit=12&activityTypeEnum=PUSH&IsShowSystemUsersActivity=true' \
    -H 'accept: text/plain'


### Response

     status: 200 OK
     content-type: application/json; charset=utf-8 
     date: Tue,23 Jul 2024 11:54:42 GMT 
     server: Kestrel 
     transfer-encoding: chunked 

&nbsp;

    {
    "totalRowCount": 0,
    "totalPageCount": 1,
    "offset": 3,
    "limit": 12,
    "statusCode": 200,
    "message": "Activities have been get by action guid(431ad283-441b-4cb0-a731-be329e628c01)",
    "dateTime": "2024-07-23T11:54:43.57315Z",
    "data": []
    }

&nbsp;

    {
    "totalRowCount": 1,
    "totalPageCount": 1,
    "offset": 0,
    "limit": 10,
    "statusCode": 200,
    "message": "Activities have been get by action guid(431ad283-441b-4cb0-a731-be329e628c01)",
    "dateTime": "2024-07-23T11:57:43.90456Z",
    "data": []
    }

&nbsp;

    {
    "totalRowCount": 0,
    "totalPageCount": 1,
    "offset": 0,
    "limit": 10,
    "statusCode": 400,
    "message": "WorkAction not found",
    "dateTime": "2024-07-23T11:58:43.1450667Z",
    "data": null
    }

!!! missing parts 400
### Get Activities using spesific LoanAccountNumber, worklistType and workActionCreatedDate

| Parameter | Type | Description |
| :--- | :--- | :--- |
| `loanAccountNumber` | `string` | **Required** |
|`worklistType`|`string`| **Required** |
|`WorkActionCreatedDate`|`string`| **Required** |
| `offset`| `integer`||
| `limit`| `integer`||
|`sortBy`|`string`||
|`sortOrder`|`sring`||
| `activityTypeEnum`| `string`||
| `isShowSystemUsersActivity`| `boolean` ||

If the given loanAccountNumber, worklistType and WorkActionCreatedDate are valid, it returns all the activities that match this informations. (Such as CREATE, CALL_AUTO, CALL_INBOUND, CALL_MANUAL, CALL_TRANSFER, CALL_CLOSE, ACT_MOVE, MEMO, SMS, EMAIL, PUSH, IVN)  
If this given informations does not match any activity, it gives not found message with statusCode: 400.

### Request

`GET Activity/GetByAcccountAndWorkActionDateAndWorklistType?loanAccountNumber&worklistType&WorkActionCreatedDate&IsShowSystemUsersActivity`

    curl -X 'GET' \
    'http://home.ermanseneren.com:7020/api/v3/Activity/GetByAcccountAndWorkActionDateAndWorklistType?loanAccountNumber=1050-67022799-1&worklistType=MANUAL&WorkActionCreatedDate=06%2F07%2F2024&IsShowSystemUsersActivity=true' \
    -H 'accept: text/plain'


### Response

     status: 200 OK
     content-type: application/json; charset=utf-8 
     date: Tue,23 Jul 2024 12:09:17 GMT 
     server: Kestrel 
     transfer-encoding: chunked 

&nbsp;

    {
    "totalRowCount": 0,
    "totalPageCount": 1,
    "offset": 0,
    "limit": 10,
    "statusCode": 200,
    "message": "Activities have been get by loanAccountNumber(1050-67022799-1) and WorklistTypeEnum(MANUAL) and WorkActionCreatedDate(06/07/2024 00:00:00)",
    "dateTime": "2024-07-23T12:09:18.2170291Z",
    "data": []
    }
<!-->
### Get Activities using spesific userIdentityNumber

| Parameter | Type | Description |
| :--- | :--- | :--- |
| `userIdentityNumber` | `string` | **Required** |
| `offset`| `integer`||
| `limit`| `integer`||
| `activityTypeEnum`| `string`||-->

## Customer

### Get LoanAccountPayments using LoanAccount Guid

| Parameter | Type | Description |
| :--- | :--- | :--- |
| `loanAccountGuid` | `string` | **Required** |


If the given loanAccountGuid is valid, it returns detailed information about Loan Account Payments. If the guid is not valid, it gives not found message with statusCode:400.

### Request

`GET Customer/GetLoanAccountPaymentByLoanAccountGuid?loanAccountGuid`

    curl -X 'GET' \
    'http://home.ermanseneren.com:7020/api/v3/Customer/GetLoanAccountPaymentByLoanAccountGuid?loanAccountGuid=03f9e238-714f-4595-8aed-763aa316b0ab' \
    -H 'accept: text/plain'

### Response

     status: 200 OK
     content-type: application/json; charset=utf-8 
     date: Tue,23 Jul 2024 12:33:45 GMT 
     server: Kestrel 
     transfer-encoding: chunked 

&nbsp;

    {
    "statusCode": 200,
    "message": "LoanAccountPayment not found by LoanAccount.Guid   ((03f9e238-714f-4595-8aed-763aa316b0ab)",
    "dateTime": "2024-07-23T12:33:46.7927197Z",
    "data": null
    }
### Get Bucket Change using Person Guid

| Parameter | Type | Description |
| :--- | :--- | :--- |
| `personGuid` | `string` | **Required** |

It returns the bucket changes associated with a given person GUID. If the guid is not valid, it gives not found message with statusCode:400.

### Request

`GET Customer/GetBucketChangeByPersonGuid?personGuid`

    curl -X 'GET' \
    'http://home.ermanseneren.com:7020/api/v3/Customer/GetBucketChangeByPersonGuid?personGuid=bd4ee697-f02d-49bf-8c65-63bf8b6a463a' \
    -H 'accept: text/plain'

### Response

     status: 200 OK
     content-type: application/json; charset=utf-8 
     date: Tue,23 Jul 2024 13:59:57 GMT 
     server: Kestrel 
     transfer-encoding: chunked

&nbsp;

    {
    "statusCode": 200,
    "message": "BucketChange have been get by personGuid(bd4ee697-f02d-49bf-8c65-63bf8b6a463a)",
    "dateTime": "2024-07-23T13:59:58.0713034Z",
    "data": []
    }

&nbsp;

    {
    "statusCode": 400,
    "message": "personEntity not found",
    "dateTime": "2024-07-23T14:01:19.1166092Z",
    "data": null
    }
    
### Get Bucket Change usin LoanAccount Guid

| Parameter | Type | Description |
| :--- | :--- | :--- |
| `loanAccountGuid` | `string` | **Required** |

It returns the bucket changes associated with a given LoanAccount's GUID. If the guid is not valid, it gives not found message with statusCode:400.

### Request

`GET Customer/GetBucketChangeByLoanAccountGuid?loanAccountGuid`

    curl -X 'GET' \
    'http://home.ermanseneren.com:7020/api/v3/Customer/GetBucketChangeByLoanAccountGuid?loanAccountGuid=5b9ae42f-0f61-4082-9b24-d71be0f10168' \
    -H 'accept: text/plain'

### Response

     status: 200 OK
     content-type: application/json; charset=utf-8 
     date: Tue,23 Jul 2024 13:49:59 GMT 
     server: Kestrel 
     transfer-encoding: chunked
    
&nbsp;

    {
    "statusCode": 200,
    "message": "BucketChange have been get by loanAccountGuid(5b9ae42f-0f61-4082-9b24-d71be0f10168)",
    "dateTime": "2024-07-23T13:49:59.5944821Z",
    "data": []
    }

&nbsp;

    {
    "statusCode": 400,
    "message": "loanAccountEntity not found",
    "dateTime": "2024-07-23T13:55:28.3239517Z",
    "data": null
    }


<!-- bunlar benzer çalışıyor 2. daha detaylı-->
### Get person using GUID

| Parameter | Type | Description |
| :--- | :--- | :--- |
| `guid` | `string` | **Required** |


If the given guid valid, it gives information about customer. If the guid is not valid, it gives not found message eith statusCode:400.

### Request

`GET Customer/GetCustomerInfoByGuid?guid`

    curl -X 'GET' \
    'http://home.ermanseneren.com:7020/api/v3/Customer/GetCustomerInfoByGuid?guid=bd4ee697-f02d-49bf-8c65-63bf8b6a463a' \
    -H 'accept: text/plain'

### Response

     status: 200 OK
     content-type: application/json; charset=utf-8 
     date: Tue,23 Jul 2024 13:30:33 GMT 
     server: Kestrel 
     transfer-encoding: chunked 

&nbsp;

    {
    "statusCode": 200,
    "message": "Person have been get by personGuid(bd4ee697-f02d-49bf-8c65-63bf8b6a463a)",
    "dateTime": "2024-07-23T13:30:33.5343916Z",
    "data": {}
    }

&nbsp;

    {
    "statusCode": 400,
    "message": "Entity with guid bd4ee697-f02d-49bf-8c65-63bf8b6a4637 not found.",
    "dateTime": "2024-07-23T13:34:40.0987949Z",
    "data": null
    }

### Get detailed person by Guid

| Parameter | Type | Description |
| :--- | :--- | :--- |
| `guid` | `string` | **Required** |


If the given guid valid, it gives detailed information about customer. If the guid is not valid, it gives not found message eith statusCode:400.

### Request

`GET Customer/GetCustomerByGuid?guid`

    curl -X 'GET' \
    'http://home.ermanseneren.com:7020/api/v3/Customer/GetCustomerByGuid?guid=bd4ee697-f02d-49bf-8c65-63bf8b6a463a' \
    -H 'accept: text/plain'

### Response

     status: 200 OK
     content-type: application/json; charset=utf-8 
     date: Tue,23 Jul 2024 13:36:04 GMT 
     server: Kestrel 
     transfer-encoding: chunked 

&nbsp;

    {
     "statusCode": 200,
     "message": "Person have been get by personGuid(bd4ee697-f02d-49bf-8c65-63bf8b6a463a)",
     "dateTime": "2024-07-23T13:36:04.3583956Z",
     "data": {}
    }

&nbsp;

    {
    "statusCode": 400,
    "message": "Entity with guid bd4ee697-f02d-49bf-8c65-63bf8b6a4639 not found.",
    "dateTime": "2024-07-23T13:45:14.2278354Z",
    "data": null
    }

### Get person models associated with a specific search

| Parameter | Type | Description |
| :--- | :--- | :--- |
| `search` | `string` | |
|`segment`|`string`| |
| `offset`| `integer`||
| `limit`| `integer`||
|`sortBy`|`string`||
|`sortOrder`|`sring`||
| `personFlag`| `string`||
| `bucketEnum`| `string` ||

This method takes parameters above for spesific searc and returns  customer list which is compatible with the information provided.

### Request

`GET Customer/CustomerSearch`

    curl -X 'GET' \
    'http://home.ermanseneren.com:7020/api/v3/Customer/CustomerSearch' \
    -H 'accept: text/plain'

### Response

     status: 200 OK
     content-type: application/json; charset=utf-8 
     date: Tue,23 Jul 2024 13:18:46 GMT 
     server: Kestrel 
     transfer-encoding: chunked 

&nbsp;
 
    {
    "totalRowCount": 10310,
    "totalPageCount": 1032,
    "offset": 0,
    "limit": 10,
    "statusCode": 200,
    "message": "Person have been get by search()",
    "dateTime": "2024-07-23T13:18:46.8836668Z",
    "data": []
    }

&nbsp;

It gives information message for any invalid parameter.

    {
    "totalRowCount": 0,
    "totalPageCount": 1,
    "offset": 0,
    "limit": 10,
    "statusCode": 400,
    "message": "2201W: LIMIT must not be negative",
    "dateTime": "2024-07-23T13:21:16.3791257Z",
    "data": null
    }



          
<!--###başlık

| Parameter | Type | Description |
| :--- | :--- | :--- |
| `` | `` | **Required** |
|``|``|  |
|``|``| **Required** |
| `offset`| `integer`||
| `limit`| `integer`||
|`sortBy`|`string`||
|`sortOrder`|`sring`||
| `activityTypeEnum`| `string`||
| `isShowSystemUsersActivity`| `boolean` ||

If the given

### Request

`GET

    curl -X

### Response

     status: 200 OK
-->
     


    
