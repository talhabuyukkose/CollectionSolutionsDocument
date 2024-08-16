> ### Endpoints 
*  [Activity Endpoints](#Activity)
* [Const Endpoints](#Const)
* [Cti Endpoints](#Cti)
* [Customer Endpoints](#Customer)
* [PromisePayment Endpoints](#PromisePayment)
* [ProxyServices Endpoints](#ProxyServices)
* [User Endpoints](#User)
* [WorkAction Endpoints](#WorkAction)
* [WorkList Endpoints](#WorkList)

## Successful Responses

### 1.
```bash
{
    "statusCode": 200,
    "message": "Successfully called ....",
    "dateTime": "2024-07-23T08:01:59.513444Z",
    "data": {}
}
```
### 2.

```bash
{
    "statusCode": 200,
    "message": "Successfully called ....",
    "dateTime": "2024-07-23T08:01:59.513444Z",
    "data": [
      {},
      {}
    ]
}
```

### 3.
```bash
{
  "totalRowCount": 109,
  "totalPageCount": 55,
  "offset": 0,
  "limit": 2,
  "statusCode": 200,
  "message": "Successfully called by ...",
  "dateTime": "2024-07-24T14:21:36.0666289Z",
  "data": [
      {},
      {}
    ]
}
```  
##  Error Responses

###  1. Not Valid Input Response

```json
{
  "statusCode": 400,
  "message": "Validation errors occurred",
  "dateTime": "2024-07-23T08:02:24.2885392Z",
  "data": null,
  "errors": {
    "guid": [
      "The value 'xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx' is not valid."
    ]
  }
}
```  
### 2. Not Found Response
   
```json
{
  "statusCode": 400,
  "message": "Entity with guid xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx not found.",
  "dateTime": "2024-07-23T08:04:07.2424163Z",
  "data": null
}
```  

### 3. Required Parameter Response
    

```json
{
  "statusCode": 400,
  "message": "Validation errors occurred",
  "dateTime": "2024-07-23T08:04:30.2292636Z",
  "data": null,
  "errors": {
    "guid": [
      "The xxxx field is required."
    ]
  }
}
```  

### 4. Invalid JSON Response

```json
{
  "statusCode": 400,
  "message": "Validation errors occurred",
  "dateTime": "2024-07-23T09:19:28.5888657Z",
  "data": null,
  "errors": {
    "$": [
      "Expected depth to be zero at the end of the JSON payload. There is an open JSON object or array that should be closed. Path: $ | LineNumber: 7 | BytePositionInLine: 0."
    ],
    "createWorklist": [
      "The createWorklist field is required."
    ]
  }
}
```

> ### JSON Response Format for Unexpected Model
&nbsp; When an unexpected or invalid model is sent in a request, the API will return a detailed error response indicating the issue. Below is a template for such a response:

**Endpoint**: \`/Activity\`  
**Method**: POST

**Request**
```bash
POST /api/v3/Activity/Create' \
--header 'Content-Type: application/json' \
--header 'Accept: text/plain' \
--data '{
  "userId": 2,
  "type": "EMAIL",
  "workActionId": 338133333333,
  "note": "<string>",
  "status": "FAILED",
  "uuid": "",
  "resultId": 2,
  "subResultId": 3,
  "scheduleDate": "2024-07-29"
}'
Host: localhost:7020
Accept: text/plain
```
**Response**
```json
{
  "statusCode": 400,
  "message": "Activity couldn't create. Message : An error occurred: Foreign Key Violation: Invalid foreign key reference. Constraint name: FK_Activities_WorkActions_WorkActionId.",
  "dateTime": "2024-07-24T14:42:53.1400892Z",
  "data": null
}
```

> ### SAMPLE REQUESTS AND RESPONSES

## Activity

#### **_Retrieve an Activity by GUID_**

**GET** `/api/v3/Activity/GetByGuid`

#### Description

Fetches a specific activity using its GUID, including related entities.

<details>
<summary><h4>Request Details</h4></summary>
##### Query Parameters

| Parameter | Type   | Description                                            |
| :-------- | :----- | :----------------------------------------------------- |
| `guid`    | `guid` | (**_Required_**) The GUID of the activity to retrieve. |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/Activity/GetByGuid?guid=c43d37ea-d71c-4454-9244-afba4e8dc522" -H "Accept: text/plain"
```
</details>
<details>
<summary><h4>Example Response</h4></summary>
  
```json
{
  "statusCode": "<integer>",
  "message": "<string>",
  "dateTime": "<dateTime>",
  "data": {
    "id": "<long>",
    "guid": "<uuid>",
    "isActive": "<boolean>",
    "createDate": "<dateTime>",
    "createUserId": "<long>",
    "updateDate": "<dateTime>",
    "updateUserId": "<long>",
    "user": {
      "id": "<long>",
      "guid": "<uuid>",
      "isActive": "<boolean>",
      "createDate": "<dateTime>",
      "createUserId": "<long>",
      "updateDate": "<dateTime>",
      "updateUserId": "<long>",
      "agentNumber": "<string>",
      "identityNumber": "<string>",
      "firstName": "<string>",
      "middleName": "<string>",
      "lastName": "<string>",
      "role": "Admin",
      "roleNumber": "<integer>"
    },
    "userId": "<long>",
    "type": "IVN",
    "workAction": {
      "id": "<long>",
      "guid": "<uuid>",
      "isActive": "<boolean>",
      "createDate": "<dateTime>",
      "createUserId": "<long>",
      "updateDate": "<dateTime>",
      "updateUserId": "<long>",
      "status": "PENDING",
      "worklistId": "<long>",
      "personId": "<long>",
      "person": {
        "id": "<long>",
        "guid": "<uuid>",
        "isActive": "<boolean>",
        "createDate": "<dateTime>",
        "createUserId": "<long>",
        "updateDate": "<dateTime>",
        "updateUserId": "<long>",
        "segment": "<string>",
        "customerId": "<long>",
        "customerNumber": "<long>",
        "relationCustNum": "<long>",
        "relationType": "SPOUSE",
        "identityNumber": "<string>",
        "name": "<string>",
        "middleName": "<string>",
        "surname": "<string>",
        "firmName": "<string>",
        "personnelFlag": "<boolean>",
        "vipFlag": "<boolean>",
        "birthDate": "<dateTime>",
        "birthPlace": "<string>",
        "workflowCode": "<string>",
        "gender": "Female",
        "dateOfDeath": "<dateTime>",
        "coreLastUpdateDate": "<dateTime>",
        "workIsMailing": "<boolean>",
        "nplFlag": "<boolean>",
        "selfCuredFlag": "<boolean>",
        "nplDate": "<dateTime>",
        "lastKrsSearchDate": "<dateTime>",
        "currentKkbScore": "<integer>",
        "creditCardUsageRate": "<double>",
        "kmhUsageRate": "<double>",
        "collectionScore": "<string>",
        "lastMonthApplicationCount": "<integer>",
        "otherBankMortgageLoanPaymentPerformance": "<string>",
        "blockageFlag": "<boolean>",
        "hepsiDpdMaxLm": "<integer>",
        "sumNumFailL3m": "<integer>",
        "tumKredilerDpdMaxMin6": "<integer>",
        "avgAsinitsBurganOverOutsV12lm": "<string>",
        "hepsiDpdMaxL12m": "<integer>",
        "hepsiDpdLm": "<integer>",
        "hepsiDpdMaxV3lm": "<string>",
        "hepsiTotalOutsV3lm": "<string>",
        "hepsiDpdAmtOutsVlm": "<string>",
        "hepsiDpdAmtOutsMax12": "<double>",
        "modelType": "<string>",
        "finalRatio": "<double>",
        "totalCashRisk": "<double>",
        "totalLimit": "<double>",
        "totalRisk": "<double>",
        "totalPursuable": "<double>",
        "minPursuable": "<double>",
        "totalAssets": "<double>",
        "totalColleteral": "<double>",
        "totalLimitUtilRatio": "<double>",
        "allMaxDpd": "<integer>",
        "engagementGuarantorInfo": "<string>"
      },
      "loanAccountId": "<long>",
      "loanAccount": {
        "id": "<long>",
        "guid": "<uuid>",
        "isActive": "<boolean>",
        "createDate": "<dateTime>",
        "createUserId": "<long>",
        "updateDate": "<dateTime>",
        "updateUserId": "<long>",
        "isExistPromisePayment": "<boolean>",
        "bucket": "B2",
        "leadAccountFlag": "<boolean>",
        "accountNumber": "<string>",
        "branchCode": "<integer>",
        "customerNumber": "<integer>",
        "personId": "<long>",
        "accountReference": "<string>",
        "usageDate": "<dateTime>",
        "accountSuffix": "<integer>",
        "type": "KMH",
        "productCode": "<string>",
        "currencyCode": "<string>",
        "currentAccountIbanNumber": "<string>",
        "accDpd": "<integer>",
        "bucket1DueAmount": "<double>",
        "bucket1RemainingAmount": "<double>",
        "bucket1DueDate": "<dateTime>",
        "bucket2DueAmount": "<double>",
        "bucket2RemainingAmount": "<double>",
        "bucket2DueDate": "<dateTime>",
        "bucket3DueAmount": "<double>",
        "bucket3RemainingAmount": "<double>",
        "bucket3DueDate": "<dateTime>",
        "rollbackFlag": "<string>",
        "restructuredFlag": "<string>",
        "lastPaymentAmount": "<double>",
        "lastPaymentDate": "<dateTime>",
        "muacceliyetDate": "<dateTime>",
        "coreLastUpdateDate": "<dateTime>",
        "stagingImportId": "<long>",
        "maturityDate": "<dateTime>",
        "balance": "<double>",
        "balanceTl": "<double>",
        "pursuable": "<double>",
        "pursuableTl": "<double>",
        "accountLimit": "<double>",
        "accountLimitTl": "<double>",
        "principalAmount": "<double>",
        "dueDate": "<dateTime>",
        "installmentNumber": "<integer>",
        "remainingInstallmentNumber": "<integer>",
        "maxDpd": "<integer>",
        "nextDueDate": "<dateTime>",
        "restructuredCount": "<integer>",
        "cautionAmount": "<double>",
        "delayRate": "<double>",
        "channelDetail": "<string>",
        "dealerName": "<string>",
        "dealerProductName": "<string>",
        "cautionName": "<string>",
        "firstPaymentFlag": "<string>",
        "insuranceFlag": "<string>",
        "insuranceName": "<string>",
        "campaignName": "<string>",
        "nplSuffix": "<integer>",
        "nplDate": "<dateTime>",
        "yySuffix": "<integer>",
        "yyDate": "<dateTime>"
      },
      "template": "<string>",
      "templateParameter": "<string>",
      "contactPersonId": "<long>",
      "contactRole": "ATTORNEY",
      "contactPoint": "<string>",
      "expireDate": "<dateTime>"
    },
    "workActionId": "<long>",
    "note": "<string>",
    "pinned": "<boolean>",
    "status": "FAILED",
    "uuid": "<string>",
    "result": {
      "id": "<long>",
      "guid": "<uuid>",
      "isActive": "<boolean>",
      "createDate": "<dateTime>",
      "createUserId": "<long>",
      "updateDate": "<dateTime>",
      "updateUserId": "<long>",
      "result": "<string>",
      "subResult": "<boolean>",
      "nextAction": "WAIT_RETRY",
      "type": "INTERVIEW_RESULT",
      "nextActionDelay": "<integer>",
      "nextActionMaxTry": "<integer>"
    },
    "resultId": "<long>",
    "subResult": {
      "id": "<long>",
      "guid": "<uuid>",
      "isActive": "<boolean>",
      "createDate": "<dateTime>",
      "createUserId": "<long>",
      "updateDate": "<dateTime>",
      "updateUserId": "<long>",
      "activityResultId": "<long>",
      "subResult": "<string>",
      "nextAction": "LOOK_AT_SUB",
      "nextActionDelay": "<integer>",
      "nextActionMaxTry": "<integer>"
    },
    "subResultId": "<long>",
    "scheduleDate": "<dateTime>"
  }
}
```
</details>

---

#### **_Retrieve Activities by Person GUID_**

**GET** `/api/v3/Activity/GetByPersonGuid`

#### Description

Fetches activities related to a specific Person GUID.

##### Query Parameters

| Parameter          | Type      | Description                                            |
| :----------------- | :-------- | :----------------------------------------------------- |
| `guid`             | `guid`    | (**_Required_**) The GUID of the activity to retrieve. |
| `Offset`           | `integer` |                                                        |
| `Limit`            | `integer` |                                                        |
| `activityTypeEnum` | `string`  |                                                        |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/Activity/GetByPersonGuid?guid=%3Cuuid%3E&Offset=%3Cinteger%3E&Limit=%3Cinteger%3E&activityTypeEnum=SMS" -H "Accept: text/plain"
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
  "statusCode": "<integer>",
  "message": "<string>",
  "dateTime": "<dateTime>",
  "data": [
    {
      "id": "<long>",
      "guid": "<uuid>",
      "isActive": "<boolean>",
      "createDate": "<dateTime>",
      "createUserId": "<long>",
      "updateDate": "<dateTime>",
      "updateUserId": "<long>",
      "userId": "<long>",
      "user": {
        "firstName": "<string>",
        "middleName": "<string>",
        "lastName": "<string>"
      },
      "type": "CALL_TRANSFER",
      "workActionId": "<long>",
      "note": "<string>",
      "pinned": "<boolean>",
      "status": "PROCESSING",
      "uuid": "<string>",
      "resultId": "<long>",
      "result": {
        "id": "<long>",
        "guid": "<uuid>",
        "isActive": "<boolean>",
        "createDate": "<dateTime>",
        "createUserId": "<long>",
        "updateDate": "<dateTime>",
        "updateUserId": "<long>",
        "result": "<string>",
        "subResult": "<boolean>",
        "nextAction": "WAIT_RETRY",
        "type": "PROMISEPAYMENT",
        "nextActionDelay": "<integer>",
        "nextActionMaxTry": "<integer>"
      },
      "subResultId": "<long>",
      "subResult": {
        "id": "<long>",
        "guid": "<uuid>",
        "isActive": "<boolean>",
        "createDate": "<dateTime>",
        "createUserId": "<long>",
        "updateDate": "<dateTime>",
        "updateUserId": "<long>",
        "activityResultId": "<long>",
        "subResult": "<string>",
        "nextAction": "LOOK_AT_SUB",
        "nextActionDelay": "<integer>",
        "nextActionMaxTry": "<integer>"
      },
      "scheduleDate": "<dateTime>"
    },
    {
      "id": "<long>",
      "guid": "<uuid>",
      "isActive": "<boolean>",
      "createDate": "<dateTime>",
      "createUserId": "<long>",
      "updateDate": "<dateTime>",
      "updateUserId": "<long>",
      "userId": "<long>",
      "user": {
        "firstName": "<string>",
        "middleName": "<string>",
        "lastName": "<string>"
      },
      "type": "IVN",
      "workActionId": "<long>",
      "note": "<string>",
      "pinned": "<boolean>",
      "status": "PROCESSING",
      "uuid": "<string>",
      "resultId": "<long>",
      "result": {
        "id": "<long>",
        "guid": "<uuid>",
        "isActive": "<boolean>",
        "createDate": "<dateTime>",
        "createUserId": "<long>",
        "updateDate": "<dateTime>",
        "updateUserId": "<long>",
        "result": "<string>",
        "subResult": "<boolean>",
        "nextAction": "LOOK_AT_SUB",
        "type": "ESCALATION",
        "nextActionDelay": "<integer>",
        "nextActionMaxTry": "<integer>"
      },
      "subResultId": "<long>",
      "subResult": {
        "id": "<long>",
        "guid": "<uuid>",
        "isActive": "<boolean>",
        "createDate": "<dateTime>",
        "createUserId": "<long>",
        "updateDate": "<dateTime>",
        "updateUserId": "<long>",
        "activityResultId": "<long>",
        "subResult": "<string>",
        "nextAction": "WAIT_RETRY",
        "nextActionDelay": "<integer>",
        "nextActionMaxTry": "<integer>"
      },
      "scheduleDate": "<dateTime>"
    }
  ],
  "totalRowCount": "<integer>",
  "totalPageCount": "<integer>",
  "offset": "<integer>",
  "limit": "<integer>"
}
```
</details>

***

#### **_Retrieve activities by WorkAction GUID_**

**GET** `/api/v3/Activity/GetByWorkActionGuid`

#### Description

Fetches activities related to a specific WorkAction GUID.

##### Query Parameters

| Parameter                    | Type      | Description                                            |
| :--------------------------- | :-------- | :----------------------------------------------------- |
| `guid`                       | `guid`    | (**_Required_**) The GUID of the activity to retrieve. |
| `offset `                    | `integer` |                                                        |
| `limit `                     | `string`  |                                                        |
| `activityTypeEnum`           | `string`  |                                                        |
| `IsShowSystemUsersActivity ` | `boolean` |                                                        |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/Activity/GetByWorkActionGuid?guid=%3Cuuid%3E&Offset=%3Cinteger%3E&Limit=%3Cinteger%3E&activityTypeEnum=SMS&IsShowSystemUsersActivity=true" -H "Accept: text/plain"
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
  "statusCode": "<integer>",
  "message": "<string>",
  "dateTime": "<dateTime>",
  "data": [
    {
      "id": "<long>",
      "guid": "<uuid>",
      "isActive": "<boolean>",
      "createDate": "<dateTime>",
      "createUserId": "<long>",
      "updateDate": "<dateTime>",
      "updateUserId": "<long>",
      "userId": "<long>",
      "type": "PUSH",
      "workActionId": "<long>",
      "note": "<string>",
      "pinned": "<boolean>",
      "status": "SUCCESS",
      "uuid": "<string>",
      "resultId": "<long>",
      "result": {
        "id": "<long>",
        "guid": "<uuid>",
        "isActive": "<boolean>",
        "createDate": "<dateTime>",
        "createUserId": "<long>",
        "updateDate": "<dateTime>",
        "updateUserId": "<long>",
        "result": "<string>",
        "subResult": "<boolean>",
        "nextAction": "LOOK_AT_SUB",
        "type": "PROMISEPAYMENT",
        "nextActionDelay": "<integer>",
        "nextActionMaxTry": "<integer>"
      },
      "subResultId": "<long>",
      "subResult": {
        "id": "<long>",
        "guid": "<uuid>",
        "isActive": "<boolean>",
        "createDate": "<dateTime>",
        "createUserId": "<long>",
        "updateDate": "<dateTime>",
        "updateUserId": "<long>",
        "activityResultId": "<long>",
        "subResult": "<string>",
        "nextAction": "STOP",
        "nextActionDelay": "<integer>",
        "nextActionMaxTry": "<integer>"
      },
      "scheduleDate": "<dateTime>"
    },
    {
      "id": "<long>",
      "guid": "<uuid>",
      "isActive": "<boolean>",
      "createDate": "<dateTime>",
      "createUserId": "<long>",
      "updateDate": "<dateTime>",
      "updateUserId": "<long>",
      "userId": "<long>",
      "type": "SMS",
      "workActionId": "<long>",
      "note": "<string>",
      "pinned": "<boolean>",
      "status": "PENDING",
      "uuid": "<string>",
      "resultId": "<long>",
      "result": {
        "id": "<long>",
        "guid": "<uuid>",
        "isActive": "<boolean>",
        "createDate": "<dateTime>",
        "createUserId": "<long>",
        "updateDate": "<dateTime>",
        "updateUserId": "<long>",
        "result": "<string>",
        "subResult": "<boolean>",
        "nextAction": "WAIT_RETRY",
        "type": "INTERVIEW_RESULT",
        "nextActionDelay": "<integer>",
        "nextActionMaxTry": "<integer>"
      },
      "subResultId": "<long>",
      "subResult": {
        "id": "<long>",
        "guid": "<uuid>",
        "isActive": "<boolean>",
        "createDate": "<dateTime>",
        "createUserId": "<long>",
        "updateDate": "<dateTime>",
        "updateUserId": "<long>",
        "activityResultId": "<long>",
        "subResult": "<string>",
        "nextAction": "STOP",
        "nextActionDelay": "<integer>",
        "nextActionMaxTry": "<integer>"
      },
      "scheduleDate": "<dateTime>"
    }
  ],
  "totalRowCount": "<integer>",
  "totalPageCount": "<integer>",
  "offset": "<integer>",
  "limit": "<integer>"
}
```
</details>

***

#### **_REtrieve activities by LoanAccount, AccountNumber, WorkActionDate and WorklistType_**

**GET** `/api/v3/Activity/GetByAcccountAndWorkActionDateAndWorklistType`

#### Description

Fetches activities related to a specific WorkAction GUID.

##### Query Parameters

| Parameter                    | Type      | Description      |
| :--------------------------- | :-------- | :--------------- |
| `loanAccountNumber`          | `string`  | (**_Required_**) |
| `worklistType `              | `string`  | (**_Required_**) |
| `WorkActionCreatedDate `     | `string`  | (**_Required_**) |
| `offset`                     | `integer` |                  |
| `limit`                      | `integer` |                  |
| `sortBy`                     | `string`  |                  |
| `sortOrder`                  | `string`  |                  |
| `activityTypeEnum`           | `string`  |                  |
| `IsShowSystemUsersActivity ` | `boolean` |                  |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/Activity/GetByAcccountAndWorkActionDateAndWorklistType?loanAccountNumber=%3Cstring%3E&worklistType=NO_ACTION&WorkActionCreatedDate=%3CdateTime%3E&Offset=%3Cinteger%3E&Limit=%3Cinteger%3E&sortBy=%3Cstring%3E&sortOrder=asc&activityTypeEnum=SMS&IsShowSystemUsersActivity=true" -H "Accept: text/plain"
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": [
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "updateDate": "<dateTime>",
            "type": "CALL_INBOUND",
            "userId": "<long>",
            "note": "<string>",
            "pinned": "<boolean>",
            "status": "NEW_ENTITY",
            "uuid": "<string>",
            "resultId": "<long>",
            "result": {
                "id": "<long>",
                "type": "NATURAL",
                "result": "<string>"
            },
            "subResultId": "<long>",
            "subResult": {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "activityResultId": "<long>",
                "subResult": "<string>",
                "nextAction": "STOP",
                "nextActionDelay": "<integer>",
                "nextActionMaxTry": "<integer>"
            },
            "user": {
                "firstName": "<string>",
                "middleName": "<string>",
                "lastName": "<string>"
            },
            "scheduleDate": "<dateTime>"
        },
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "updateDate": "<dateTime>",
            "type": "CALL_CLOSE",
            "userId": "<long>",
            "note": "<string>",
            "pinned": "<boolean>",
            "status": "NEW_ENTITY",
            "uuid": "<string>",
            "resultId": "<long>",
            "result": {
                "id": "<long>",
                "type": "ESCALATION",
                "result": "<string>"
            },
            "subResultId": "<long>",
            "subResult": {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "activityResultId": "<long>",
                "subResult": "<string>",
                "nextAction": "WAIT_RETRY",
                "nextActionDelay": "<integer>",
                "nextActionMaxTry": "<integer>"
            },
            "user": {
                "firstName": "<string>",
                "middleName": "<string>",
                "lastName": "<string>"
            },
            "scheduleDate": "<dateTime>"
        }
    ],
    "totalRowCount": "<integer>",
    "totalPageCount": "<integer>",
    "offset": "<integer>",
    "limit": "<integer>"
}
```
</details>

***

#### **_Retrieve activities by User with userIdentityNumber_**

**GET** `/api/v3/Activity/GetByUserIdentityNumber`

#### Description

Fetches activities related to a specific User with userIdentityNumber.

##### Query Parameters

| Parameter            | Type      | Description      |
| :------------------- | :-------- | :--------------- |
| `userIdentityNumber` | `string`  | (**_Required_**) |
| `offset`             | `integer` |                  |
| `limit`              | `integer` |                  |
| `activityTypeEnum`   | `string`  |                  |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/Activity/GetByUserIdentityNumber?userIdentityNumber=%3Cstring%3E&Offset=%3Cinteger%3E&Limit=%3Cinteger%3E&activityTypeEnum=SMS" -H "Accept: text/plain"
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": [
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "userId": "<long>",
            "type": "PUSH",
            "workActionId": "<long>",
            "note": "<string>",
            "pinned": "<boolean>",
            "status": "SUCCESS",
            "uuid": "<string>",
            "resultId": "<long>",
            "result": {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "result": "<string>",
                "subResult": "<boolean>",
                "nextAction": "LOOK_AT_SUB",
                "type": "PROMISEPAYMENT",
                "nextActionDelay": "<integer>",
                "nextActionMaxTry": "<integer>"
            },
            "subResultId": "<long>",
            "subResult": {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "activityResultId": "<long>",
                "subResult": "<string>",
                "nextAction": "STOP",
                "nextActionDelay": "<integer>",
                "nextActionMaxTry": "<integer>"
            },
            "scheduleDate": "<dateTime>"
        },
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "userId": "<long>",
            "type": "SMS",
            "workActionId": "<long>",
            "note": "<string>",
            "pinned": "<boolean>",
            "status": "PENDING",
            "uuid": "<string>",
            "resultId": "<long>",
            "result": {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "result": "<string>",
                "subResult": "<boolean>",
                "nextAction": "WAIT_RETRY",
                "type": "INTERVIEW_RESULT",
                "nextActionDelay": "<integer>",
                "nextActionMaxTry": "<integer>"
            },
            "subResultId": "<long>",
            "subResult": {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "activityResultId": "<long>",
                "subResult": "<string>",
                "nextAction": "STOP",
                "nextActionDelay": "<integer>",
                "nextActionMaxTry": "<integer>"
            },
            "scheduleDate": "<dateTime>"
        }
    ],
    "totalRowCount": "<integer>",
    "totalPageCount": "<integer>",
    "offset": "<integer>",
    "limit": "<integer>"
}
```
</details>

***

#### **_Retrieve activities by Person GUID and UserId and Activity Date and others_**

**GET** `/api/v3/Activity/GetByPersonGuidAndDateOnlyAgent`

#### Description

Fetches a list of activities associated with a specific person GUID.

##### Query Parameters

| Parameter           | Type      | Description      |
| :------------------ | :-------- | :--------------- |
| `personGuid`        | `guid`    | (**_Required_**) |
| `loanAccountNumber` | `string`  |                  |
| `startDate `        | `string`  |                  |
| `endDate `          | `string`  |                  |
| `sortBy`            | `string`  |                  |
| `sortOrder`         | `string`  |                  |
| `offset`            | `integer` |                  |
| `limit`             | `integer` |                  |
| `userId`            | `integer` |                  |
| `ResultId`          | `integer` |                  |
| `SubResultId`       | `integer` |                  |
| `activityType`      | `string`  |                  |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/Activity/GetByPersonGuidAndDateOnlyAgent?personGuid=%3Cuuid%3E&loanAccountNumber=%3Cstring%3E&startDate=%3CdateTime%3E&endDate=%3CdateTime%3E&sortBy=%3Cstring%3E&sortOrder=asc&Offset=%3Cinteger%3E&Limit=%3Cinteger%3E&userId=-1&ResultId=-1&SubResultId=-1&activityType=SMS" -H "Accept: text/plain"
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": [
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "userId": "<long>",
            "user": {
                "firstName": "<string>",
                "middleName": "<string>",
                "lastName": "<string>"
            },
            "type": "MEMO",
            "workActionId": "<long>",
            "workAction": {
                "status": "NEW_ENTITY",
                "worklistId": "<long>",
                "worklist": {
                    "name": "<string>",
                    "type": "MANUAL",
                    "guid": "<uuid>"
                },
                "loanAccountId": "<long>",
                "loanAccount": {
                    "bucket": "B4",
                    "leadAccountFlag": "<boolean>",
                    "accountNumber": "<string>",
                    "customerNumber": "<long>",
                    "type": "VADESIZ"
                },
                "template": "<string>",
                "templateParameter": "<string>",
                "contactRole": "GUARANTOR",
                "contactPoint": "<string>",
                "expireDate": "<dateTime>",
                "priority": "<integer>"
            },
            "note": "<string>",
            "pinned": "<boolean>",
            "status": "SUCCESS",
            "uuid": "<string>",
            "result": {
                "id": "<long>",
                "type": "CALL_RESULT",
                "result": "<string>"
            },
            "resultId": "<long>",
            "subResult": {
                "id": "<long>",
                "subResult": "<string>"
            },
            "subResultId": "<long>",
            "scheduleDate": "<dateTime>"
        },
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "userId": "<long>",
            "user": {
                "firstName": "<string>",
                "middleName": "<string>",
                "lastName": "<string>"
            },
            "type": "CALL_MANUAL",
            "workActionId": "<long>",
            "workAction": {
                "status": "SUCCESS",
                "worklistId": "<long>",
                "worklist": {
                    "name": "<string>",
                    "type": "SMS",
                    "guid": "<uuid>"
                },
                "loanAccountId": "<long>",
                "loanAccount": {
                    "bucket": "B2",
                    "leadAccountFlag": "<boolean>",
                    "accountNumber": "<string>",
                    "customerNumber": "<long>",
                    "type": "VADESIZ"
                },
                "template": "<string>",
                "templateParameter": "<string>",
                "contactRole": "GUARDIAN",
                "contactPoint": "<string>",
                "expireDate": "<dateTime>",
                "priority": "<integer>"
            },
            "note": "<string>",
            "pinned": "<boolean>",
            "status": "FAILED",
            "uuid": "<string>",
            "result": {
                "id": "<long>",
                "type": "ESCALATION",
                "result": "<string>"
            },
            "resultId": "<long>",
            "subResult": {
                "id": "<long>",
                "subResult": "<string>"
            },
            "subResultId": "<long>",
            "scheduleDate": "<dateTime>"
        }
    ]
}
```
</details>

***

#### **_Create an activity_**

**POST** `/api/v3/Activity/Create`

#### Description

Creates a new activity with the provided details

##### Query Parameters

| Parameter       | Type | Description |
| :-------------- | :--- | :---------- |
| `no parameters` |      |             |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X POST "http://localhost:7080/api/v3/Activity/Create" -H "Accept: text/plain" -data '{
  "userId": "<long>",
  "type": "EMAIL",
  "workActionId": "<long>",
  "note": "<string>",
  "status": "FAILED",
  "uuid": "<string>",
  "resultId": "<long>",
  "subResultId": "<long>",
  "scheduleDate": "<dateTime>"
}'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": {
        "id": "<long>",
        "guid": "<uuid>",
        "isActive": "<boolean>",
        "createDate": "<dateTime>",
        "createUserId": "<long>",
        "updateDate": "<dateTime>",
        "updateUserId": "<long>",
        "userId": "<long>",
        "type": "CREATE",
        "workActionId": "<long>",
        "note": "<string>",
        "pinned": "<boolean>",
        "status": "NEW_ENTITY",
        "uuid": "<string>",
        "resultId": "<long>",
        "result": {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "result": "<string>",
            "subResult": "<boolean>",
            "nextAction": "WAIT_RETRY",
            "type": "ESCALATION",
            "nextActionDelay": "<integer>",
            "nextActionMaxTry": "<integer>"
        },
        "subResultId": "<long>",
        "subResult": {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "activityResultId": "<long>",
            "subResult": "<string>",
            "nextAction": "LOOK_AT_SUB",
            "nextActionDelay": "<integer>",
            "nextActionMaxTry": "<integer>"
        },
        "scheduleDate": "<dateTime>"
    }
}
```
</details>

---

#### **_Update an activity_**

**POST** `/api/v3/Activity/Update`

#### Description

Updates an existing activity with the specified details

##### Query Parameters

| Parameter       | Type | Description |
| :-------------- | :--- | :---------- |
| `no parameters` |      |             |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X POST "http://localhost:7080/api/v3/Activity/Update" -H "Accept: text/plain" -data '{
  "guid": "<uuid>",
  "isActive": "<boolean>",
  "updateUserId": "<long>",
  "userId": "<long>",
  "type": "CALL_CLOSE",
  "workActionId": "<long>",
  "note": "<string>",
  "pinned": "<boolean>",
  "status": "FAILED",
  "uuid": "<string>",
  "resultId": "<long>",
  "subResultId": "<long>"
}'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
  "statusCode": "<integer>",
  "message": "<string>",
  "dateTime": "<dateTime>",
  "data": {
    "id": "<long>",
    "guid": "<uuid>",
    "isActive": "<boolean>",
    "createDate": "<dateTime>",
    "createUserId": "<long>",
    "updateDate": "<dateTime>",
    "updateUserId": "<long>",
    "userId": "<long>",
    "type": "CREATE",
    "workActionId": "<long>",
    "note": "<string>",
    "pinned": "<boolean>",
    "status": "NEW_ENTITY",
    "uuid": "<string>",
    "resultId": "<long>",
    "result": {
      "id": "<long>",
      "guid": "<uuid>",
      "isActive": "<boolean>",
      "createDate": "<dateTime>",
      "createUserId": "<long>",
      "updateDate": "<dateTime>",
      "updateUserId": "<long>",
      "result": "<string>",
      "subResult": "<boolean>",
      "nextAction": "WAIT_RETRY",
      "type": "ESCALATION",
      "nextActionDelay": "<integer>",
      "nextActionMaxTry": "<integer>"
    },
    "subResultId": "<long>",
    "subResult": {
      "id": "<long>",
      "guid": "<uuid>",
      "isActive": "<boolean>",
      "createDate": "<dateTime>",
      "createUserId": "<long>",
      "updateDate": "<dateTime>",
      "updateUserId": "<long>",
      "activityResultId": "<long>",
      "subResult": "<string>",
      "nextAction": "LOOK_AT_SUB",
      "nextActionDelay": "<integer>",
      "nextActionMaxTry": "<integer>"
    },
    "scheduleDate": "<dateTime>"
  }
}
```
</details>

---

#### **_Deactivate an activity_**

**POST** `/api/v3/Activity/Deactivate`

#### Description

Deactivates a specified activity

##### Query Parameters

| Parameter       | Type | Description |
| :-------------- | :--- | :---------- |
| `no parameters` |      |             |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X POST "http://localhost:7080/api/v3/Activity/Deactivate" -H "Accept: text/plain" -data '{
  "guid": "<uuid>",
  "updateUserId": "<long>"
}'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
  "statusCode": "<integer>",
  "message": "<string>",
  "dateTime": "<dateTime>",
  "data": {
    "nullable": true
  }
}
```
</details>

---

## Const

#### **_Get all enum_**

**GET** `/api/v3/Const/GetAllEnums`

#### Description

The method return all enums

##### Query Parameters

| Parameter       | Type | Description |
| :-------------- | :--- | :---------- |
| `no parameters` |      |             |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/Const/GetAllEnums"
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": [
        {
            "name": "<string>",
            "values": [
                "<string>",
                "<string>",
                "<string>",
                "<string>",
                "<string>"
            ]
        },
          {
            "name": "<string>",
            "values": [
                "<string>",
                "<string>",
                "<string>",
                "<string>",
                "<string>",
                "<string>",
                "<string>",
                "<string>",
                "<string>",
                "<string>"
            ]
        },
         {
            "name": "<string>",
            "values": [
                "<string>",
                "<string>",
                "<string>"

            ]
        },
        ...
    ]

}

```

</details>

***

#### **_Get ActivityResult list_**

**GET** `/api/v3/Const/GetActivityResults`

#### Description

Fetches a list of all ActivityResults.

##### Query Parameters

| Parameter       | Type | Description |
| :-------------- | :--- | :---------- |
| `no parameters` | `    |             |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/Const/GetActivityResults" -H "Accept: text/plain"
````

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": [
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "result": "<string>",
            "subResult": "<boolean>",
            "nextAction": "LOOK_AT_SUB",
            "type": "CALL_RESULT",
            "nextActionDelay": "<integer>",
            "nextActionMaxTry": "<integer>"
        },
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "result": "<string>",
            "subResult": "<boolean>",
            "nextAction": "STOP",
            "type": "PROMISEPAYMENT",
            "nextActionDelay": "<integer>",
            "nextActionMaxTry": "<integer>"
        }
    ]
}
```
</details>

***

#### **_Get segment list_**

**GET** `/api/v3/Const/GetSegment`

#### Description

Fetches a list of all segments.

##### Query Parameters

| Parameter       | Type | Description |
| :-------------- | :--- | :---------- |
| `no parameters` |     |             |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/Const/GetSegments" -H "Accept: text/plain"
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json

{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": {
        "nullable": true
    }
}
```
</details>

***

#### **_Get ActivityResult by Id_**

**GET** `/api/v3/Const/GetActivityResultById`

#### Description

Fetches a specific ActivityResult by its Id.

##### Query Parameters

| Parameter | Type   | Description |
| :-------- | :----- | :---------- |
| `id`      | `long` |             |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/Const/GetActivityResultById?id=%3Clong%3E" -H 'Accept: text/plain'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": {
        "id": "<long>",
        "guid": "<uuid>",
        "isActive": "<boolean>",
        "createDate": "<dateTime>",
        "createUserId": "<long>",
        "updateDate": "<dateTime>",
        "updateUserId": "<long>",
        "result": "<string>",
        "subResult": "<boolean>",
        "nextAction": "LOOK_AT_SUB",
        "type": "PROMISEPAYMENT",
        "nextActionDelay": "<integer>",
        "nextActionMaxTry": "<integer>"
    }
}
```
</details>

---

#### **_Get ActivitySubResult by Id_**

**GET** `/api/v3/Const/GetActivitySubResultById`

#### Description

Fetches a specific ActivitySubResult by its Id.

##### Query Parameters

| Parameter | Type | Description |
| :-------- | :--- | :---------- |
| `id`      |      | `integer`   |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/Const/GetActivitySubResultById?id=%3Clong%3E" -H "Accept: text/plain"
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": {
        "id": "<long>",
        "guid": "<uuid>",
        "isActive": "<boolean>",
        "createDate": "<dateTime>",
        "createUserId": "<long>",
        "updateDate": "<dateTime>",
        "updateUserId": "<long>",
        "activityResultId": "<long>",
        "subResult": "<string>",
        "nextAction": "LOOK_AT_SUB",
        "nextActionDelay": "<integer>",
        "nextActionMaxTry": "<integer>"
    }
}
```
</details>

---

#### **_Get ActivitySubResult list_**

**GET** `/api/v3/Const/GetActivitySubResults`

#### Description

Fetches a list of all ActivitySubResults.

##### Query Parameters

| Parameter       | Type | Description |
| :-------------- | :--- | :---------- |
| `no parameters` |      |             |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X POST "http://localhost:7080/api/v3/Const/GetActivitySubResults" -H "Accept: text/plain"
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": [
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "activityResultId": "<long>",
            "subResult": "<string>",
            "nextAction": "WAIT_RETRY",
            "nextActionDelay": "<integer>",
            "nextActionMaxTry": "<integer>"
        },
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "activityResultId": "<long>",
            "subResult": "<string>",
            "nextAction": "LOOK_AT_SUB",
            "nextActionDelay": "<integer>",
            "nextActionMaxTry": "<integer>"
        }
    ]
}
```
</details>

---

## Const

#### **_Get all enum_**

**GET** `/api/v3/Const/GetLastWorkDay`

#### Description

The method return all enums

##### Query Parameters

| Parameter | Type      | Description |
| :-------- | :-------- | :---------- |
| `year`    | `integer` |             |
| `month`   | `inteer`  |             |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/Const/GetLastWorkDay?year=%3Cinteger%3E&month=%3Cinteger%3E"
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": 200,
    "message": "Last workday of year-month (<year>-<month>): ",
    "dateTime": "<dateTime>",
    "data": "<integer>"
}

```

</details>

---

## Cti

#### **_Get call permit_**

**GET** `/api/v3/Cti/CallPermit`

#### Description



##### Query Parameters

| Parameter | Type   | Description |
| :-------- | :----- | :---------- |
| `guid`      | `guid` |             |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/Cti/CallPermit?guid=%3Cuuid%3E" -H 'Accept: text/plain'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>"
}
```
</details>

---

#### **_Set Call Start_**

**POST** `/api/v3/Cti/SetCallStart`

#### Description



##### Query Parameters

| Parameter | Type | Description |
| :-------- | :--- | :---------- |
| `no parameters`      |      |    |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X POST "http://localhost:7080/api/v3/Cti/SetCallStart" -H "Accept: text/plain" -data '{
  "callType": "CALL_MANUAL",
  "callDate": "<dateTime>",
  "userIdn": "<string>",
  "contactPhone": "<string>",
  "contactIdn": "<string>",
  "customerNumber": "<long>",
  "callGuid": "<string>",
  "callUiid": "<string>"
}'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>"
}
```
</details>

---

#### **_Set Call Result_**

**POST** `/api/v3/Cti/SetCallResult`

#### Description


##### Query Parameters

| Parameter       | Type | Description |
| :-------------- | :--- | :---------- |
| `no parameters` |      |             |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X POST "http://localhost:7080/api/v3/Cti/SetCallResult" -H "Accept: text/plain" -data '{
  "uuid": "<string>",
  "guid": "<string>",
  "result_code": "CALL_FAILED",
  "reason_code": "<string>",
  "caller_id": "<string>",
  "call_start_date": "<string>",
  "call_end_date": "<string>",
  "identity_number": "<string>",
  "customer_number": "<integer>",
  "call_type": "CALL_AUTO"
}'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>"
}
```
</details>

---

## Customer

#### **_Retrieve Loan Account Payments By Loan Account Guid_**

**GET** `/api/v3/Customer/GetLoanAccountPaymentByLoanAccountGuid`

#### Description

Fetches a detailed Loan Account Payments using its loanAccountGuid identifier.


##### Query Parameters

| Parameter | Type   | Description |
| :-------- | :----- | :---------- |
| `loanAccountGuid`      | `guid` |   (**_required_** )       |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/Customer/GetLoanAccountPaymentByLoanAccountGuid?loanAccountGuid=%3Cuuid%3E" -H 'Accept: text/plain'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": [
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "loanAccountId": "<long>",
            "paymentDate": "<dateTime>",
            "paymentAmount": "<double>",
            "paymentType": "CashDeposit",
            "paymentChannel": "<string>",
            "paymentReference": "<string>",
            "sequenceNumber": "<integer>",
            "isSeqCompleted": "<boolean>",
            "partialPaidInstallmentAmount": "<double>",
            "partialPaidDelayInterestAmount": "<double>",
            "partialPaidDelayKkdfAmount": "<double>",
            "partialPaidDelayBsmvAmount": "<double>",
            "totalPaymentAmount": "<double>"
        },
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "loanAccountId": "<long>",
            "paymentDate": "<dateTime>",
            "paymentAmount": "<double>",
            "paymentType": "Cheque",
            "paymentChannel": "<string>",
            "paymentReference": "<string>",
            "sequenceNumber": "<integer>",
            "isSeqCompleted": "<boolean>",
            "partialPaidInstallmentAmount": "<double>",
            "partialPaidDelayInterestAmount": "<double>",
            "partialPaidDelayKkdfAmount": "<double>",
            "partialPaidDelayBsmvAmount": "<double>",
            "totalPaymentAmount": "<double>"
        }
    ]
}
```
</details>

---

#### **_Retrieve Base Accounts by Person Guid_**

**GET** `/api/v3/Customer/GetAllAccountsBaseEntityByPersonGuid`

#### Description

Fetches a detailed base account using its personGUID identifier.

##### Query Parameters

| Parameter | Type | Description |
| :-------- | :--- | :---------- |
| `personGuid `      | `guid` |   (**_required_** )       |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/Customer/GetAllAccountsBaseEntityByPersonGuid?personGuid=%3Cuuid%3E" -H 'Accept: text/plain'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": [
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "bucket": "B1",
            "leadAccountFlag": "<boolean>",
            "accountNumber": "<string>",
            "branchCode": "<integer>",
            "customerNumber": "<integer>",
            "personId": "<long>",
            "accountReference": "<string>",
            "usageDate": "<dateTime>",
            "accountSuffix": "<integer>",
            "type": "OZEL_KARSILIK",
            "productCode": "<string>",
            "currencyCode": "<string>",
            "currentAccountIbanNumber": "<string>",
            "accDpd": "<integer>",
            "bucket1DueAmount": "<double>",
            "bucket1RemainingAmount": "<double>",
            "bucket1DueDate": "<dateTime>",
            "bucket2DueAmount": "<double>",
            "bucket2RemainingAmount": "<double>",
            "bucket2DueDate": "<dateTime>",
            "bucket3DueAmount": "<double>",
            "bucket3RemainingAmount": "<double>",
            "bucket3DueDate": "<dateTime>",
            "rollbackFlag": "<string>",
            "restructuredFlag": "<string>",
            "lastPaymentAmount": "<double>",
            "lastPaymentDate": "<dateTime>",
            "muacceliyetDate": "<dateTime>",
            "coreLastUpdateDate": "<dateTime>",
            "totalRemainingAmount": "<double>",
            "stagingImportId": "<long>"
        },
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "bucket": "B1",
            "leadAccountFlag": "<boolean>",
            "accountNumber": "<string>",
            "branchCode": "<integer>",
            "customerNumber": "<integer>",
            "personId": "<long>",
            "accountReference": "<string>",
            "usageDate": "<dateTime>",
            "accountSuffix": "<integer>",
            "type": "Y_YAPILANRIMA_BIREYSEL_KREDI",
            "productCode": "<string>",
            "currencyCode": "<string>",
            "currentAccountIbanNumber": "<string>",
            "accDpd": "<integer>",
            "bucket1DueAmount": "<double>",
            "bucket1RemainingAmount": "<double>",
            "bucket1DueDate": "<dateTime>",
            "bucket2DueAmount": "<double>",
            "bucket2RemainingAmount": "<double>",
            "bucket2DueDate": "<dateTime>",
            "bucket3DueAmount": "<double>",
            "bucket3RemainingAmount": "<double>",
            "bucket3DueDate": "<dateTime>",
            "rollbackFlag": "<string>",
            "restructuredFlag": "<string>",
            "lastPaymentAmount": "<double>",
            "lastPaymentDate": "<dateTime>",
            "muacceliyetDate": "<dateTime>",
            "coreLastUpdateDate": "<dateTime>",
            "totalRemainingAmount": "<double>",
            "stagingImportId": "<long>"
        }
    ]
}
```
</details>

---

#### **_Retrieve a Loan Account By Loan Account Guid_**

**GET** `/api/v3/Customer/GetLoanAccountByGuid`

#### Description

Fetches a detailed loan account using its GUID identifier.

##### Query Parameters

| Parameter       | Type | Description |
| :-------------- | :--- | :---------- |
| `loanAccountGuid`      | `guid` |   (**_required_** )       |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/Customer/GetLoanAccountByGuid?loanAccountGuid=%3Cuuid%3E" -H "Accept: text/plain"
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": {
        "id": "<long>",
        "guid": "<uuid>",
        "isActive": "<boolean>",
        "createDate": "<dateTime>",
        "createUserId": "<long>",
        "updateDate": "<dateTime>",
        "updateUserId": "<long>",
        "isExistPromisePayment": "<boolean>",
        "bucket": "B1",
        "leadAccountFlag": "<boolean>",
        "accountNumber": "<string>",
        "branchCode": "<integer>",
        "customerNumber": "<long>",
        "person": {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "segment": "<string>",
            "customerId": "<long>",
            "customerNumber": "<long>",
            "relationCustNum": "<long>",
            "relationType": "OTHER",
            "identityNumber": "<string>",
            "name": "<string>",
            "middleName": "<string>",
            "surname": "<string>",
            "firmName": "<string>",
            "personnelFlag": "<boolean>",
            "vipFlag": "<boolean>",
            "birthDate": "<dateTime>",
            "birthPlace": "<string>",
            "workflowCode": "<string>",
            "gender": "Female",
            "dateOfDeath": "<dateTime>",
            "coreLastUpdateDate": "<dateTime>",
            "workIsMailing": "<boolean>",
            "nplFlag": "<boolean>",
            "selfCuredFlag": "<boolean>",
            "nplDate": "<dateTime>",
            "lastKrsSearchDate": "<dateTime>",
            "currentKkbScore": "<integer>",
            "creditCardUsageRate": "<double>",
            "kmhUsageRate": "<double>",
            "collectionScore": "<string>",
            "lastMonthApplicationCount": "<integer>",
            "otherBankMortgageLoanPaymentPerformance": "<string>",
            "blockageFlag": "<boolean>",
            "hepsiDpdMaxLm": "<integer>",
            "sumNumFailL3m": "<integer>",
            "tumKredilerDpdMaxMin6": "<integer>",
            "avgAsinitsBurganOverOutsV12lm": "<string>",
            "hepsiDpdMaxL12m": "<integer>",
            "hepsiDpdLm": "<integer>",
            "hepsiDpdMaxV3lm": "<string>",
            "hepsiTotalOutsV3lm": "<string>",
            "hepsiDpdAmtOutsVlm": "<string>",
            "hepsiDpdAmtOutsMax12": "<double>",
            "modelType": "<string>",
            "finalRatio": "<double>",
            "totalCashRisk": "<double>",
            "totalLimit": "<double>",
            "totalRisk": "<double>",
            "totalPursuable": "<double>",
            "minPursuable": "<double>",
            "totalAssets": "<double>",
            "totalColleteral": "<double>",
            "totalLimitUtilRatio": "<double>",
            "allMaxDpd": "<integer>",
            "engagementGuarantorInfo": "<string>"
        },
        "personId": "<long>",
        "accountReference": "<string>",
        "usageDate": "<dateTime>",
        "accountSuffix": "<integer>",
        "type": "MUHTELIF_ALACAK",
        "productCode": "<string>",
        "currencyCode": "<string>",
        "currentAccountIbanNumber": "<string>",
        "accDpd": "<integer>",
        "bucket1DueAmount": "<double>",
        "bucket1RemainingAmount": "<double>",
        "bucket1DueDate": "<dateTime>",
        "bucket2DueAmount": "<double>",
        "bucket2RemainingAmount": "<double>",
        "bucket2DueDate": "<dateTime>",
        "bucket3DueAmount": "<double>",
        "bucket3RemainingAmount": "<double>",
        "bucket3DueDate": "<dateTime>",
        "rollbackFlag": "<string>",
        "restructuredFlag": "<string>",
        "lastPaymentAmount": "<double>",
        "lastPaymentDate": "<dateTime>",
        "muacceliyetDate": "<dateTime>",
        "coreLastUpdateDate": "<dateTime>",
        "stagingImport": {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "startDate": "<dateTime>",
            "endDate": "<dateTime>",
            "status": "FAILED",
            "errorLog": "<string>"
        },
        "stagingImportId": "<long>",
        "promisePayments": [
            {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "activityId": "<long>",
                "loanAccountId": "<long>",
                "personId": "<long>",
                "relationType": "OTHER",
                "promiseDate": "<dateTime>",
                "promiseAmount": "<double>",
                "sequenceNumber": "<integer>",
                "note": "<string>",
                "isPaid": "<boolean>",
                "loanAccountPaymentId": "<long>",
                "giveName": "<string>",
                "accountNumber": "<string>",
                "activityCreateDate": "<dateTime>"
            },
            {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "activityId": "<long>",
                "loanAccountId": "<long>",
                "personId": "<long>",
                "relationType": "SIBLING",
                "promiseDate": "<dateTime>",
                "promiseAmount": "<double>",
                "sequenceNumber": "<integer>",
                "note": "<string>",
                "isPaid": "<boolean>",
                "loanAccountPaymentId": "<long>",
                "giveName": "<string>",
                "accountNumber": "<string>",
                "activityCreateDate": "<dateTime>"
            }
        ],
        "workActions": [
            {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "status": "FAILED",
                "worklistId": "<long>",
                "personId": "<long>",
                "loanAccountId": "<long>",
                "template": "<string>",
                "templateParameter": "<string>",
                "contactPersonId": "<long>",
                "contactRole": "RELATIVE",
                "contactPoint": "<string>",
                "expireDate": "<dateTime>"
            },
            {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "status": "FAILED",
                "worklistId": "<long>",
                "personId": "<long>",
                "loanAccountId": "<long>",
                "template": "<string>",
                "templateParameter": "<string>",
                "contactPersonId": "<long>",
                "contactRole": "GUARANTOR",
                "contactPoint": "<string>",
                "expireDate": "<dateTime>"
            }
        ],
        "bucketChanges": [
            {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "loanAccountId": "<long>",
                "personId": "<long>",
                "type": "ADJUSTMENT",
                "pastDueAmount": "<double>",
                "fromBucket": "B1",
                "toBucket": "B3"
            },
            {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "loanAccountId": "<long>",
                "personId": "<long>",
                "type": "ADJUSTMENT",
                "pastDueAmount": "<double>",
                "fromBucket": "B3",
                "toBucket": "B4"
            }
        ],
        "loanAccountPayments": [
            {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "loanAccountId": "<long>",
                "paymentDate": "<dateTime>",
                "paymentAmount": "<double>",
                "paymentType": "Cheque",
                "paymentChannel": "<string>",
                "paymentReference": "<string>",
                "sequenceNumber": "<integer>",
                "isSeqCompleted": "<boolean>",
                "partialPaidInstallmentAmount": "<double>",
                "partialPaidDelayInterestAmount": "<double>",
                "partialPaidDelayKkdfAmount": "<double>",
                "partialPaidDelayBsmvAmount": "<double>",
                "totalPaymentAmount": "<double>"
            },
            {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "loanAccountId": "<long>",
                "paymentDate": "<dateTime>",
                "paymentAmount": "<double>",
                "paymentType": "EFT",
                "paymentChannel": "<string>",
                "paymentReference": "<string>",
                "sequenceNumber": "<integer>",
                "isSeqCompleted": "<boolean>",
                "partialPaidInstallmentAmount": "<double>",
                "partialPaidDelayInterestAmount": "<double>",
                "partialPaidDelayKkdfAmount": "<double>",
                "partialPaidDelayBsmvAmount": "<double>",
                "totalPaymentAmount": "<double>"
            }
        ],
        "loanAccountCautions": [
            {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "accountBranchCode": "<integer>",
                "accountNumber": "<integer>",
                "cautionAccountSuffix": "<integer>",
                "cautionKind": "<string>",
                "cautionDescription": "<string>",
                "currencyCode": "<string>",
                "balance": "<double>",
                "balanceTl": "<double>",
                "cautionType": "<string>",
                "cautionsRef": "<integer>",
                "engagementGuarantorInfo": "<long>",
                "engagementGuarantorNames": {
                    "guid": "<uuid>",
                    "name": "<string>",
                    "middleName": "<string>",
                    "surname": "<string>",
                    "firmName": "<string>"
                },
                "coreLastUpdateDate": "<dateTime>",
                "loanAccountId": "<long>",
                "personId": "<long>"
            },
            {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "accountBranchCode": "<integer>",
                "accountNumber": "<integer>",
                "cautionAccountSuffix": "<integer>",
                "cautionKind": "<string>",
                "cautionDescription": "<string>",
                "currencyCode": "<string>",
                "balance": "<double>",
                "balanceTl": "<double>",
                "cautionType": "<string>",
                "cautionsRef": "<integer>",
                "engagementGuarantorInfo": "<long>",
                "engagementGuarantorNames": {
                    "guid": "<uuid>",
                    "name": "<string>",
                    "middleName": "<string>",
                    "surname": "<string>",
                    "firmName": "<string>"
                },
                "coreLastUpdateDate": "<dateTime>",
                "loanAccountId": "<long>",
                "personId": "<long>"
            }
        ],
        "maturityDate": "<dateTime>",
        "balance": "<double>",
        "balanceTl": "<double>",
        "pursuable": "<double>",
        "pursuableTl": "<double>",
        "accountLimit": "<double>",
        "accountLimitTl": "<double>",
        "principalAmount": "<double>",
        "dueDate": "<dateTime>",
        "installmentNumber": "<integer>",
        "remainingInstallmentNumber": "<integer>",
        "maxDpd": "<integer>",
        "nextDueDate": "<dateTime>",
        "restructuredCount": "<integer>",
        "cautionAmount": "<double>",
        "delayRate": "<double>",
        "channelDetail": "<string>",
        "dealerName": "<string>",
        "dealerProductName": "<string>",
        "cautionName": "<string>",
        "firstPaymentFlag": "<string>",
        "insuranceFlag": "<string>",
        "insuranceName": "<string>",
        "campaignName": "<string>",
        "nplSuffix": "<integer>",
        "nplDate": "<dateTime>",
        "yySuffix": "<integer>",
        "yyDate": "<dateTime>"
    }
}
```
</details>

---

#### **_Retrieve a Base Account by LoanAccount AccountNumber_**

**GET** `/api/v3/Customer/GetBaseAccountByAccountNumber`

#### Description

Fetches a detailed loan account using its GUID identifier.

##### Query Parameters

| Parameter | Type      | Description |
| :-------- | :-------- | :---------- |
| `accountNumber`      | `string` |   (**_required_** )       |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/Customer/GetBaseAccountByAccountNumber?accountNumber=%3Cstring%3E" -H 'Accept: text/plain'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": {
        "id": "<long>",
        "guid": "<uuid>",
        "isActive": "<boolean>",
        "createDate": "<dateTime>",
        "createUserId": "<long>",
        "updateDate": "<dateTime>",
        "updateUserId": "<long>",
        "bucket": "B3",
        "leadAccountFlag": "<boolean>",
        "accountNumber": "<string>",
        "branchCode": "<integer>",
        "customerNumber": "<integer>",
        "personId": "<long>",
        "accountReference": "<string>",
        "usageDate": "<dateTime>",
        "accountSuffix": "<integer>",
        "type": "VADELI",
        "productCode": "<string>",
        "currencyCode": "<string>",
        "currentAccountIbanNumber": "<string>",
        "accDpd": "<integer>",
        "bucket1DueAmount": "<double>",
        "bucket1RemainingAmount": "<double>",
        "bucket1DueDate": "<dateTime>",
        "bucket2DueAmount": "<double>",
        "bucket2RemainingAmount": "<double>",
        "bucket2DueDate": "<dateTime>",
        "bucket3DueAmount": "<double>",
        "bucket3RemainingAmount": "<double>",
        "bucket3DueDate": "<dateTime>",
        "rollbackFlag": "<string>",
        "restructuredFlag": "<string>",
        "lastPaymentAmount": "<double>",
        "lastPaymentDate": "<dateTime>",
        "muacceliyetDate": "<dateTime>",
        "coreLastUpdateDate": "<dateTime>",
        "totalRemainingAmount": "<double>",
        "stagingImportId": "<long>"
    }
}

```

</details>

***


#### **_Retrieve Loan Accounts by Person Guid_**

**GET** `/api/v3/Customer/GetLoanAccountsByPersonGuid`

#### Description

Fetches loan accounts associated with a specific person's GUID.

##### Query Parameters

| Parameter | Type      | Description |
| :-------- | :-------- | :---------- |
| `personGuid`      | `guid` |   (**_required_** )       |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/Customer/GetLoanAccountsByPersonGuid?personGuid=%3Cuuid%3E" -H 'Accept: text/plain'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json

{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": [
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "isExistPromisePayment": "<boolean>",
            "bucket": "B4",
            "leadAccountFlag": "<boolean>",
            "accountNumber": "<string>",
            "branchCode": "<integer>",
            "customerNumber": "<integer>",
            "personId": "<long>",
            "accountReference": "<string>",
            "usageDate": "<dateTime>",
            "accountSuffix": "<integer>",
            "type": "Y_YAPILANRIMA_ITFA_BAGLANAN_KREDI",
            "productCode": "<string>",
            "currencyCode": "<string>",
            "currentAccountIbanNumber": "<string>",
            "accDpd": "<integer>",
            "bucket1DueAmount": "<double>",
            "bucket1RemainingAmount": "<double>",
            "bucket1DueDate": "<dateTime>",
            "bucket2DueAmount": "<double>",
            "bucket2RemainingAmount": "<double>",
            "bucket2DueDate": "<dateTime>",
            "bucket3DueAmount": "<double>",
            "bucket3RemainingAmount": "<double>",
            "bucket3DueDate": "<dateTime>",
            "rollbackFlag": "<string>",
            "restructuredFlag": "<string>",
            "lastPaymentAmount": "<double>",
            "lastPaymentDate": "<dateTime>",
            "muacceliyetDate": "<dateTime>",
            "coreLastUpdateDate": "<dateTime>",
            "stagingImportId": "<long>",
            "maturityDate": "<dateTime>",
            "balance": "<double>",
            "balanceTl": "<double>",
            "pursuable": "<double>",
            "pursuableTl": "<double>",
            "accountLimit": "<double>",
            "accountLimitTl": "<double>",
            "principalAmount": "<double>",
            "dueDate": "<dateTime>",
            "installmentNumber": "<integer>",
            "remainingInstallmentNumber": "<integer>",
            "maxDpd": "<integer>",
            "nextDueDate": "<dateTime>",
            "restructuredCount": "<integer>",
            "cautionAmount": "<double>",
            "delayRate": "<double>",
            "channelDetail": "<string>",
            "dealerName": "<string>",
            "dealerProductName": "<string>",
            "cautionName": "<string>",
            "firstPaymentFlag": "<string>",
            "insuranceFlag": "<string>",
            "insuranceName": "<string>",
            "campaignName": "<string>",
            "nplSuffix": "<integer>",
            "nplDate": "<dateTime>",
            "yySuffix": "<integer>",
            "yyDate": "<dateTime>"
        },
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "isExistPromisePayment": "<boolean>",
            "bucket": "B4",
            "leadAccountFlag": "<boolean>",
            "accountNumber": "<string>",
            "branchCode": "<integer>",
            "customerNumber": "<integer>",
            "personId": "<long>",
            "accountReference": "<string>",
            "usageDate": "<dateTime>",
            "accountSuffix": "<integer>",
            "type": "MUHTELIF_ALACAK",
            "productCode": "<string>",
            "currencyCode": "<string>",
            "currentAccountIbanNumber": "<string>",
            "accDpd": "<integer>",
            "bucket1DueAmount": "<double>",
            "bucket1RemainingAmount": "<double>",
            "bucket1DueDate": "<dateTime>",
            "bucket2DueAmount": "<double>",
            "bucket2RemainingAmount": "<double>",
            "bucket2DueDate": "<dateTime>",
            "bucket3DueAmount": "<double>",
            "bucket3RemainingAmount": "<double>",
            "bucket3DueDate": "<dateTime>",
            "rollbackFlag": "<string>",
            "restructuredFlag": "<string>",
            "lastPaymentAmount": "<double>",
            "lastPaymentDate": "<dateTime>",
            "muacceliyetDate": "<dateTime>",
            "coreLastUpdateDate": "<dateTime>",
            "stagingImportId": "<long>",
            "maturityDate": "<dateTime>",
            "balance": "<double>",
            "balanceTl": "<double>",
            "pursuable": "<double>",
            "pursuableTl": "<double>",
            "accountLimit": "<double>",
            "accountLimitTl": "<double>",
            "principalAmount": "<double>",
            "dueDate": "<dateTime>",
            "installmentNumber": "<integer>",
            "remainingInstallmentNumber": "<integer>",
            "maxDpd": "<integer>",
            "nextDueDate": "<dateTime>",
            "restructuredCount": "<integer>",
            "cautionAmount": "<double>",
            "delayRate": "<double>",
            "channelDetail": "<string>",
            "dealerName": "<string>",
            "dealerProductName": "<string>",
            "cautionName": "<string>",
            "firstPaymentFlag": "<string>",
            "insuranceFlag": "<string>",
            "insuranceName": "<string>",
            "campaignName": "<string>",
            "nplSuffix": "<integer>",
            "nplDate": "<dateTime>",
            "yySuffix": "<integer>",
            "yyDate": "<dateTime>"
        }
    ]
}

```
</details>

***


#### **_Retrieve Loan Accounts by Customer Number_**

**GET** `/api/v3/Customer/GetLoanAccountsByCustomerNumber`

#### Description

Fetches loan accounts associated with a specific customer number.

##### Query Parameters

| Parameter | Type      | Description |
| :-------- | :-------- | :---------- |
| `customerNumber`      | `integer` |   (**_required_** )       |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/Customer/GetLoanAccountsByCustomerNumber?customerNumber=%3Cinteger%3E" -H 'Accept: text/plain'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": [
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "isExistPromisePayment": "<boolean>",
            "bucket": "B4",
            "leadAccountFlag": "<boolean>",
            "accountNumber": "<string>",
            "branchCode": "<integer>",
            "customerNumber": "<integer>",
            "personId": "<long>",
            "accountReference": "<string>",
            "usageDate": "<dateTime>",
            "accountSuffix": "<integer>",
            "type": "Y_YAPILANRIMA_ITFA_BAGLANAN_KREDI",
            "productCode": "<string>",
            "currencyCode": "<string>",
            "currentAccountIbanNumber": "<string>",
            "accDpd": "<integer>",
            "bucket1DueAmount": "<double>",
            "bucket1RemainingAmount": "<double>",
            "bucket1DueDate": "<dateTime>",
            "bucket2DueAmount": "<double>",
            "bucket2RemainingAmount": "<double>",
            "bucket2DueDate": "<dateTime>",
            "bucket3DueAmount": "<double>",
            "bucket3RemainingAmount": "<double>",
            "bucket3DueDate": "<dateTime>",
            "rollbackFlag": "<string>",
            "restructuredFlag": "<string>",
            "lastPaymentAmount": "<double>",
            "lastPaymentDate": "<dateTime>",
            "muacceliyetDate": "<dateTime>",
            "coreLastUpdateDate": "<dateTime>",
            "stagingImportId": "<long>",
            "maturityDate": "<dateTime>",
            "balance": "<double>",
            "balanceTl": "<double>",
            "pursuable": "<double>",
            "pursuableTl": "<double>",
            "accountLimit": "<double>",
            "accountLimitTl": "<double>",
            "principalAmount": "<double>",
            "dueDate": "<dateTime>",
            "installmentNumber": "<integer>",
            "remainingInstallmentNumber": "<integer>",
            "maxDpd": "<integer>",
            "nextDueDate": "<dateTime>",
            "restructuredCount": "<integer>",
            "cautionAmount": "<double>",
            "delayRate": "<double>",
            "channelDetail": "<string>",
            "dealerName": "<string>",
            "dealerProductName": "<string>",
            "cautionName": "<string>",
            "firstPaymentFlag": "<string>",
            "insuranceFlag": "<string>",
            "insuranceName": "<string>",
            "campaignName": "<string>",
            "nplSuffix": "<integer>",
            "nplDate": "<dateTime>",
            "yySuffix": "<integer>",
            "yyDate": "<dateTime>"
        },
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "isExistPromisePayment": "<boolean>",
            "bucket": "B4",
            "leadAccountFlag": "<boolean>",
            "accountNumber": "<string>",
            "branchCode": "<integer>",
            "customerNumber": "<integer>",
            "personId": "<long>",
            "accountReference": "<string>",
            "usageDate": "<dateTime>",
            "accountSuffix": "<integer>",
            "type": "MUHTELIF_ALACAK",
            "productCode": "<string>",
            "currencyCode": "<string>",
            "currentAccountIbanNumber": "<string>",
            "accDpd": "<integer>",
            "bucket1DueAmount": "<double>",
            "bucket1RemainingAmount": "<double>",
            "bucket1DueDate": "<dateTime>",
            "bucket2DueAmount": "<double>",
            "bucket2RemainingAmount": "<double>",
            "bucket2DueDate": "<dateTime>",
            "bucket3DueAmount": "<double>",
            "bucket3RemainingAmount": "<double>",
            "bucket3DueDate": "<dateTime>",
            "rollbackFlag": "<string>",
            "restructuredFlag": "<string>",
            "lastPaymentAmount": "<double>",
            "lastPaymentDate": "<dateTime>",
            "muacceliyetDate": "<dateTime>",
            "coreLastUpdateDate": "<dateTime>",
            "stagingImportId": "<long>",
            "maturityDate": "<dateTime>",
            "balance": "<double>",
            "balanceTl": "<double>",
            "pursuable": "<double>",
            "pursuableTl": "<double>",
            "accountLimit": "<double>",
            "accountLimitTl": "<double>",
            "principalAmount": "<double>",
            "dueDate": "<dateTime>",
            "installmentNumber": "<integer>",
            "remainingInstallmentNumber": "<integer>",
            "maxDpd": "<integer>",
            "nextDueDate": "<dateTime>",
            "restructuredCount": "<integer>",
            "cautionAmount": "<double>",
            "delayRate": "<double>",
            "channelDetail": "<string>",
            "dealerName": "<string>",
            "dealerProductName": "<string>",
            "cautionName": "<string>",
            "firstPaymentFlag": "<string>",
            "insuranceFlag": "<string>",
            "insuranceName": "<string>",
            "campaignName": "<string>",
            "nplSuffix": "<integer>",
            "nplDate": "<dateTime>",
            "yySuffix": "<integer>",
            "yyDate": "<dateTime>"
        }
    ]
}
```
</details>

---


#### **_Retrieve a Card Account by Loan Account Guid_**

**GET** `/api/v3/Customer/GetCardAccountByGuid`

#### Description

Fetches a detailed card account using its GUID identifier.

##### Query Parameters

| Parameter | Type      | Description |
| :-------- | :-------- | :---------- |
| `guid`      | `guid` |   (**_required_** )       |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/Customer/GetCardAccountByGuid?guid=%3Cuuid%3E" -H 'Accept: text/plain'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": {
        "id": "<long>",
        "guid": "<uuid>",
        "isActive": "<boolean>",
        "createDate": "<dateTime>",
        "createUserId": "<long>",
        "updateDate": "<dateTime>",
        "updateUserId": "<long>",
        "isExistPromisePayment": "<boolean>",
        "bucket": "B3",
        "leadAccountFlag": "<boolean>",
        "accountNumber": "<string>",
        "branchCode": "<integer>",
        "customerNumber": "<long>",
        "person": {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "segment": "<string>",
            "customerId": "<long>",
            "customerNumber": "<long>",
            "relationCustNum": "<long>",
            "relationType": "CHILD",
            "identityNumber": "<string>",
            "name": "<string>",
            "middleName": "<string>",
            "surname": "<string>",
            "firmName": "<string>",
            "personnelFlag": "<boolean>",
            "vipFlag": "<boolean>",
            "birthDate": "<dateTime>",
            "birthPlace": "<string>",
            "workflowCode": "<string>",
            "gender": "Female",
            "dateOfDeath": "<dateTime>",
            "coreLastUpdateDate": "<dateTime>",
            "workIsMailing": "<boolean>",
            "nplFlag": "<boolean>",
            "selfCuredFlag": "<boolean>",
            "nplDate": "<dateTime>",
            "lastKrsSearchDate": "<dateTime>",
            "currentKkbScore": "<integer>",
            "creditCardUsageRate": "<double>",
            "kmhUsageRate": "<double>",
            "collectionScore": "<string>",
            "lastMonthApplicationCount": "<integer>",
            "otherBankMortgageLoanPaymentPerformance": "<string>",
            "blockageFlag": "<boolean>",
            "hepsiDpdMaxLm": "<integer>",
            "sumNumFailL3m": "<integer>",
            "tumKredilerDpdMaxMin6": "<integer>",
            "avgAsinitsBurganOverOutsV12lm": "<string>",
            "hepsiDpdMaxL12m": "<integer>",
            "hepsiDpdLm": "<integer>",
            "hepsiDpdMaxV3lm": "<string>",
            "hepsiTotalOutsV3lm": "<string>",
            "hepsiDpdAmtOutsVlm": "<string>",
            "hepsiDpdAmtOutsMax12": "<double>",
            "modelType": "<string>",
            "finalRatio": "<double>",
            "totalCashRisk": "<double>",
            "totalLimit": "<double>",
            "totalRisk": "<double>",
            "totalPursuable": "<double>",
            "minPursuable": "<double>",
            "totalAssets": "<double>",
            "totalColleteral": "<double>",
            "totalLimitUtilRatio": "<double>",
            "allMaxDpd": "<integer>",
            "engagementGuarantorInfo": "<string>"
        },
        "personId": "<long>",
        "accountReference": "<string>",
        "usageDate": "<dateTime>",
        "accountSuffix": "<integer>",
        "type": "TASFIYE_ALACAK",
        "productCode": "<string>",
        "currencyCode": "<string>",
        "currentAccountIbanNumber": "<string>",
        "accDpd": "<integer>",
        "bucket1DueAmount": "<double>",
        "bucket1RemainingAmount": "<double>",
        "bucket1DueDate": "<dateTime>",
        "bucket2DueAmount": "<double>",
        "bucket2RemainingAmount": "<double>",
        "bucket2DueDate": "<dateTime>",
        "bucket3DueAmount": "<double>",
        "bucket3RemainingAmount": "<double>",
        "bucket3DueDate": "<dateTime>",
        "rollbackFlag": "<string>",
        "restructuredFlag": "<string>",
        "lastPaymentAmount": "<double>",
        "lastPaymentDate": "<dateTime>",
        "muacceliyetDate": "<dateTime>",
        "coreLastUpdateDate": "<dateTime>",
        "stagingImport": {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "startDate": "<dateTime>",
            "endDate": "<dateTime>",
            "status": "PENDING",
            "errorLog": "<string>"
        },
        "stagingImportId": "<long>",
        "promisePayments": [
            {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "activityId": "<long>",
                "loanAccountId": "<long>",
                "personId": "<long>",
                "relationType": "AGENT",
                "promiseDate": "<dateTime>",
                "promiseAmount": "<double>",
                "sequenceNumber": "<integer>",
                "note": "<string>",
                "isPaid": "<boolean>",
                "loanAccountPaymentId": "<long>",
                "giveName": "<string>",
                "accountNumber": "<string>",
                "activityCreateDate": "<dateTime>"
            },
            {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "activityId": "<long>",
                "loanAccountId": "<long>",
                "personId": "<long>",
                "relationType": "CHILD",
                "promiseDate": "<dateTime>",
                "promiseAmount": "<double>",
                "sequenceNumber": "<integer>",
                "note": "<string>",
                "isPaid": "<boolean>",
                "loanAccountPaymentId": "<long>",
                "giveName": "<string>",
                "accountNumber": "<string>",
                "activityCreateDate": "<dateTime>"
            }
        ],
        "workActions": [
            {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "status": "SUCCESS",
                "worklistId": "<long>",
                "personId": "<long>",
                "loanAccountId": "<long>",
                "template": "<string>",
                "templateParameter": "<string>",
                "contactPersonId": "<long>",
                "contactRole": "FATHER",
                "contactPoint": "<string>",
                "expireDate": "<dateTime>"
            },
            {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "status": "FAILED",
                "worklistId": "<long>",
                "personId": "<long>",
                "loanAccountId": "<long>",
                "template": "<string>",
                "templateParameter": "<string>",
                "contactPersonId": "<long>",
                "contactRole": "FATHER",
                "contactPoint": "<string>",
                "expireDate": "<dateTime>"
            }
        ],
        "bucketChanges": [
            {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "loanAccountId": "<long>",
                "personId": "<long>",
                "type": "PAYMENT",
                "pastDueAmount": "<double>",
                "fromBucket": "B1",
                "toBucket": "B3"
            },
            {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "loanAccountId": "<long>",
                "personId": "<long>",
                "type": "PAYMENT",
                "pastDueAmount": "<double>",
                "fromBucket": "B1",
                "toBucket": "B0"
            }
        ],
        "loanAccountPayments": [
            {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "loanAccountId": "<long>",
                "paymentDate": "<dateTime>",
                "paymentAmount": "<double>",
                "paymentType": "Other",
                "paymentChannel": "<string>",
                "paymentReference": "<string>",
                "sequenceNumber": "<integer>",
                "isSeqCompleted": "<boolean>",
                "partialPaidInstallmentAmount": "<double>",
                "partialPaidDelayInterestAmount": "<double>",
                "partialPaidDelayKkdfAmount": "<double>",
                "partialPaidDelayBsmvAmount": "<double>",
                "totalPaymentAmount": "<double>"
            },
            {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "loanAccountId": "<long>",
                "paymentDate": "<dateTime>",
                "paymentAmount": "<double>",
                "paymentType": "Transfer",
                "paymentChannel": "<string>",
                "paymentReference": "<string>",
                "sequenceNumber": "<integer>",
                "isSeqCompleted": "<boolean>",
                "partialPaidInstallmentAmount": "<double>",
                "partialPaidDelayInterestAmount": "<double>",
                "partialPaidDelayKkdfAmount": "<double>",
                "partialPaidDelayBsmvAmount": "<double>",
                "totalPaymentAmount": "<double>"
            }
        ],
        "loanAccountCautions": [
            {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "accountBranchCode": "<integer>",
                "accountNumber": "<integer>",
                "cautionAccountSuffix": "<integer>",
                "cautionKind": "<string>",
                "cautionDescription": "<string>",
                "currencyCode": "<string>",
                "balance": "<double>",
                "balanceTl": "<double>",
                "cautionType": "<string>",
                "cautionsRef": "<integer>",
                "engagementGuarantorInfo": "<long>",
                "engagementGuarantorNames": {
                    "guid": "<uuid>",
                    "name": "<string>",
                    "middleName": "<string>",
                    "surname": "<string>",
                    "firmName": "<string>"
                },
                "coreLastUpdateDate": "<dateTime>",
                "loanAccountId": "<long>",
                "personId": "<long>"
            },
            {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "accountBranchCode": "<integer>",
                "accountNumber": "<integer>",
                "cautionAccountSuffix": "<integer>",
                "cautionKind": "<string>",
                "cautionDescription": "<string>",
                "currencyCode": "<string>",
                "balance": "<double>",
                "balanceTl": "<double>",
                "cautionType": "<string>",
                "cautionsRef": "<integer>",
                "engagementGuarantorInfo": "<long>",
                "engagementGuarantorNames": {
                    "guid": "<uuid>",
                    "name": "<string>",
                    "middleName": "<string>",
                    "surname": "<string>",
                    "firmName": "<string>"
                },
                "coreLastUpdateDate": "<dateTime>",
                "loanAccountId": "<long>",
                "personId": "<long>"
            }
        ],
        "cardStatus": "<string>",
        "cardNumber": "<string>",
        "statementDate": "<dateTime>",
        "statementDueDate": "<dateTime>",
        "statementAmount": "<double>",
        "statementMinimumPayableAmount": "<double>",
        "cardTotalDebitAmount": "<double>",
        "cardLimit": "<double>",
        "cardAvailableLimit": "<double>",
        "cardCashLimit": "<double>",
        "cardCloseAmount": "<double>",
        "cardAutoPaymentOrderFlag": "<string>",
        "additionalCardExistFlag": "<string>",
        "cardDeliveryAddress": "<string>",
        "cardDelayStatus": "<string>",
        "delayBeginDate": "<dateTime>",
        "legalMinimumPaymentAnnual": "<integer>",
        "legalMinimumPaymentFreq": "<integer>",
        "interestRate": "<double>",
        "delayInterestRate": "<double>",
        "cashInterestRate": "<double>",
        "customerSegmentInfo": "<string>",
        "lastStatementAmount": "<double>",
        "lastStatementRemainingAmount": "<double>",
        "statementCardAmount": "<double>",
        "statementCardRemainingAmount": "<double>"
    }
}
```
</details>

---


#### **_Retrieve Card Accounts by Person Guid_**

**GET** `/api/v3/Customer/GetCardAccountsByPersonGuid`

#### Description

Fetches card accounts associated with a specific person's GUID.

##### Query Parameters

| Parameter | Type      | Description |
| :-------- | :-------- | :---------- |
| `personGuid`      | `guid` |   (**_required_** )       |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/Customer/GetCardAccountsByPersonGuid?personGuid=%3Cuuid%3E" -H 'Accept: text/plain'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": [
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "isExistPromisePayment": "<boolean>",
            "bucket": "B3",
            "leadAccountFlag": "<boolean>",
            "accountNumber": "<string>",
            "branchCode": "<integer>",
            "customerNumber": "<long>",
            "person": {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "segment": "<string>",
                "customerId": "<long>",
                "customerNumber": "<long>",
                "relationCustNum": "<long>",
                "relationType": "SIBLING",
                "identityNumber": "<string>",
                "name": "<string>",
                "middleName": "<string>",
                "surname": "<string>",
                "firmName": "<string>",
                "personnelFlag": "<boolean>",
                "vipFlag": "<boolean>",
                "birthDate": "<dateTime>",
                "birthPlace": "<string>",
                "workflowCode": "<string>",
                "gender": "Female",
                "dateOfDeath": "<dateTime>",
                "coreLastUpdateDate": "<dateTime>",
                "workIsMailing": "<boolean>",
                "nplFlag": "<boolean>",
                "selfCuredFlag": "<boolean>",
                "nplDate": "<dateTime>",
                "lastKrsSearchDate": "<dateTime>",
                "currentKkbScore": "<integer>",
                "creditCardUsageRate": "<double>",
                "kmhUsageRate": "<double>",
                "collectionScore": "<string>",
                "lastMonthApplicationCount": "<integer>",
                "otherBankMortgageLoanPaymentPerformance": "<string>",
                "blockageFlag": "<boolean>",
                "hepsiDpdMaxLm": "<integer>",
                "sumNumFailL3m": "<integer>",
                "tumKredilerDpdMaxMin6": "<integer>",
                "avgAsinitsBurganOverOutsV12lm": "<string>",
                "hepsiDpdMaxL12m": "<integer>",
                "hepsiDpdLm": "<integer>",
                "hepsiDpdMaxV3lm": "<string>",
                "hepsiTotalOutsV3lm": "<string>",
                "hepsiDpdAmtOutsVlm": "<string>",
                "hepsiDpdAmtOutsMax12": "<double>",
                "modelType": "<string>",
                "finalRatio": "<double>",
                "totalCashRisk": "<double>",
                "totalLimit": "<double>",
                "totalRisk": "<double>",
                "totalPursuable": "<double>",
                "minPursuable": "<double>",
                "totalAssets": "<double>",
                "totalColleteral": "<double>",
                "totalLimitUtilRatio": "<double>",
                "allMaxDpd": "<integer>",
                "engagementGuarantorInfo": "<string>"
            },
            "personId": "<long>",
            "accountReference": "<string>",
            "usageDate": "<dateTime>",
            "accountSuffix": "<integer>",
            "type": "VADESIZ",
            "productCode": "<string>",
            "currencyCode": "<string>",
            "currentAccountIbanNumber": "<string>",
            "accDpd": "<integer>",
            "bucket1DueAmount": "<double>",
            "bucket1RemainingAmount": "<double>",
            "bucket1DueDate": "<dateTime>",
            "bucket2DueAmount": "<double>",
            "bucket2RemainingAmount": "<double>",
            "bucket2DueDate": "<dateTime>",
            "bucket3DueAmount": "<double>",
            "bucket3RemainingAmount": "<double>",
            "bucket3DueDate": "<dateTime>",
            "rollbackFlag": "<string>",
            "restructuredFlag": "<string>",
            "lastPaymentAmount": "<double>",
            "lastPaymentDate": "<dateTime>",
            "muacceliyetDate": "<dateTime>",
            "coreLastUpdateDate": "<dateTime>",
            "stagingImport": {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "startDate": "<dateTime>",
                "endDate": "<dateTime>",
                "status": "FAILED",
                "errorLog": "<string>"
            },
            "stagingImportId": "<long>",
            "cardStatus": "<string>",
            "cardNumber": "<string>",
            "statementDate": "<dateTime>",
            "statementDueDate": "<dateTime>",
            "statementAmount": "<double>",
            "statementMinimumPayableAmount": "<double>",
            "cardTotalDebitAmount": "<double>",
            "cardLimit": "<double>",
            "cardAvailableLimit": "<double>",
            "cardCashLimit": "<double>",
            "cardCloseAmount": "<double>",
            "cardAutoPaymentOrderFlag": "<string>",
            "additionalCardExistFlag": "<string>",
            "cardDeliveryAddress": "<string>",
            "cardDelayStatus": "<string>",
            "delayBeginDate": "<dateTime>",
            "legalMinimumPaymentAnnual": "<integer>",
            "legalMinimumPaymentFreq": "<integer>",
            "interestRate": "<double>",
            "delayInterestRate": "<double>",
            "cashInterestRate": "<double>",
            "customerSegmentInfo": "<string>",
            "lastStatementAmount": "<double>",
            "lastStatementRemainingAmount": "<double>",
            "statementCardAmount": "<double>",
            "statementCardRemainingAmount": "<double>"
        },
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "isExistPromisePayment": "<boolean>",
            "bucket": "B3",
            "leadAccountFlag": "<boolean>",
            "accountNumber": "<string>",
            "branchCode": "<integer>",
            "customerNumber": "<long>",
            "person": {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "segment": "<string>",
                "customerId": "<long>",
                "customerNumber": "<long>",
                "relationCustNum": "<long>",
                "relationType": "SPOUSE",
                "identityNumber": "<string>",
                "name": "<string>",
                "middleName": "<string>",
                "surname": "<string>",
                "firmName": "<string>",
                "personnelFlag": "<boolean>",
                "vipFlag": "<boolean>",
                "birthDate": "<dateTime>",
                "birthPlace": "<string>",
                "workflowCode": "<string>",
                "gender": "Female",
                "dateOfDeath": "<dateTime>",
                "coreLastUpdateDate": "<dateTime>",
                "workIsMailing": "<boolean>",
                "nplFlag": "<boolean>",
                "selfCuredFlag": "<boolean>",
                "nplDate": "<dateTime>",
                "lastKrsSearchDate": "<dateTime>",
                "currentKkbScore": "<integer>",
                "creditCardUsageRate": "<double>",
                "kmhUsageRate": "<double>",
                "collectionScore": "<string>",
                "lastMonthApplicationCount": "<integer>",
                "otherBankMortgageLoanPaymentPerformance": "<string>",
                "blockageFlag": "<boolean>",
                "hepsiDpdMaxLm": "<integer>",
                "sumNumFailL3m": "<integer>",
                "tumKredilerDpdMaxMin6": "<integer>",
                "avgAsinitsBurganOverOutsV12lm": "<string>",
                "hepsiDpdMaxL12m": "<integer>",
                "hepsiDpdLm": "<integer>",
                "hepsiDpdMaxV3lm": "<string>",
                "hepsiTotalOutsV3lm": "<string>",
                "hepsiDpdAmtOutsVlm": "<string>",
                "hepsiDpdAmtOutsMax12": "<double>",
                "modelType": "<string>",
                "finalRatio": "<double>",
                "totalCashRisk": "<double>",
                "totalLimit": "<double>",
                "totalRisk": "<double>",
                "totalPursuable": "<double>",
                "minPursuable": "<double>",
                "totalAssets": "<double>",
                "totalColleteral": "<double>",
                "totalLimitUtilRatio": "<double>",
                "allMaxDpd": "<integer>",
                "engagementGuarantorInfo": "<string>"
            },
            "personId": "<long>",
            "accountReference": "<string>",
            "usageDate": "<dateTime>",
            "accountSuffix": "<integer>",
            "type": "OZEL_KARSILIK",
            "productCode": "<string>",
            "currencyCode": "<string>",
            "currentAccountIbanNumber": "<string>",
            "accDpd": "<integer>",
            "bucket1DueAmount": "<double>",
            "bucket1RemainingAmount": "<double>",
            "bucket1DueDate": "<dateTime>",
            "bucket2DueAmount": "<double>",
            "bucket2RemainingAmount": "<double>",
            "bucket2DueDate": "<dateTime>",
            "bucket3DueAmount": "<double>",
            "bucket3RemainingAmount": "<double>",
            "bucket3DueDate": "<dateTime>",
            "rollbackFlag": "<string>",
            "restructuredFlag": "<string>",
            "lastPaymentAmount": "<double>",
            "lastPaymentDate": "<dateTime>",
            "muacceliyetDate": "<dateTime>",
            "coreLastUpdateDate": "<dateTime>",
            "stagingImport": {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "startDate": "<dateTime>",
                "endDate": "<dateTime>",
                "status": "PENDING",
                "errorLog": "<string>"
            },
            "stagingImportId": "<long>",
            "cardStatus": "<string>",
            "cardNumber": "<string>",
            "statementDate": "<dateTime>",
            "statementDueDate": "<dateTime>",
            "statementAmount": "<double>",
            "statementMinimumPayableAmount": "<double>",
            "cardTotalDebitAmount": "<double>",
            "cardLimit": "<double>",
            "cardAvailableLimit": "<double>",
            "cardCashLimit": "<double>",
            "cardCloseAmount": "<double>",
            "cardAutoPaymentOrderFlag": "<string>",
            "additionalCardExistFlag": "<string>",
            "cardDeliveryAddress": "<string>",
            "cardDelayStatus": "<string>",
            "delayBeginDate": "<dateTime>",
            "legalMinimumPaymentAnnual": "<integer>",
            "legalMinimumPaymentFreq": "<integer>",
            "interestRate": "<double>",
            "delayInterestRate": "<double>",
            "cashInterestRate": "<double>",
            "customerSegmentInfo": "<string>",
            "lastStatementAmount": "<double>",
            "lastStatementRemainingAmount": "<double>",
            "statementCardAmount": "<double>",
            "statementCardRemainingAmount": "<double>"
        }
    ]
}
```
</details>

***


#### **_Retrieve Card Accounts by Loan Account Customer Number_**

**GET** `/api/v3/Customer/GetCardAccountsByCustomerNumber`

#### Description

Fetches card accounts associated with a specific customer number.

##### Query Parameters

| Parameter | Type      | Description |
| :-------- | :-------- | :---------- |
| `customerNumber`      | `integer` |   (**_required_** )       |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/Customer/GetCardAccountsByCustomerNumber?customerNumber=%3Cinteger%3E" -H 'Accept: text/plain'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": [
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "isExistPromisePayment": "<boolean>",
            "bucket": "B3",
            "leadAccountFlag": "<boolean>",
            "accountNumber": "<string>",
            "branchCode": "<integer>",
            "customerNumber": "<long>",
            "person": {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "segment": "<string>",
                "customerId": "<long>",
                "customerNumber": "<long>",
                "relationCustNum": "<long>",
                "relationType": "SIBLING",
                "identityNumber": "<string>",
                "name": "<string>",
                "middleName": "<string>",
                "surname": "<string>",
                "firmName": "<string>",
                "personnelFlag": "<boolean>",
                "vipFlag": "<boolean>",
                "birthDate": "<dateTime>",
                "birthPlace": "<string>",
                "workflowCode": "<string>",
                "gender": "Female",
                "dateOfDeath": "<dateTime>",
                "coreLastUpdateDate": "<dateTime>",
                "workIsMailing": "<boolean>",
                "nplFlag": "<boolean>",
                "selfCuredFlag": "<boolean>",
                "nplDate": "<dateTime>",
                "lastKrsSearchDate": "<dateTime>",
                "currentKkbScore": "<integer>",
                "creditCardUsageRate": "<double>",
                "kmhUsageRate": "<double>",
                "collectionScore": "<string>",
                "lastMonthApplicationCount": "<integer>",
                "otherBankMortgageLoanPaymentPerformance": "<string>",
                "blockageFlag": "<boolean>",
                "hepsiDpdMaxLm": "<integer>",
                "sumNumFailL3m": "<integer>",
                "tumKredilerDpdMaxMin6": "<integer>",
                "avgAsinitsBurganOverOutsV12lm": "<string>",
                "hepsiDpdMaxL12m": "<integer>",
                "hepsiDpdLm": "<integer>",
                "hepsiDpdMaxV3lm": "<string>",
                "hepsiTotalOutsV3lm": "<string>",
                "hepsiDpdAmtOutsVlm": "<string>",
                "hepsiDpdAmtOutsMax12": "<double>",
                "modelType": "<string>",
                "finalRatio": "<double>",
                "totalCashRisk": "<double>",
                "totalLimit": "<double>",
                "totalRisk": "<double>",
                "totalPursuable": "<double>",
                "minPursuable": "<double>",
                "totalAssets": "<double>",
                "totalColleteral": "<double>",
                "totalLimitUtilRatio": "<double>",
                "allMaxDpd": "<integer>",
                "engagementGuarantorInfo": "<string>"
            },
            "personId": "<long>",
            "accountReference": "<string>",
            "usageDate": "<dateTime>",
            "accountSuffix": "<integer>",
            "type": "VADESIZ",
            "productCode": "<string>",
            "currencyCode": "<string>",
            "currentAccountIbanNumber": "<string>",
            "accDpd": "<integer>",
            "bucket1DueAmount": "<double>",
            "bucket1RemainingAmount": "<double>",
            "bucket1DueDate": "<dateTime>",
            "bucket2DueAmount": "<double>",
            "bucket2RemainingAmount": "<double>",
            "bucket2DueDate": "<dateTime>",
            "bucket3DueAmount": "<double>",
            "bucket3RemainingAmount": "<double>",
            "bucket3DueDate": "<dateTime>",
            "rollbackFlag": "<string>",
            "restructuredFlag": "<string>",
            "lastPaymentAmount": "<double>",
            "lastPaymentDate": "<dateTime>",
            "muacceliyetDate": "<dateTime>",
            "coreLastUpdateDate": "<dateTime>",
            "stagingImport": {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "startDate": "<dateTime>",
                "endDate": "<dateTime>",
                "status": "FAILED",
                "errorLog": "<string>"
            },
            "stagingImportId": "<long>",
            "cardStatus": "<string>",
            "cardNumber": "<string>",
            "statementDate": "<dateTime>",
            "statementDueDate": "<dateTime>",
            "statementAmount": "<double>",
            "statementMinimumPayableAmount": "<double>",
            "cardTotalDebitAmount": "<double>",
            "cardLimit": "<double>",
            "cardAvailableLimit": "<double>",
            "cardCashLimit": "<double>",
            "cardCloseAmount": "<double>",
            "cardAutoPaymentOrderFlag": "<string>",
            "additionalCardExistFlag": "<string>",
            "cardDeliveryAddress": "<string>",
            "cardDelayStatus": "<string>",
            "delayBeginDate": "<dateTime>",
            "legalMinimumPaymentAnnual": "<integer>",
            "legalMinimumPaymentFreq": "<integer>",
            "interestRate": "<double>",
            "delayInterestRate": "<double>",
            "cashInterestRate": "<double>",
            "customerSegmentInfo": "<string>",
            "lastStatementAmount": "<double>",
            "lastStatementRemainingAmount": "<double>",
            "statementCardAmount": "<double>",
            "statementCardRemainingAmount": "<double>"
        },
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "isExistPromisePayment": "<boolean>",
            "bucket": "B3",
            "leadAccountFlag": "<boolean>",
            "accountNumber": "<string>",
            "branchCode": "<integer>",
            "customerNumber": "<long>",
            "person": {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "segment": "<string>",
                "customerId": "<long>",
                "customerNumber": "<long>",
                "relationCustNum": "<long>",
                "relationType": "SPOUSE",
                "identityNumber": "<string>",
                "name": "<string>",
                "middleName": "<string>",
                "surname": "<string>",
                "firmName": "<string>",
                "personnelFlag": "<boolean>",
                "vipFlag": "<boolean>",
                "birthDate": "<dateTime>",
                "birthPlace": "<string>",
                "workflowCode": "<string>",
                "gender": "Female",
                "dateOfDeath": "<dateTime>",
                "coreLastUpdateDate": "<dateTime>",
                "workIsMailing": "<boolean>",
                "nplFlag": "<boolean>",
                "selfCuredFlag": "<boolean>",
                "nplDate": "<dateTime>",
                "lastKrsSearchDate": "<dateTime>",
                "currentKkbScore": "<integer>",
                "creditCardUsageRate": "<double>",
                "kmhUsageRate": "<double>",
                "collectionScore": "<string>",
                "lastMonthApplicationCount": "<integer>",
                "otherBankMortgageLoanPaymentPerformance": "<string>",
                "blockageFlag": "<boolean>",
                "hepsiDpdMaxLm": "<integer>",
                "sumNumFailL3m": "<integer>",
                "tumKredilerDpdMaxMin6": "<integer>",
                "avgAsinitsBurganOverOutsV12lm": "<string>",
                "hepsiDpdMaxL12m": "<integer>",
                "hepsiDpdLm": "<integer>",
                "hepsiDpdMaxV3lm": "<string>",
                "hepsiTotalOutsV3lm": "<string>",
                "hepsiDpdAmtOutsVlm": "<string>",
                "hepsiDpdAmtOutsMax12": "<double>",
                "modelType": "<string>",
                "finalRatio": "<double>",
                "totalCashRisk": "<double>",
                "totalLimit": "<double>",
                "totalRisk": "<double>",
                "totalPursuable": "<double>",
                "minPursuable": "<double>",
                "totalAssets": "<double>",
                "totalColleteral": "<double>",
                "totalLimitUtilRatio": "<double>",
                "allMaxDpd": "<integer>",
                "engagementGuarantorInfo": "<string>"
            },
            "personId": "<long>",
            "accountReference": "<string>",
            "usageDate": "<dateTime>",
            "accountSuffix": "<integer>",
            "type": "OZEL_KARSILIK",
            "productCode": "<string>",
            "currencyCode": "<string>",
            "currentAccountIbanNumber": "<string>",
            "accDpd": "<integer>",
            "bucket1DueAmount": "<double>",
            "bucket1RemainingAmount": "<double>",
            "bucket1DueDate": "<dateTime>",
            "bucket2DueAmount": "<double>",
            "bucket2RemainingAmount": "<double>",
            "bucket2DueDate": "<dateTime>",
            "bucket3DueAmount": "<double>",
            "bucket3RemainingAmount": "<double>",
            "bucket3DueDate": "<dateTime>",
            "rollbackFlag": "<string>",
            "restructuredFlag": "<string>",
            "lastPaymentAmount": "<double>",
            "lastPaymentDate": "<dateTime>",
            "muacceliyetDate": "<dateTime>",
            "coreLastUpdateDate": "<dateTime>",
            "stagingImport": {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "startDate": "<dateTime>",
                "endDate": "<dateTime>",
                "status": "PENDING",
                "errorLog": "<string>"
            },
            "stagingImportId": "<long>",
            "cardStatus": "<string>",
            "cardNumber": "<string>",
            "statementDate": "<dateTime>",
            "statementDueDate": "<dateTime>",
            "statementAmount": "<double>",
            "statementMinimumPayableAmount": "<double>",
            "cardTotalDebitAmount": "<double>",
            "cardLimit": "<double>",
            "cardAvailableLimit": "<double>",
            "cardCashLimit": "<double>",
            "cardCloseAmount": "<double>",
            "cardAutoPaymentOrderFlag": "<string>",
            "additionalCardExistFlag": "<string>",
            "cardDeliveryAddress": "<string>",
            "cardDelayStatus": "<string>",
            "delayBeginDate": "<dateTime>",
            "legalMinimumPaymentAnnual": "<integer>",
            "legalMinimumPaymentFreq": "<integer>",
            "interestRate": "<double>",
            "delayInterestRate": "<double>",
            "cashInterestRate": "<double>",
            "customerSegmentInfo": "<string>",
            "lastStatementAmount": "<double>",
            "lastStatementRemainingAmount": "<double>",
            "statementCardAmount": "<double>",
            "statementCardRemainingAmount": "<double>"
        }
    ]
}
```
</details>

***


#### **_Retrieve Phone Numbers by Person Guid_**

**GET** `/api/v3/Customer/GetPhonesByPersonGuid`

#### Description

Fetches all phone numbers associated with a given person's GUID. This is useful for retrieving contact details linked to a person record.

##### Query Parameters

| Parameter | Type      | Description |
| :-------- | :-------- | :---------- |
| `personGuid`      | `guid` |   (**_required_** )       |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/Customer/GetPhonesByPersonGuid?personGuid=%3Cuuid%3E" -H 'Accept: text/plain'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": [
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "phoneNumberText": "<string>",
            "type": "Work",
            "name": "<string>",
            "isDefault": "<boolean>",
            "personId": "<long>",
            "lastSuccessfulCallDate": "<dateTime>"
        },
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "phoneNumberText": "<string>",
            "type": "Fax",
            "name": "<string>",
            "isDefault": "<boolean>",
            "personId": "<long>",
            "lastSuccessfulCallDate": "<dateTime>"
        }
    ]
}

```
</details>

---


#### **_Retrieve Emais by Person Guid_**

**GET** `/api/v3/Customer/GetEmailsByPersonGuid`

#### Description

Fetches all emails associated with a given person's GUID. This endpoint is intended for retrieving all registered email addresses for a specific individual.

##### Query Parameters

| Parameter | Type      | Description |
| :-------- | :-------- | :---------- |
| `personGuid`      | `guid` |   (**_required_** )       |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/Customer/GetEmailsByPersonGuid?personGuid=%3Cuuid%3E" -H 'Accept: text/plain'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": [
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "eMailAddress": "<string>",
            "isDefault": "<boolean>",
            "personId": "<long>"
        },
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "eMailAddress": "<string>",
            "isDefault": "<boolean>",
            "personId": "<long>"
        }
    ]
}
```
</details>

---


#### **_Retrieve Addresses by Person Guid_**

**GET** `/api/v3/Customer/GetAddressesByPersonGuid`

#### Description

Fetches all Addresses associated with a given person's GUID. This endpoint is intended for retrieving all registered addresses for a specific individual.

##### Query Parameters

| Parameter | Type      | Description |
| :-------- | :-------- | :---------- |
| `personGuid`      | `guid` |   (**_required_** )       |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/Customer/GetAddressesByPersonGuid?personGuid=%3Cuuid%3E" -H 'Accept: text/plain'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": [
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "name": "<string>",
            "district": "<string>",
            "street": "<string>",
            "addressText": "<string>",
            "town": "<string>",
            "city": "<string>",
            "postalCode": "<string>",
            "country": "<string>",
            "isDefault": "<boolean>",
            "personId": "<long>"
        },
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "name": "<string>",
            "district": "<string>",
            "street": "<string>",
            "addressText": "<string>",
            "town": "<string>",
            "city": "<string>",
            "postalCode": "<string>",
            "country": "<string>",
            "isDefault": "<boolean>",
            "personId": "<long>"
        }
    ]
}
```
</details>

---

#### **_Create a Phone Number_**

**POST** `/api/v3/Customer/CreatePhone`

#### Description

Registers a new phone number in the system.

##### Query Parameters

| Parameter       | Type | Description |
| :-------------- | :--- | :---------- |
| `no parameters` |      |             |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X POST "http://localhost:7080/api/v3/Customer/CreatePhone" -H 'Accept: text/plain' -data '{
  "phoneNumberText": "<string>",
  "type": "MobileSms",
  "name": "<string>",
  "isDefault": "<boolean>",
  "personId": "<long>",
  "stagingImportId": "<long>",
  "lastSuccessfulCallDate": "<dateTime>"
}'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": {
        "id": "<long>",
        "guid": "<uuid>",
        "isActive": "<boolean>",
        "createDate": "<dateTime>",
        "createUserId": "<long>",
        "updateDate": "<dateTime>",
        "updateUserId": "<long>",
        "phoneNumberText": "<string>",
        "type": "Home",
        "name": "<string>",
        "isDefault": "<boolean>",
        "personId": "<long>",
        "lastSuccessfulCallDate": "<dateTime>"
    }
}
```
</details>

---

#### **_Update a Phone Number_**

**POST** `/api/v3/Customer/UpdatePhone`

#### Description

Updates an existing phone number in the system.

##### Query Parameters

| Parameter       | Type | Description |
| :-------------- | :--- | :---------- |
| `no parameters` |      |             |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X POST "http://localhost:7080/api/v3/Customer/UpdatePhone" -H 'Accept: text/plain' -data '{
  "guid": "<uuid>",
  "isActive": "<boolean>",
  "updateUserId": "<long>",
  "phoneNumberText": "<string>",
  "type": "Fax",
  "name": "<string>",
  "isDefault": "<boolean>",
  "personId": "<long>",
  "lastSuccessfulCallDate": "<dateTime>"
}'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": {
        "id": "<long>",
        "guid": "<uuid>",
        "isActive": "<boolean>",
        "createDate": "<dateTime>",
        "createUserId": "<long>",
        "updateDate": "<dateTime>",
        "updateUserId": "<long>",
        "phoneNumberText": "<string>",
        "type": "Home",
        "name": "<string>",
        "isDefault": "<boolean>",
        "personId": "<long>",
        "lastSuccessfulCallDate": "<dateTime>"
    }
}
```
</details>

---

#### **_Update a Phone Number Only Last successfuldate_**

**POST** `/api/v3/Customer/SetPhoneLastSuccessfulDate`

#### Description

Updates an existing phone number in the system.

##### Query Parameters

| Parameter       | Type | Description |
| :-------------- | :--- | :---------- |
| `no parameters` |      |             |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X POST "http://localhost:7080/api/v3/Customer/SetPhoneLastSuccessfulDate" -H 'Accept: text/plain' -data '{
  "updateUserId": "<long>",
  "phoneNumberText": "<string>",
  "personId": "<long>"
}'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": {
        "id": "<long>",
        "guid": "<uuid>",
        "isActive": "<boolean>",
        "createDate": "<dateTime>",
        "createUserId": "<long>",
        "updateDate": "<dateTime>",
        "updateUserId": "<long>",
        "phoneNumberText": "<string>",
        "type": "Home",
        "name": "<string>",
        "isDefault": "<boolean>",
        "personId": "<long>",
        "lastSuccessfulCallDate": "<dateTime>"
    }
}
```
</details>

---

#### **_Deactivate a phone Number_**

**POST** `/api/v3/Customer/DeletePhone`

#### Description

Deactivates a phone number, effectively removing it from active use.

##### Query Parameters

| Parameter       | Type | Description |
| :-------------- | :--- | :---------- |
| `no parameters` |      |             |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X POST "http://localhost:7080/api/v3/Customer/DeletePhone" -H 'Accept: text/plain' -data '{
  "guid": "<uuid>",
  "updateUserId": "<long>"
}'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": {
        "nullable": true
    }
}
```
</details>

---

#### **_Create an Email_**

**POST** `/api/v3/Customer/CreateEmail`

#### Description

Registers a new email in the system.

##### Query Parameters

| Parameter       | Type | Description |
| :-------------- | :--- | :---------- |
| `no parameters` |      |             |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X POST "http://localhost:7080/api/v3/Customer/CreateEmail" -H 'Accept: text/plain' -data '{
  "eMailAddress": "<string>",
  "isDefault": "<boolean>",
  "personId": "<long>",
  "stagingImportId": "<long>"
}'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": {
        "id": "<long>",
        "guid": "<uuid>",
        "isActive": "<boolean>",
        "createDate": "<dateTime>",
        "createUserId": "<long>",
        "updateDate": "<dateTime>",
        "updateUserId": "<long>",
        "eMailAddress": "<string>",
        "isDefault": "<boolean>",
        "personId": "<long>"
    }
}
```
</details>

---

#### **_Update an Email_**

**POST** `/api/v3/Customer/UpdateEmail`

#### Description

Updates an existing email in the system.

##### Query Parameters

| Parameter       | Type | Description |
| :-------------- | :--- | :---------- |
| `no parameters` |      |             |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X POST "http://localhost:7080/api/v3/Customer/UpdateEmail" -H 'Accept: text/plain' -data '{
  "guid": "<uuid>",
  "isActive": "<boolean>",
  "updateUserId": "<long>",
  "eMailAddress": "<string>",
  "isDefault": "<boolean>",
  "personId": "<long>"
}'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": {
        "id": "<long>",
        "guid": "<uuid>",
        "isActive": "<boolean>",
        "createDate": "<dateTime>",
        "createUserId": "<long>",
        "updateDate": "<dateTime>",
        "updateUserId": "<long>",
        "eMailAddress": "<string>",
        "isDefault": "<boolean>",
        "personId": "<long>"
    }
}
```
</details>

---

#### **_Deactivate an Email_**

**POST** `/api/v3/Customer/DeleteEmail`

#### Description

Deactivates an Email, effectively removing it from active use.

##### Query Parameters

| Parameter       | Type | Description |
| :-------------- | :--- | :---------- |
| `no parameters` |      |             |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X POST "http://localhost:7080/api/v3/Customer/DeleteEmail" -H 'Accept: text/plain' -data '{
  "guid": "<uuid>",
  "updateUserId": "<long>"
}'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": {
        "nullable": true
    }
}
```
</details>

---

#### **_Create an Address_**

**POST** `/api/v3/Customer/CreateAddress`

#### Description

Creates a new address record in the system.

##### Query Parameters

| Parameter       | Type | Description |
| :-------------- | :--- | :---------- |
| `no parameters` |      |             |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X POST "http://localhost:7080/api/v3/Customer/CreateAddress" -H 'Accept: text/plain' -data '{
  "name": "<string>",
  "district": "<string>",
  "street": "<string>",
  "addressText": "<string>",
  "town": "<string>",
  "city": "<string>",
  "postalCode": "<string>",
  "country": "<string>",
  "isDefault": "<boolean>",
  "personId": "<long>",
  "stagingImportId": "<long>"
}'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": {
        "id": "<long>",
        "guid": "<uuid>",
        "isActive": "<boolean>",
        "createDate": "<dateTime>",
        "createUserId": "<long>",
        "updateDate": "<dateTime>",
        "updateUserId": "<long>",
        "name": "<string>",
        "district": "<string>",
        "street": "<string>",
        "addressText": "<string>",
        "town": "<string>",
        "city": "<string>",
        "postalCode": "<string>",
        "country": "<string>",
        "isDefault": "<boolean>",
        "personId": "<long>"
    }
}
```
</details>

---

#### **_Update an Address_**

**POST** `/api/v3/Customer/UpdateAddress`

#### Description

Updates an existing address record in the system.

##### Query Parameters

| Parameter       | Type | Description |
| :-------------- | :--- | :---------- |
| `no parameters` |      |             |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X POST "http://localhost:7080/api/v3/Customer/UpdateAddress" -H 'Accept: text/plain' -data '{
  "guid": "<uuid>",
  "isActive": "<boolean>",
  "updateUserId": "<long>",
  "name": "<string>",
  "district": "<string>",
  "street": "<string>",
  "town": "<string>",
  "city": "<string>",
  "postalCode": "<string>",
  "country": "<string>",
  "isDefault": "<boolean>",
  "personId": "<long>"
}'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": {
        "id": "<long>",
        "guid": "<uuid>",
        "isActive": "<boolean>",
        "createDate": "<dateTime>",
        "createUserId": "<long>",
        "updateDate": "<dateTime>",
        "updateUserId": "<long>",
        "name": "<string>",
        "district": "<string>",
        "street": "<string>",
        "addressText": "<string>",
        "town": "<string>",
        "city": "<string>",
        "postalCode": "<string>",
        "country": "<string>",
        "isDefault": "<boolean>",
        "personId": "<long>"
    }
}
```
</details>

---

#### **_Deactivates an Address_**

**POST** `/api/v3/Customer/DeleteAddress`

#### Description

Deactivates an address record in the system.

##### Query Parameters

| Parameter       | Type | Description |
| :-------------- | :--- | :---------- |
| `no parameters` |      |             |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X POST "http://localhost:7080/api/v3/Customer/DeleteAddress" -H 'Accept: text/plain' -data '{
  "guid": "<uuid>",
  "updateUserId": "<long>"
}'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": {
        "nullable": true
    }
}
```
</details>

---

#### **_Retrieve Bucket Changes by Person Guid_**

**GET** `/api/v3/Customer/GetBucketChangeByPersonGuid`

#### Description

Fetches all bucket changes associated with a given person's GUID. This is useful for retrieving contact details linked to a person record.

##### Query Parameters

| Parameter    | Type   | Description       |
| :----------- | :----- | :---------------- |
| `personGuid` | `guid` | (**_required_** ) |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/Customer/GetBucketChangeByPersonGuid?personGuid=%3Cuuid%3E" -H 'Accept: text/plain'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": [
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "loanAccountId": "<long>",
            "personId": "<long>",
            "type": "ADJUSTMENT",
            "pastDueAmount": "<double>",
            "fromBucket": "B2",
            "toBucket": "B4"
        },
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "loanAccountId": "<long>",
            "personId": "<long>",
            "type": "ADJUSTMENT",
            "pastDueAmount": "<double>",
            "fromBucket": "B3",
            "toBucket": "B0"
        }
    ]
}
```
</details>

---

#### **_Retrieve Bucket Changes by LoanAccount Guid_**

**GET** `/api/v3/Customer/GetBucketChangeByLoanAccountGuid`

#### Description

Fetches all bucket changes associated with a given LoanAccount's GUID. This is useful for retrieving contact details linked to a LoanAccount record.

##### Query Parameters

| Parameter         | Type   | Description       |
| :---------------- | :----- | :---------------- |
| `loanAccountGuid` | `guid` | (**_required_** ) |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080}/api/v3/Customer/GetBucketChangeByLoanAccountGuid?loanAccountGuid=%3Cuuid%3E" -H 'Accept: text/plain'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": [
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "loanAccountId": "<long>",
            "personId": "<long>",
            "type": "ADJUSTMENT",
            "pastDueAmount": "<double>",
            "fromBucket": "B2",
            "toBucket": "B4"
        },
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "loanAccountId": "<long>",
            "personId": "<long>",
            "type": "ADJUSTMENT",
            "pastDueAmount": "<double>",
            "fromBucket": "B3",
            "toBucket": "B0"
        }
    ]
}
```
</details>

---

#### **_Retrieve a Person by Person Guid_**

**GET** `/api/v3/Customer/GetCustomerByGuid`

#### Description

Fetches a detailed person using its GUID identifier.

##### Query Parameters

| Parameter        | Type     | Description       |
| :--------------- | :------- | :---------------- |
| `guid`           | `guid`   | (**_required_** ) |
| `identityNumber` | `string` |                   |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/Customer/GetCustomerByGuid?guid=%3Cuuid%3E" -H 'Accept: text/plain'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": {
        "id": "<long>",
        "guid": "<uuid>",
        "isActive": "<boolean>",
        "createDate": "<dateTime>",
        "createUserId": "<long>",
        "updateDate": "<dateTime>",
        "updateUserId": "<long>",
        "segment": "<string>",
        "customerId": "<long>",
        "customerNumber": "<long>",
        "relationCustNum": "<long>",
        "relationType": "RELATIVE",
        "identityNumber": "<string>",
        "name": "<string>",
        "middleName": "<string>",
        "surname": "<string>",
        "firmName": "<string>",
        "personnelFlag": "<boolean>",
        "vipFlag": "<boolean>",
        "birthDate": "<dateTime>",
        "birthPlace": "<string>",
        "workflowCode": "<string>",
        "gender": "Female",
        "dateOfDeath": "<dateTime>",
        "workIsMailing": "<boolean>",
        "nplFlag": "<boolean>",
        "nplDate": "<dateTime>",
        "lastKrsSearchDate": "<dateTime>",
        "currentKkbScore": "<integer>",
        "creditCardUsageRate": "<double>",
        "kmhUsageRate": "<double>",
        "collectionScore": "<string>",
        "lastMonthApplicationCount": "<integer>",
        "otherBankMortgageLoanPaymentPerformance": "<string>",
        "blockageFlag": "<boolean>",
        "blockageReason": "<string>",
        "tumKredilerDpdMaxMin6": "<integer>",
        "modelType": "<string>",
        "totalCashRisk": "<double>",
        "totalLimit": "<double>",
        "totalRisk": "<double>",
        "totalPursuable": "<double>",
        "minPursuable": "<double>",
        "totalAssets": "<double>",
        "totalColleteral": "<double>",
        "totalLimitUtilRatio": "<double>",
        "allMaxDpd": "<integer>",
        "engagementGuarantorInfo": "<string>",
        "spare01Key": "<string>",
        "spare01Value": "<string>",
        "spare02Key": "<string>",
        "spare02Value": "<string>",
        "spare03Key": "<string>",
        "spare03Value": "<string>",
        "spare04Key": "<string>",
        "spare04Value": "<string>",
        "spare05Key": "<string>",
        "spare05Value": "<string>",
        "spare06Key": "<string>",
        "spare06Value": "<string>",
        "spare07Key": "<string>",
        "spare07Value": "<string>",
        "spare08Key": "<string>",
        "spare08Value": "<string>",
        "spare09Key": "<string>",
        "spare09Value": "<string>",
        "spare10Key": "<string>",
        "spare10Value": "<string>",
        "promisePayments": [
            {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "activityId": "<long>",
                "loanAccountId": "<long>",
                "personId": "<long>",
                "relationType": "AGENT",
                "promiseDate": "<dateTime>",
                "promiseAmount": "<double>",
                "sequenceNumber": "<integer>",
                "note": "<string>",
                "isPaid": "<boolean>",
                "loanAccountPaymentId": "<long>",
                "giveName": "<string>",
                "accountNumber": "<string>",
                "activityCreateDate": "<dateTime>"
            },
            {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "activityId": "<long>",
                "loanAccountId": "<long>",
                "personId": "<long>",
                "relationType": "MOTHER",
                "promiseDate": "<dateTime>",
                "promiseAmount": "<double>",
                "sequenceNumber": "<integer>",
                "note": "<string>",
                "isPaid": "<boolean>",
                "loanAccountPaymentId": "<long>",
                "giveName": "<string>",
                "accountNumber": "<string>",
                "activityCreateDate": "<dateTime>"
            }
        ],
        "addresses": [
            {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "name": "<string>",
                "district": "<string>",
                "street": "<string>",
                "addressText": "<string>",
                "town": "<string>",
                "city": "<string>",
                "postalCode": "<string>",
                "country": "<string>",
                "isDefault": "<boolean>",
                "personId": "<long>"
            },
            {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "name": "<string>",
                "district": "<string>",
                "street": "<string>",
                "addressText": "<string>",
                "town": "<string>",
                "city": "<string>",
                "postalCode": "<string>",
                "country": "<string>",
                "isDefault": "<boolean>",
                "personId": "<long>"
            }
        ],
        "phoneNumbers": [
            {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "phoneNumberText": "<string>",
                "type": "Mobile",
                "name": "<string>",
                "isDefault": "<boolean>",
                "personId": "<long>",
                "lastSuccessfulCallDate": "<dateTime>"
            },
            {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "phoneNumberText": "<string>",
                "type": "Mobile",
                "name": "<string>",
                "isDefault": "<boolean>",
                "personId": "<long>",
                "lastSuccessfulCallDate": "<dateTime>"
            }
        ],
        "eMails": [
            {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "eMailAddress": "<string>",
                "isDefault": "<boolean>",
                "personId": "<long>"
            },
            {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "eMailAddress": "<string>",
                "isDefault": "<boolean>",
                "personId": "<long>"
            }
        ],
        "leadAccount": {
            "bucket": "B3",
            "leadAccountFlag": "<boolean>",
            "accountNumber": "<string>",
            "branchCode": "<integer>",
            "customerNumber": "<integer>",
            "personId": "<long>",
            "accountReference": "<string>",
            "usageDate": "<dateTime>",
            "accountSuffix": "<integer>",
            "type": "ZARAR_NITELIKLI_ALACAK",
            "productCode": "<string>",
            "currencyCode": "<string>",
            "currentAccountIbanNumber": "<string>",
            "accDpd": "<integer>",
            "bucket1DueAmount": "<double>",
            "bucket1RemainingAmount": "<double>",
            "bucket1DueDate": "<dateTime>",
            "bucket2DueAmount": "<double>",
            "bucket2RemainingAmount": "<double>",
            "bucket2DueDate": "<dateTime>",
            "bucket3DueAmount": "<double>",
            "bucket3RemainingAmount": "<double>",
            "bucket3DueDate": "<dateTime>",
            "rollbackFlag": "<string>",
            "restructuredFlag": "<string>",
            "lastPaymentAmount": "<double>",
            "lastPaymentDate": "<dateTime>",
            "muacceliyetDate": "<dateTime>",
            "coreLastUpdateDate": "<dateTime>",
            "totalRemainingAmount": "<double>",
            "stagingImportId": "<long>",
            "bucketChange": {
                "createDate": "<dateTime>",
                "type": "ADJUSTMENT",
                "pastDueAmount": "<double>",
                "fromBucket": "B0",
                "toBucket": "B2"
            },
            "spare01Key": "<string>",
            "spare01Value": "<string>",
            "spare02Key": "<string>",
            "spare02Value": "<string>",
            "spare03Key": "<string>",
            "spare03Value": "<string>",
            "spare04Key": "<string>",
            "spare04Value": "<string>",
            "spare05Key": "<string>"
        },
        "loanAccounts": [
            {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "isExistPromisePayment": "<boolean>",
                "bucket": "B1",
                "leadAccountFlag": "<boolean>",
                "accountNumber": "<string>",
                "branchCode": "<integer>",
                "customerNumber": "<integer>",
                "personId": "<long>",
                "accountReference": "<string>",
                "usageDate": "<dateTime>",
                "accountSuffix": "<integer>",
                "type": "KONUT_KREDISI",
                "productCode": "<string>",
                "currencyCode": "<string>",
                "currentAccountIbanNumber": "<string>",
                "accDpd": "<integer>",
                "bucket1DueAmount": "<double>",
                "bucket1RemainingAmount": "<double>",
                "bucket1DueDate": "<dateTime>",
                "bucket2DueAmount": "<double>",
                "bucket2RemainingAmount": "<double>",
                "bucket2DueDate": "<dateTime>",
                "bucket3DueAmount": "<double>",
                "bucket3RemainingAmount": "<double>",
                "bucket3DueDate": "<dateTime>",
                "rollbackFlag": "<string>",
                "restructuredFlag": "<string>",
                "lastPaymentAmount": "<double>",
                "lastPaymentDate": "<dateTime>",
                "muacceliyetDate": "<dateTime>",
                "coreLastUpdateDate": "<dateTime>",
                "loanAccountCautions": [
                    {
                        "id": "<long>",
                        "guid": "<uuid>",
                        "isActive": "<boolean>",
                        "createDate": "<dateTime>",
                        "createUserId": "<long>",
                        "updateDate": "<dateTime>",
                        "updateUserId": "<long>",
                        "accountBranchCode": "<integer>",
                        "accountNumber": "<integer>",
                        "cautionAccountSuffix": "<integer>",
                        "cautionKind": "<string>",
                        "cautionDescription": "<string>",
                        "currencyCode": "<string>",
                        "balance": "<double>",
                        "balanceTl": "<double>",
                        "cautionType": "<string>",
                        "cautionsRef": "<integer>",
                        "engagementGuarantorInfo": "<long>",
                        "engagementGuarantorNames": {
                            "guid": "<uuid>",
                            "name": "<string>",
                            "middleName": "<string>",
                            "surname": "<string>",
                            "firmName": "<string>"
                        },
                        "coreLastUpdateDate": "<dateTime>",
                        "loanAccountId": "<long>",
                        "personId": "<long>"
                    },
                    {
                        "id": "<long>",
                        "guid": "<uuid>",
                        "isActive": "<boolean>",
                        "createDate": "<dateTime>",
                        "createUserId": "<long>",
                        "updateDate": "<dateTime>",
                        "updateUserId": "<long>",
                        "accountBranchCode": "<integer>",
                        "accountNumber": "<integer>",
                        "cautionAccountSuffix": "<integer>",
                        "cautionKind": "<string>",
                        "cautionDescription": "<string>",
                        "currencyCode": "<string>",
                        "balance": "<double>",
                        "balanceTl": "<double>",
                        "cautionType": "<string>",
                        "cautionsRef": "<integer>",
                        "engagementGuarantorInfo": "<long>",
                        "engagementGuarantorNames": {
                            "guid": "<uuid>",
                            "name": "<string>",
                            "middleName": "<string>",
                            "surname": "<string>",
                            "firmName": "<string>"
                        },
                        "coreLastUpdateDate": "<dateTime>",
                        "loanAccountId": "<long>",
                        "personId": "<long>"
                    }
                ],
                "bucketChange": {
                    "createDate": "<dateTime>",
                    "type": "NOPAYMENT",
                    "pastDueAmount": "<double>",
                    "fromBucket": "B1",
                    "toBucket": "B2"
                },
                "maturityDate": "<dateTime>",
                "balance": "<double>",
                "balanceTl": "<double>",
                "pursuable": "<double>",
                "pursuableTl": "<double>",
                "accountLimit": "<double>",
                "accountLimitTl": "<double>",
                "principalAmount": "<double>",
                "dueDate": "<dateTime>",
                "installmentNumber": "<integer>",
                "remainingInstallmentNumber": "<integer>",
                "maxDpd": "<integer>",
                "nextDueDate": "<dateTime>",
                "restructuredCount": "<integer>",
                "cautionAmount": "<double>",
                "delayRate": "<double>",
                "channelDetail": "<string>",
                "dealerName": "<string>",
                "dealerProductName": "<string>",
                "cautionName": "<string>",
                "firstPaymentFlag": "<string>",
                "insuranceFlag": "<string>",
                "insuranceName": "<string>",
                "campaignName": "<string>",
                "nplSuffix": "<integer>",
                "nplDate": "<dateTime>",
                "yySuffix": "<integer>",
                "yyDate": "<dateTime>",
                "spare01Key": "<string>",
                "spare01Value": "<string>",
                "spare02Key": "<string>",
                "spare02Value": "<string>",
                "spare03Key": "<string>",
                "spare03Value": "<string>",
                "spare04Key": "<string>",
                "spare04Value": "<string>",
                "spare05Key": "<string>"
            },
            {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "isExistPromisePayment": "<boolean>",
                "bucket": "B4",
                "leadAccountFlag": "<boolean>",
                "accountNumber": "<string>",
                "branchCode": "<integer>",
                "customerNumber": "<integer>",
                "personId": "<long>",
                "accountReference": "<string>",
                "usageDate": "<dateTime>",
                "accountSuffix": "<integer>",
                "type": "Y_YAPILANRIMA_TASIT",
                "productCode": "<string>",
                "currencyCode": "<string>",
                "currentAccountIbanNumber": "<string>",
                "accDpd": "<integer>",
                "bucket1DueAmount": "<double>",
                "bucket1RemainingAmount": "<double>",
                "bucket1DueDate": "<dateTime>",
                "bucket2DueAmount": "<double>",
                "bucket2RemainingAmount": "<double>",
                "bucket2DueDate": "<dateTime>",
                "bucket3DueAmount": "<double>",
                "bucket3RemainingAmount": "<double>",
                "bucket3DueDate": "<dateTime>",
                "rollbackFlag": "<string>",
                "restructuredFlag": "<string>",
                "lastPaymentAmount": "<double>",
                "lastPaymentDate": "<dateTime>",
                "muacceliyetDate": "<dateTime>",
                "coreLastUpdateDate": "<dateTime>",
                "loanAccountCautions": [
                    {
                        "id": "<long>",
                        "guid": "<uuid>",
                        "isActive": "<boolean>",
                        "createDate": "<dateTime>",
                        "createUserId": "<long>",
                        "updateDate": "<dateTime>",
                        "updateUserId": "<long>",
                        "accountBranchCode": "<integer>",
                        "accountNumber": "<integer>",
                        "cautionAccountSuffix": "<integer>",
                        "cautionKind": "<string>",
                        "cautionDescription": "<string>",
                        "currencyCode": "<string>",
                        "balance": "<double>",
                        "balanceTl": "<double>",
                        "cautionType": "<string>",
                        "cautionsRef": "<integer>",
                        "engagementGuarantorInfo": "<long>",
                        "engagementGuarantorNames": {
                            "guid": "<uuid>",
                            "name": "<string>",
                            "middleName": "<string>",
                            "surname": "<string>",
                            "firmName": "<string>"
                        },
                        "coreLastUpdateDate": "<dateTime>",
                        "loanAccountId": "<long>",
                        "personId": "<long>"
                    },
                    {
                        "id": "<long>",
                        "guid": "<uuid>",
                        "isActive": "<boolean>",
                        "createDate": "<dateTime>",
                        "createUserId": "<long>",
                        "updateDate": "<dateTime>",
                        "updateUserId": "<long>",
                        "accountBranchCode": "<integer>",
                        "accountNumber": "<integer>",
                        "cautionAccountSuffix": "<integer>",
                        "cautionKind": "<string>",
                        "cautionDescription": "<string>",
                        "currencyCode": "<string>",
                        "balance": "<double>",
                        "balanceTl": "<double>",
                        "cautionType": "<string>",
                        "cautionsRef": "<integer>",
                        "engagementGuarantorInfo": "<long>",
                        "engagementGuarantorNames": {
                            "guid": "<uuid>",
                            "name": "<string>",
                            "middleName": "<string>",
                            "surname": "<string>",
                            "firmName": "<string>"
                        },
                        "coreLastUpdateDate": "<dateTime>",
                        "loanAccountId": "<long>",
                        "personId": "<long>"
                    }
                ],
                "bucketChange": {
                    "createDate": "<dateTime>",
                    "type": "ADJUSTMENT",
                    "pastDueAmount": "<double>",
                    "fromBucket": "B4",
                    "toBucket": "B0"
                },
                "maturityDate": "<dateTime>",
                "balance": "<double>",
                "balanceTl": "<double>",
                "pursuable": "<double>",
                "pursuableTl": "<double>",
                "accountLimit": "<double>",
                "accountLimitTl": "<double>",
                "principalAmount": "<double>",
                "dueDate": "<dateTime>",
                "installmentNumber": "<integer>",
                "remainingInstallmentNumber": "<integer>",
                "maxDpd": "<integer>",
                "nextDueDate": "<dateTime>",
                "restructuredCount": "<integer>",
                "cautionAmount": "<double>",
                "delayRate": "<double>",
                "channelDetail": "<string>",
                "dealerName": "<string>",
                "dealerProductName": "<string>",
                "cautionName": "<string>",
                "firstPaymentFlag": "<string>",
                "insuranceFlag": "<string>",
                "insuranceName": "<string>",
                "campaignName": "<string>",
                "nplSuffix": "<integer>",
                "nplDate": "<dateTime>",
                "yySuffix": "<integer>",
                "yyDate": "<dateTime>",
                "spare01Key": "<string>",
                "spare01Value": "<string>",
                "spare02Key": "<string>",
                "spare02Value": "<string>",
                "spare03Key": "<string>",
                "spare03Value": "<string>",
                "spare04Key": "<string>",
                "spare04Value": "<string>",
                "spare05Key": "<string>"
            }
        ],
        "cardAccounts": [
            {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "isExistPromisePayment": "<boolean>",
                "bucket": "B3",
                "leadAccountFlag": "<boolean>",
                "accountNumber": "<string>",
                "branchCode": "<integer>",
                "customerNumber": "<long>",
                "personId": "<long>",
                "accountReference": "<string>",
                "usageDate": "<dateTime>",
                "accountSuffix": "<integer>",
                "type": "OTHER",
                "productCode": "<string>",
                "currencyCode": "<string>",
                "currentAccountIbanNumber": "<string>",
                "accDpd": "<integer>",
                "bucket1DueAmount": "<double>",
                "bucket1RemainingAmount": "<double>",
                "bucket1DueDate": "<dateTime>",
                "bucket2DueAmount": "<double>",
                "bucket2RemainingAmount": "<double>",
                "bucket2DueDate": "<dateTime>",
                "bucket3DueAmount": "<double>",
                "bucket3RemainingAmount": "<double>",
                "bucket3DueDate": "<dateTime>",
                "rollbackFlag": "<string>",
                "restructuredFlag": "<string>",
                "lastPaymentAmount": "<double>",
                "lastPaymentDate": "<dateTime>",
                "muacceliyetDate": "<dateTime>",
                "coreLastUpdateDate": "<dateTime>",
                "loanAccountCautions": [
                    {
                        "id": "<long>",
                        "guid": "<uuid>",
                        "isActive": "<boolean>",
                        "createDate": "<dateTime>",
                        "createUserId": "<long>",
                        "updateDate": "<dateTime>",
                        "updateUserId": "<long>",
                        "accountBranchCode": "<integer>",
                        "accountNumber": "<integer>",
                        "cautionAccountSuffix": "<integer>",
                        "cautionKind": "<string>",
                        "cautionDescription": "<string>",
                        "currencyCode": "<string>",
                        "balance": "<double>",
                        "balanceTl": "<double>",
                        "cautionType": "<string>",
                        "cautionsRef": "<integer>",
                        "engagementGuarantorInfo": "<long>",
                        "engagementGuarantorNames": {
                            "guid": "<uuid>",
                            "name": "<string>",
                            "middleName": "<string>",
                            "surname": "<string>",
                            "firmName": "<string>"
                        },
                        "coreLastUpdateDate": "<dateTime>",
                        "loanAccountId": "<long>",
                        "personId": "<long>"
                    },
                    {
                        "id": "<long>",
                        "guid": "<uuid>",
                        "isActive": "<boolean>",
                        "createDate": "<dateTime>",
                        "createUserId": "<long>",
                        "updateDate": "<dateTime>",
                        "updateUserId": "<long>",
                        "accountBranchCode": "<integer>",
                        "accountNumber": "<integer>",
                        "cautionAccountSuffix": "<integer>",
                        "cautionKind": "<string>",
                        "cautionDescription": "<string>",
                        "currencyCode": "<string>",
                        "balance": "<double>",
                        "balanceTl": "<double>",
                        "cautionType": "<string>",
                        "cautionsRef": "<integer>",
                        "engagementGuarantorInfo": "<long>",
                        "engagementGuarantorNames": {
                            "guid": "<uuid>",
                            "name": "<string>",
                            "middleName": "<string>",
                            "surname": "<string>",
                            "firmName": "<string>"
                        },
                        "coreLastUpdateDate": "<dateTime>",
                        "loanAccountId": "<long>",
                        "personId": "<long>"
                    }
                ],
                "bucketChange": {
                    "createDate": "<dateTime>",
                    "type": "NOPAYMENT",
                    "pastDueAmount": "<double>",
                    "fromBucket": "B3",
                    "toBucket": "B1"
                },
                "cardStatus": "<string>",
                "cardNumber": "<string>",
                "statementDate": "<dateTime>",
                "statementDueDate": "<dateTime>",
                "statementAmount": "<double>",
                "statementMinimumPayableAmount": "<double>",
                "cardTotalDebitAmount": "<double>",
                "cardLimit": "<double>",
                "cardAvailableLimit": "<double>",
                "cardCashLimit": "<double>",
                "cardCloseAmount": "<double>",
                "cardAutoPaymentOrderFlag": "<string>",
                "additionalCardExistFlag": "<string>",
                "cardDeliveryAddress": "<string>",
                "cardDelayStatus": "<string>",
                "delayBeginDate": "<dateTime>",
                "legalMinimumPaymentAnnual": "<integer>",
                "legalMinimumPaymentFreq": "<integer>",
                "interestRate": "<double>",
                "delayInterestRate": "<double>",
                "cashInterestRate": "<double>",
                "customerSegmentInfo": "<string>",
                "lastStatementAmount": "<double>",
                "lastStatementRemainingAmount": "<double>",
                "statementCardAmount": "<double>",
                "statementCardRemainingAmount": "<double>",
                "spare01Key": "<string>",
                "spare01Value": "<string>",
                "spare02Key": "<string>",
                "spare02Value": "<string>",
                "spare03Key": "<string>",
                "spare03Value": "<string>",
                "spare04Key": "<string>",
                "spare04Value": "<string>",
                "spare05Key": "<string>"
            },
            {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "isExistPromisePayment": "<boolean>",
                "bucket": "B0",
                "leadAccountFlag": "<boolean>",
                "accountNumber": "<string>",
                "branchCode": "<integer>",
                "customerNumber": "<long>",
                "personId": "<long>",
                "accountReference": "<string>",
                "usageDate": "<dateTime>",
                "accountSuffix": "<integer>",
                "type": "TASIT_KREDISI",
                "productCode": "<string>",
                "currencyCode": "<string>",
                "currentAccountIbanNumber": "<string>",
                "accDpd": "<integer>",
                "bucket1DueAmount": "<double>",
                "bucket1RemainingAmount": "<double>",
                "bucket1DueDate": "<dateTime>",
                "bucket2DueAmount": "<double>",
                "bucket2RemainingAmount": "<double>",
                "bucket2DueDate": "<dateTime>",
                "bucket3DueAmount": "<double>",
                "bucket3RemainingAmount": "<double>",
                "bucket3DueDate": "<dateTime>",
                "rollbackFlag": "<string>",
                "restructuredFlag": "<string>",
                "lastPaymentAmount": "<double>",
                "lastPaymentDate": "<dateTime>",
                "muacceliyetDate": "<dateTime>",
                "coreLastUpdateDate": "<dateTime>",
                "loanAccountCautions": [
                    {
                        "id": "<long>",
                        "guid": "<uuid>",
                        "isActive": "<boolean>",
                        "createDate": "<dateTime>",
                        "createUserId": "<long>",
                        "updateDate": "<dateTime>",
                        "updateUserId": "<long>",
                        "accountBranchCode": "<integer>",
                        "accountNumber": "<integer>",
                        "cautionAccountSuffix": "<integer>",
                        "cautionKind": "<string>",
                        "cautionDescription": "<string>",
                        "currencyCode": "<string>",
                        "balance": "<double>",
                        "balanceTl": "<double>",
                        "cautionType": "<string>",
                        "cautionsRef": "<integer>",
                        "engagementGuarantorInfo": "<long>",
                        "engagementGuarantorNames": {
                            "guid": "<uuid>",
                            "name": "<string>",
                            "middleName": "<string>",
                            "surname": "<string>",
                            "firmName": "<string>"
                        },
                        "coreLastUpdateDate": "<dateTime>",
                        "loanAccountId": "<long>",
                        "personId": "<long>"
                    },
                    {
                        "id": "<long>",
                        "guid": "<uuid>",
                        "isActive": "<boolean>",
                        "createDate": "<dateTime>",
                        "createUserId": "<long>",
                        "updateDate": "<dateTime>",
                        "updateUserId": "<long>",
                        "accountBranchCode": "<integer>",
                        "accountNumber": "<integer>",
                        "cautionAccountSuffix": "<integer>",
                        "cautionKind": "<string>",
                        "cautionDescription": "<string>",
                        "currencyCode": "<string>",
                        "balance": "<double>",
                        "balanceTl": "<double>",
                        "cautionType": "<string>",
                        "cautionsRef": "<integer>",
                        "engagementGuarantorInfo": "<long>",
                        "engagementGuarantorNames": {
                            "guid": "<uuid>",
                            "name": "<string>",
                            "middleName": "<string>",
                            "surname": "<string>",
                            "firmName": "<string>"
                        },
                        "coreLastUpdateDate": "<dateTime>",
                        "loanAccountId": "<long>",
                        "personId": "<long>"
                    }
                ],
                "bucketChange": {
                    "createDate": "<dateTime>",
                    "type": "PAYMENT",
                    "pastDueAmount": "<double>",
                    "fromBucket": "B0",
                    "toBucket": "B3"
                },
                "cardStatus": "<string>",
                "cardNumber": "<string>",
                "statementDate": "<dateTime>",
                "statementDueDate": "<dateTime>",
                "statementAmount": "<double>",
                "statementMinimumPayableAmount": "<double>",
                "cardTotalDebitAmount": "<double>",
                "cardLimit": "<double>",
                "cardAvailableLimit": "<double>",
                "cardCashLimit": "<double>",
                "cardCloseAmount": "<double>",
                "cardAutoPaymentOrderFlag": "<string>",
                "additionalCardExistFlag": "<string>",
                "cardDeliveryAddress": "<string>",
                "cardDelayStatus": "<string>",
                "delayBeginDate": "<dateTime>",
                "legalMinimumPaymentAnnual": "<integer>",
                "legalMinimumPaymentFreq": "<integer>",
                "interestRate": "<double>",
                "delayInterestRate": "<double>",
                "cashInterestRate": "<double>",
                "customerSegmentInfo": "<string>",
                "lastStatementAmount": "<double>",
                "lastStatementRemainingAmount": "<double>",
                "statementCardAmount": "<double>",
                "statementCardRemainingAmount": "<double>",
                "spare01Key": "<string>",
                "spare01Value": "<string>",
                "spare02Key": "<string>",
                "spare02Value": "<string>",
                "spare03Key": "<string>",
                "spare03Value": "<string>",
                "spare04Key": "<string>",
                "spare04Value": "<string>",
                "spare05Key": "<string>"
            }
        ]
    }
}
```
</details>

---

#### **_Retrieve a general property of Person_**

**GET** `/api/v3/Customer/GetCustomerInfoByGuid`

#### Description

Fetches a detailed person using its GUID identifier.

##### Query Parameters

| Parameter        | Type     | Description       |
| :--------------- | :------- | :---------------- |
| `guid`           | `guid`   | (**_required_** ) |
| `identityNumber` | `string` |                   |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/Customer/GetCustomerInfoByGuid?guid=%3Cuuid%3E" -H 'Accept: text/plain'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": {
        "id": "<long>",
        "guid": "<uuid>",
        "isActive": "<boolean>",
        "createDate": "<dateTime>",
        "createUserId": "<long>",
        "updateDate": "<dateTime>",
        "updateUserId": "<long>",
        "segment": "<string>",
        "customerId": "<long>",
        "customerNumber": "<long>",
        "relationCustNum": "<long>",
        "relationType": "FATHER",
        "identityNumber": "<string>",
        "name": "<string>",
        "middleName": "<string>",
        "surname": "<string>",
        "firmName": "<string>",
        "birthDate": "<dateTime>",
        "birthPlace": "<string>",
        "gender": "Female",
        "dateOfDeath": "<dateTime>",
        "nplFlag": "<boolean>",
        "nplDate": "<dateTime>",
        "blockageFlag": "<boolean>",
        "allMaxDpd": "<integer>",
        "leadAccount": {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "bucket": "B1",
            "leadAccountFlag": "<boolean>",
            "accountNumber": "<string>",
            "branchCode": "<integer>",
            "customerNumber": "<integer>",
            "personId": "<long>",
            "accountReference": "<string>",
            "usageDate": "<dateTime>",
            "accountSuffix": "<integer>",
            "type": "MUHTELIF_ALACAK",
            "productCode": "<string>",
            "currencyCode": "<string>",
            "currentAccountIbanNumber": "<string>",
            "accDpd": "<integer>",
            "bucket1DueAmount": "<double>",
            "bucket1RemainingAmount": "<double>",
            "bucket1DueDate": "<dateTime>",
            "bucket2DueAmount": "<double>",
            "bucket2RemainingAmount": "<double>",
            "bucket2DueDate": "<dateTime>",
            "bucket3DueAmount": "<double>",
            "bucket3RemainingAmount": "<double>",
            "bucket3DueDate": "<dateTime>",
            "rollbackFlag": "<string>",
            "restructuredFlag": "<string>",
            "lastPaymentAmount": "<double>",
            "lastPaymentDate": "<dateTime>",
            "muacceliyetDate": "<dateTime>",
            "coreLastUpdateDate": "<dateTime>",
            "totalRemainingAmount": "<double>",
            "stagingImportId": "<long>"
        }
    }
}
```
</details>

---

#### **_Retrieve Person by Search_**

**GET** `/api/v3/Customer/CustomerSearch`

#### Description

Fetches person models associated with a specific search. Search term take Customer Number, Identity Number, Phone Numbers, Name, MiddleName, Surname or Company Name.

##### Query Parameters

| Parameter     | Type      | Description |
| :------------ | :-------- | :---------- |
| `search`      | `string`  |             |
| `segment `    | `string`  |             |
| `offset`      | `integer` |             |
| `limit`       | `integer` |             |
| `sortBy`      | `string`  |             |
| `sortOrder`   | `string`  |             |
| `personFlag`  | `string`  |             |
| `bucketEnum ` | `string`  |             |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/Customer/CustomerSearch?search=%3Cstring%3E&segment=%3Cstring%3E&Offset=%3Cinteger%3E&Limit=%3Cinteger%3E&sortBy=%3Cstring%3E&sortOrder=asc&personFlag=Npl&bucketEnum=B2" -H 'Accept: text/plain'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": [
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "segment": "<string>",
            "customerId": "<long>",
            "customerNumber": "<long>",
            "relationCustNum": "<long>",
            "relationType": "FATHER",
            "identityNumber": "<string>",
            "name": "<string>",
            "middleName": "<string>",
            "surname": "<string>",
            "firmName": "<string>",
            "personnelFlag": "<boolean>",
            "vipFlag": "<boolean>",
            "birthDate": "<dateTime>",
            "birthPlace": "<string>",
            "workflowCode": "<string>",
            "gender": "Male",
            "dateOfDeath": "<dateTime>",
            "coreLastUpdateDate": "<dateTime>",
            "workIsMailing": "<boolean>",
            "nplFlag": "<boolean>",
            "selfCuredFlag": "<boolean>",
            "nplDate": "<dateTime>",
            "lastKrsSearchDate": "<dateTime>",
            "currentKkbScore": "<integer>",
            "creditCardUsageRate": "<double>",
            "kmhUsageRate": "<double>",
            "collectionScore": "<string>",
            "lastMonthApplicationCount": "<integer>",
            "otherBankMortgageLoanPaymentPerformance": "<string>",
            "blockageFlag": "<boolean>",
            "hepsiDpdMaxLm": "<integer>",
            "sumNumFailL3m": "<integer>",
            "tumKredilerDpdMaxMin6": "<integer>",
            "avgAsinitsBurganOverOutsV12lm": "<string>",
            "hepsiDpdMaxL12m": "<integer>",
            "hepsiDpdLm": "<integer>",
            "hepsiDpdMaxV3lm": "<string>",
            "hepsiTotalOutsV3lm": "<string>",
            "hepsiDpdAmtOutsVlm": "<string>",
            "hepsiDpdAmtOutsMax12": "<double>",
            "modelType": "<string>",
            "finalRatio": "<double>",
            "totalCashRisk": "<double>",
            "totalLimit": "<double>",
            "totalRisk": "<double>",
            "totalPursuable": "<double>",
            "minPursuable": "<double>",
            "totalAssets": "<double>",
            "totalColleteral": "<double>",
            "totalLimitUtilRatio": "<double>",
            "allMaxDpd": "<integer>",
            "engagementGuarantorInfo": "<string>",
            "phoneNumbers": [
                {
                    "id": "<long>",
                    "guid": "<uuid>",
                    "isActive": "<boolean>",
                    "createDate": "<dateTime>",
                    "createUserId": "<long>",
                    "updateDate": "<dateTime>",
                    "updateUserId": "<long>",
                    "phoneNumberText": "<string>",
                    "type": "Fax",
                    "name": "<string>",
                    "isDefault": "<boolean>",
                    "personId": "<long>",
                    "lastSuccessfulCallDate": "<dateTime>"
                },
                {
                    "id": "<long>",
                    "guid": "<uuid>",
                    "isActive": "<boolean>",
                    "createDate": "<dateTime>",
                    "createUserId": "<long>",
                    "updateDate": "<dateTime>",
                    "updateUserId": "<long>",
                    "phoneNumberText": "<string>",
                    "type": "MobileSms",
                    "name": "<string>",
                    "isDefault": "<boolean>",
                    "personId": "<long>",
                    "lastSuccessfulCallDate": "<dateTime>"
                }
            ]
        },
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "segment": "<string>",
            "customerId": "<long>",
            "customerNumber": "<long>",
            "relationCustNum": "<long>",
            "relationType": "OWNER",
            "identityNumber": "<string>",
            "name": "<string>",
            "middleName": "<string>",
            "surname": "<string>",
            "firmName": "<string>",
            "personnelFlag": "<boolean>",
            "vipFlag": "<boolean>",
            "birthDate": "<dateTime>",
            "birthPlace": "<string>",
            "workflowCode": "<string>",
            "gender": "Female",
            "dateOfDeath": "<dateTime>",
            "coreLastUpdateDate": "<dateTime>",
            "workIsMailing": "<boolean>",
            "nplFlag": "<boolean>",
            "selfCuredFlag": "<boolean>",
            "nplDate": "<dateTime>",
            "lastKrsSearchDate": "<dateTime>",
            "currentKkbScore": "<integer>",
            "creditCardUsageRate": "<double>",
            "kmhUsageRate": "<double>",
            "collectionScore": "<string>",
            "lastMonthApplicationCount": "<integer>",
            "otherBankMortgageLoanPaymentPerformance": "<string>",
            "blockageFlag": "<boolean>",
            "hepsiDpdMaxLm": "<integer>",
            "sumNumFailL3m": "<integer>",
            "tumKredilerDpdMaxMin6": "<integer>",
            "avgAsinitsBurganOverOutsV12lm": "<string>",
            "hepsiDpdMaxL12m": "<integer>",
            "hepsiDpdLm": "<integer>",
            "hepsiDpdMaxV3lm": "<string>",
            "hepsiTotalOutsV3lm": "<string>",
            "hepsiDpdAmtOutsVlm": "<string>",
            "hepsiDpdAmtOutsMax12": "<double>",
            "modelType": "<string>",
            "finalRatio": "<double>",
            "totalCashRisk": "<double>",
            "totalLimit": "<double>",
            "totalRisk": "<double>",
            "totalPursuable": "<double>",
            "minPursuable": "<double>",
            "totalAssets": "<double>",
            "totalColleteral": "<double>",
            "totalLimitUtilRatio": "<double>",
            "allMaxDpd": "<integer>",
            "engagementGuarantorInfo": "<string>",
            "phoneNumbers": [
                {
                    "id": "<long>",
                    "guid": "<uuid>",
                    "isActive": "<boolean>",
                    "createDate": "<dateTime>",
                    "createUserId": "<long>",
                    "updateDate": "<dateTime>",
                    "updateUserId": "<long>",
                    "phoneNumberText": "<string>",
                    "type": "MobileSms",
                    "name": "<string>",
                    "isDefault": "<boolean>",
                    "personId": "<long>",
                    "lastSuccessfulCallDate": "<dateTime>"
                },
                {
                    "id": "<long>",
                    "guid": "<uuid>",
                    "isActive": "<boolean>",
                    "createDate": "<dateTime>",
                    "createUserId": "<long>",
                    "updateDate": "<dateTime>",
                    "updateUserId": "<long>",
                    "phoneNumberText": "<string>",
                    "type": "Other",
                    "name": "<string>",
                    "isDefault": "<boolean>",
                    "personId": "<long>",
                    "lastSuccessfulCallDate": "<dateTime>"
                }
            ]
        }
    ],
    "totalRowCount": "<integer>",
    "totalPageCount": "<integer>",
    "offset": "<integer>",
    "limit": "<integer>"
}
```
</details>

---

#### **_Retrieve Relational Person List by Relational CustomerNumber_**

**GET** `/api/v3/Customer/GetRelationPersonByCustomerNumber`

#### Description

Fetches relatonal person associated with a specific customer number.

##### Query Parameters

| Parameter        | Type      | Description       |
| :--------------- | :-------- | :---------------- |
| `customerNumber` | `integer` | (**_required_** ) |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/Customer/GetRelationPersonByCustomerNumber?customerNumber=%3Clong%3E" -H 'Accept: text/plain'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": [
        {
            "segment": "<string>",
            "relationType": "CHILD",
            "identityNumber": "<string>",
            "name": "<string>",
            "middleName": "<string>",
            "surname": "<string>",
            "firmName": "<string>",
            "guid": "<uuid>",
            "phoneNumbers": [
                {
                    "id": "<long>",
                    "guid": "<uuid>",
                    "isActive": "<boolean>",
                    "createDate": "<dateTime>",
                    "createUserId": "<long>",
                    "updateDate": "<dateTime>",
                    "updateUserId": "<long>",
                    "phoneNumberText": "<string>",
                    "type": "MobileSms",
                    "name": "<string>",
                    "isDefault": "<boolean>",
                    "personId": "<long>",
                    "lastSuccessfulCallDate": "<dateTime>"
                },
                {
                    "id": "<long>",
                    "guid": "<uuid>",
                    "isActive": "<boolean>",
                    "createDate": "<dateTime>",
                    "createUserId": "<long>",
                    "updateDate": "<dateTime>",
                    "updateUserId": "<long>",
                    "phoneNumberText": "<string>",
                    "type": "Home",
                    "name": "<string>",
                    "isDefault": "<boolean>",
                    "personId": "<long>",
                    "lastSuccessfulCallDate": "<dateTime>"
                }
            ]
        },
        {
            "segment": "<string>",
            "relationType": "AGENT",
            "identityNumber": "<string>",
            "name": "<string>",
            "middleName": "<string>",
            "surname": "<string>",
            "firmName": "<string>",
            "guid": "<uuid>",
            "phoneNumbers": [
                {
                    "id": "<long>",
                    "guid": "<uuid>",
                    "isActive": "<boolean>",
                    "createDate": "<dateTime>",
                    "createUserId": "<long>",
                    "updateDate": "<dateTime>",
                    "updateUserId": "<long>",
                    "phoneNumberText": "<string>",
                    "type": "Work",
                    "name": "<string>",
                    "isDefault": "<boolean>",
                    "personId": "<long>",
                    "lastSuccessfulCallDate": "<dateTime>"
                },
                {
                    "id": "<long>",
                    "guid": "<uuid>",
                    "isActive": "<boolean>",
                    "createDate": "<dateTime>",
                    "createUserId": "<long>",
                    "updateDate": "<dateTime>",
                    "updateUserId": "<long>",
                    "phoneNumberText": "<string>",
                    "type": "Other",
                    "name": "<string>",
                    "isDefault": "<boolean>",
                    "personId": "<long>",
                    "lastSuccessfulCallDate": "<dateTime>"
                }
            ]
        }
    ]
}
```
</details>

---

## PromisePayment

#### **_Retrieve a PromisePayment by Guid_**

**GET** `/api/v3/PromisePayment/GetByGuid`

#### Description

Returns a specific PromisePayment identified by GUID, including related details.

##### Query Parameters

| Parameter | Type   | Description       |
| :-------- | :----- | :---------------- |
| `guid`    | `guid` | (**_required_** ) |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/PromisePayment/GetByGuid?guid=%3Cuuid%3E" -H 'Accept: text/plain'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": {
        "id": "<long>",
        "guid": "<uuid>",
        "isActive": "<boolean>",
        "createDate": "<dateTime>",
        "createUserId": "<long>",
        "updateDate": "<dateTime>",
        "updateUserId": "<long>",
        "activity": {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "userId": "<long>",
            "type": "ACT_MOVE",
            "workActionId": "<long>",
            "note": "<string>",
            "pinned": "<boolean>",
            "status": "PROCESSING",
            "uuid": "<string>",
            "resultId": "<long>",
            "result": {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "result": "<string>",
                "subResult": "<boolean>",
                "nextAction": "LOOK_AT_SUB",
                "type": "PROMISEPAYMENT",
                "nextActionDelay": "<integer>",
                "nextActionMaxTry": "<integer>"
            },
            "subResultId": "<long>",
            "subResult": {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "activityResultId": "<long>",
                "subResult": "<string>",
                "nextAction": "WAIT_RETRY",
                "nextActionDelay": "<integer>",
                "nextActionMaxTry": "<integer>"
            },
            "scheduleDate": "<dateTime>"
        },
        "activityId": "<long>",
        "loanAccount": {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "isExistPromisePayment": "<boolean>",
            "bucket": "B2",
            "leadAccountFlag": "<boolean>",
            "accountNumber": "<string>",
            "branchCode": "<integer>",
            "customerNumber": "<integer>",
            "personId": "<long>",
            "accountReference": "<string>",
            "usageDate": "<dateTime>",
            "accountSuffix": "<integer>",
            "type": "IHTIYAC_KREDISI",
            "productCode": "<string>",
            "currencyCode": "<string>",
            "currentAccountIbanNumber": "<string>",
            "accDpd": "<integer>",
            "bucket1DueAmount": "<double>",
            "bucket1RemainingAmount": "<double>",
            "bucket1DueDate": "<dateTime>",
            "bucket2DueAmount": "<double>",
            "bucket2RemainingAmount": "<double>",
            "bucket2DueDate": "<dateTime>",
            "bucket3DueAmount": "<double>",
            "bucket3RemainingAmount": "<double>",
            "bucket3DueDate": "<dateTime>",
            "rollbackFlag": "<string>",
            "restructuredFlag": "<string>",
            "lastPaymentAmount": "<double>",
            "lastPaymentDate": "<dateTime>",
            "muacceliyetDate": "<dateTime>",
            "coreLastUpdateDate": "<dateTime>",
            "stagingImportId": "<long>",
            "maturityDate": "<dateTime>",
            "balance": "<double>",
            "balanceTl": "<double>",
            "pursuable": "<double>",
            "pursuableTl": "<double>",
            "accountLimit": "<double>",
            "accountLimitTl": "<double>",
            "principalAmount": "<double>",
            "dueDate": "<dateTime>",
            "installmentNumber": "<integer>",
            "remainingInstallmentNumber": "<integer>",
            "maxDpd": "<integer>",
            "nextDueDate": "<dateTime>",
            "restructuredCount": "<integer>",
            "cautionAmount": "<double>",
            "delayRate": "<double>",
            "channelDetail": "<string>",
            "dealerName": "<string>",
            "dealerProductName": "<string>",
            "cautionName": "<string>",
            "firstPaymentFlag": "<string>",
            "insuranceFlag": "<string>",
            "insuranceName": "<string>",
            "campaignName": "<string>",
            "nplSuffix": "<integer>",
            "nplDate": "<dateTime>",
            "yySuffix": "<integer>",
            "yyDate": "<dateTime>"
        },
        "loanAccountId": "<long>",
        "person": {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "segment": "<string>",
            "customerId": "<long>",
            "customerNumber": "<long>",
            "relationCustNum": "<long>",
            "relationType": "GUARANTOR",
            "identityNumber": "<string>",
            "name": "<string>",
            "middleName": "<string>",
            "surname": "<string>",
            "firmName": "<string>",
            "personnelFlag": "<boolean>",
            "vipFlag": "<boolean>",
            "birthDate": "<dateTime>",
            "birthPlace": "<string>",
            "workflowCode": "<string>",
            "gender": "Male",
            "dateOfDeath": "<dateTime>",
            "coreLastUpdateDate": "<dateTime>",
            "workIsMailing": "<boolean>",
            "nplFlag": "<boolean>",
            "selfCuredFlag": "<boolean>",
            "nplDate": "<dateTime>",
            "lastKrsSearchDate": "<dateTime>",
            "currentKkbScore": "<integer>",
            "creditCardUsageRate": "<double>",
            "kmhUsageRate": "<double>",
            "collectionScore": "<string>",
            "lastMonthApplicationCount": "<integer>",
            "otherBankMortgageLoanPaymentPerformance": "<string>",
            "blockageFlag": "<boolean>",
            "hepsiDpdMaxLm": "<integer>",
            "sumNumFailL3m": "<integer>",
            "tumKredilerDpdMaxMin6": "<integer>",
            "avgAsinitsBurganOverOutsV12lm": "<string>",
            "hepsiDpdMaxL12m": "<integer>",
            "hepsiDpdLm": "<integer>",
            "hepsiDpdMaxV3lm": "<string>",
            "hepsiTotalOutsV3lm": "<string>",
            "hepsiDpdAmtOutsVlm": "<string>",
            "hepsiDpdAmtOutsMax12": "<double>",
            "modelType": "<string>",
            "finalRatio": "<double>",
            "totalCashRisk": "<double>",
            "totalLimit": "<double>",
            "totalRisk": "<double>",
            "totalPursuable": "<double>",
            "minPursuable": "<double>",
            "totalAssets": "<double>",
            "totalColleteral": "<double>",
            "totalLimitUtilRatio": "<double>",
            "allMaxDpd": "<integer>",
            "engagementGuarantorInfo": "<string>"
        },
        "personId": "<long>",
        "relationType": "GUARANTOR",
        "promiseDate": "<dateTime>",
        "promiseAmount": "<double>",
        "sequenceNumber": "<integer>",
        "note": "<string>",
        "isPaid": "<boolean>",
        "payment": {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "loanAccountId": "<long>",
            "paymentDate": "<dateTime>",
            "paymentAmount": "<double>",
            "paymentType": "CashDeposit",
            "paymentChannel": "<string>",
            "paymentReference": "<string>",
            "sequenceNumber": "<integer>",
            "isSeqCompleted": "<boolean>",
            "partialPaidInstallmentAmount": "<double>",
            "partialPaidDelayInterestAmount": "<double>",
            "partialPaidDelayKkdfAmount": "<double>",
            "partialPaidDelayBsmvAmount": "<double>",
            "totalPaymentAmount": "<double>"
        },
        "loanAccountPaymentId": "<long>",
        "giveName": "<string>",
        "accountNumber": "<string>",
        "activityCreateDate": "<dateTime>"
    }
}
```
</details>

---

#### **_Retrieve PromisePayments by Loan Account Guid_**

**GET** `/api/v3/PromisePayment/GetByLoanAccountGuid`

#### Description

Returns PromisePayments associated with a specific LoanAccount GUID.

##### Query Parameters

| Parameter | Type   | Description       |
| :-------- | :----- | :---------------- |
| `guid`    | `guid` | (**_required_** ) |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/PromisePayment/GetByLoanAccountGuid?guid=%3Cuuid%3E" -H 'Accept: text/plain'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": [
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "activityId": "<long>",
            "loanAccountId": "<long>",
            "personId": "<long>",
            "relationType": "AGENT",
            "promiseDate": "<dateTime>",
            "promiseAmount": "<double>",
            "sequenceNumber": "<integer>",
            "note": "<string>",
            "isPaid": "<boolean>",
            "loanAccountPaymentId": "<long>",
            "giveName": "<string>",
            "accountNumber": "<string>",
            "activityCreateDate": "<dateTime>"
        },
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "activityId": "<long>",
            "loanAccountId": "<long>",
            "personId": "<long>",
            "relationType": "ATTORNEY",
            "promiseDate": "<dateTime>",
            "promiseAmount": "<double>",
            "sequenceNumber": "<integer>",
            "note": "<string>",
            "isPaid": "<boolean>",
            "loanAccountPaymentId": "<long>",
            "giveName": "<string>",
            "accountNumber": "<string>",
            "activityCreateDate": "<dateTime>"
        }
    ]
}
```
</details>

---

#### **_Retrieve Promise Paymnets by Activity Guid_**

**GET** `/api/v3/PromisePayment/GetByActivityGuid`

#### Description

Returns PromisePayments associated with a specific Activity GUID.

##### Query Parameters

| Parameter | Type   | Description       |
| :-------- | :----- | :---------------- |
| `guid`    | `guid` | (**_required_** ) |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/PromisePayment/GetByActivityGuid?guid=%3Cuuid%3E" -H 'Accept: text/plain'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": [
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "activityId": "<long>",
            "loanAccountId": "<long>",
            "personId": "<long>",
            "relationType": "AGENT",
            "promiseDate": "<dateTime>",
            "promiseAmount": "<double>",
            "sequenceNumber": "<integer>",
            "note": "<string>",
            "isPaid": "<boolean>",
            "loanAccountPaymentId": "<long>",
            "giveName": "<string>",
            "accountNumber": "<string>",
            "activityCreateDate": "<dateTime>"
        },
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "activityId": "<long>",
            "loanAccountId": "<long>",
            "personId": "<long>",
            "relationType": "ATTORNEY",
            "promiseDate": "<dateTime>",
            "promiseAmount": "<double>",
            "sequenceNumber": "<integer>",
            "note": "<string>",
            "isPaid": "<boolean>",
            "loanAccountPaymentId": "<long>",
            "giveName": "<string>",
            "accountNumber": "<string>",
            "activityCreateDate": "<dateTime>"
        }
    ]
}
```
</details>

---

#### **_Retrieve PromisePayments by WorkAction Guid_**

**GET** `/api/v3/PromisePayment/GetByWorkActionGuid`

#### Description

Returns PromisePayments associated with a specific WorkAction GUID.

##### Query Parameters

| Parameter | Type   | Description       |
| :-------- | :----- | :---------------- |
| `guid`    | `guid` | (**_required_** ) |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/PromisePayment/GetByWorkActionGuid?guid=%3Cuuid%3E" -H 'Accept: text/plain'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": [
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "activityId": "<long>",
            "loanAccountId": "<long>",
            "personId": "<long>",
            "relationType": "AGENT",
            "promiseDate": "<dateTime>",
            "promiseAmount": "<double>",
            "sequenceNumber": "<integer>",
            "note": "<string>",
            "isPaid": "<boolean>",
            "loanAccountPaymentId": "<long>",
            "giveName": "<string>",
            "accountNumber": "<string>",
            "activityCreateDate": "<dateTime>"
        },
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "activityId": "<long>",
            "loanAccountId": "<long>",
            "personId": "<long>",
            "relationType": "ATTORNEY",
            "promiseDate": "<dateTime>",
            "promiseAmount": "<double>",
            "sequenceNumber": "<integer>",
            "note": "<string>",
            "isPaid": "<boolean>",
            "loanAccountPaymentId": "<long>",
            "giveName": "<string>",
            "accountNumber": "<string>",
            "activityCreateDate": "<dateTime>"
        }
    ]
}
```
</details>

---

#### **_Retrieve PromisePayments by Worklist Guid with pagination_**

**GET** `/api/v3/PromisePayment/GetByWorklistGuid`

#### Description

Returns paginated PromisePayments associated with a specific Worklist GUID.

##### Query Parameters

| Parameter | Type      | Description       |
| :-------- | :-------- | :---------------- |
| `guid`    | `guid`    | (**_required_** ) |
| `offset`  | `integer` |                   |
| `limit`   | `integer` |                   |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/PromisePayment/GetByWorklistGuid?guid=%3Cuuid%3E&Offset=%3Cinteger%3E&Limit=%3Cinteger%3E" -H 'Accept: text/plain'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": [
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "activityId": "<long>",
            "loanAccountId": "<long>",
            "personId": "<long>",
            "relationType": "AGENT",
            "promiseDate": "<dateTime>",
            "promiseAmount": "<double>",
            "sequenceNumber": "<integer>",
            "note": "<string>",
            "isPaid": "<boolean>",
            "loanAccountPaymentId": "<long>",
            "giveName": "<string>",
            "accountNumber": "<string>",
            "activityCreateDate": "<dateTime>"
        },
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "activityId": "<long>",
            "loanAccountId": "<long>",
            "personId": "<long>",
            "relationType": "ATTORNEY",
            "promiseDate": "<dateTime>",
            "promiseAmount": "<double>",
            "sequenceNumber": "<integer>",
            "note": "<string>",
            "isPaid": "<boolean>",
            "loanAccountPaymentId": "<long>",
            "giveName": "<string>",
            "accountNumber": "<string>",
            "activityCreateDate": "<dateTime>"
        }
    ]
}
```
</details>

---

#### **_Retrieve PromisePayments by Person Guid with pagination_**

**GET** `/api/v3/PromisePayment/GetByPersonGuid`

#### Description

Returns paginated PromisePayments associated with a specific Person GUID.

##### Query Parameters

| Parameter | Type      | Description       |
| :-------- | :-------- | :---------------- |
| `guid`    | `guid`    | (**_required_** ) |
| `offset`  | `integer` |                   |
| `limit`   | `integer` |                   |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/PromisePayment/GetByPersonGuid?guid=%3Cuuid%3E&Offset=%3Cinteger%3E&Limit=%3Cinteger%3E" -H 'Accept: text/plain'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": [
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "activityId": "<long>",
            "loanAccountId": "<long>",
            "personId": "<long>",
            "relationType": "AGENT",
            "promiseDate": "<dateTime>",
            "promiseAmount": "<double>",
            "sequenceNumber": "<integer>",
            "note": "<string>",
            "isPaid": "<boolean>",
            "loanAccountPaymentId": "<long>",
            "giveName": "<string>",
            "accountNumber": "<string>",
            "activityCreateDate": "<dateTime>"
        },
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "activityId": "<long>",
            "loanAccountId": "<long>",
            "personId": "<long>",
            "relationType": "ATTORNEY",
            "promiseDate": "<dateTime>",
            "promiseAmount": "<double>",
            "sequenceNumber": "<integer>",
            "note": "<string>",
            "isPaid": "<boolean>",
            "loanAccountPaymentId": "<long>",
            "giveName": "<string>",
            "accountNumber": "<string>",
            "activityCreateDate": "<dateTime>"
        }
    ]
}
```
</details>

---

#### **_Retrieve PromisePayments by User with userIdentityNumber with pagination_**

**GET** `/api/v3/PromisePayment/GetByUserIdentityNumber`

#### Description

Returns paginated PromisePayments associated with a specific User with userIdentityNumber.

##### Query Parameters

| Parameter            | Type      | Description       |
| :------------------- | :-------- | :---------------- |
| `userIdentityNumber` | `string`  | (**_required_** ) |
| `offset`             | `integer` |                   |
| `limit`              | `integer` |                   |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/PromisePayment/GetByUserIdentityNumber?userIdentityNumber=%3Cstring%3E&Offset=%3Cinteger%3E&Limit=%3Cinteger%3E" -H 'Accept: text/plain'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": [
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "activityId": "<long>",
            "loanAccountId": "<long>",
            "personId": "<long>",
            "relationType": "AGENT",
            "promiseDate": "<dateTime>",
            "promiseAmount": "<double>",
            "sequenceNumber": "<integer>",
            "note": "<string>",
            "isPaid": "<boolean>",
            "loanAccountPaymentId": "<long>",
            "giveName": "<string>",
            "accountNumber": "<string>",
            "activityCreateDate": "<dateTime>"
        },
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "activityId": "<long>",
            "loanAccountId": "<long>",
            "personId": "<long>",
            "relationType": "ATTORNEY",
            "promiseDate": "<dateTime>",
            "promiseAmount": "<double>",
            "sequenceNumber": "<integer>",
            "note": "<string>",
            "isPaid": "<boolean>",
            "loanAccountPaymentId": "<long>",
            "giveName": "<string>",
            "accountNumber": "<string>",
            "activityCreateDate": "<dateTime>"
        }
    ]
}
```
</details>

---

#### **_Create a PromisePayment_**

**POST** `/api/v3/PromisePayment/Create`

#### Description

Creates new PromisePayments based on the provided data.

##### Query Parameters

| Parameter       | Type | Description |
| :-------------- | :--- | :---------- |
| `no parameters` |      |             |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X POST "http://localhost:7080/api/v3/PromisePayment/Create" -H 'Accept: text/plain' -data '[
  {
    "activityId": "<long>",
    "loanAccountId": "<long>",
    "personId": "<long>",
    "relationType": "OTHER",
    "promiseDate": "<dateTime>",
    "promiseAmount": "<double>",
    "sequenceNumber": "<integer>",
    "note": "<string>"
  },
  {
    "activityId": "<long>",
    "loanAccountId": "<long>",
    "personId": "<long>",
    "relationType": "SPOUSE",
    "promiseDate": "<dateTime>",
    "promiseAmount": "<double>",
    "sequenceNumber": "<integer>",
    "note": "<string>"
  }
]'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": [
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "activityId": "<long>",
            "loanAccountId": "<long>",
            "personId": "<long>",
            "relationType": "AGENT",
            "promiseDate": "<dateTime>",
            "promiseAmount": "<double>",
            "sequenceNumber": "<integer>",
            "note": "<string>",
            "isPaid": "<boolean>",
            "loanAccountPaymentId": "<long>",
            "giveName": "<string>",
            "accountNumber": "<string>",
            "activityCreateDate": "<dateTime>"
        },
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "activityId": "<long>",
            "loanAccountId": "<long>",
            "personId": "<long>",
            "relationType": "ATTORNEY",
            "promiseDate": "<dateTime>",
            "promiseAmount": "<double>",
            "sequenceNumber": "<integer>",
            "note": "<string>",
            "isPaid": "<boolean>",
            "loanAccountPaymentId": "<long>",
            "giveName": "<string>",
            "accountNumber": "<string>",
            "activityCreateDate": "<dateTime>"
        }
    ]
}
```
</details>

---

#### **_Update a PromisePayment_**

**POST** `/api/v3/PromisePayment/Update`

#### Description

Updates an existing PromisePayment with the specified details.

##### Query Parameters

| Parameter       | Type | Description |
| :-------------- | :--- | :---------- |
| `no parameters` |      |             |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X POST "http://localhost:7080/api/v3/PromisePayment/Update" -H 'Accept: text/plain' -data '{
  "guid": "<uuid>",
  "isActive": "<boolean>",
  "updateUserId": "<long>",
  "activityId": "<long>",
  "loanAccountId": "<long>",
  "personId": "<long>",
  "relationType": "OWNER",
  "promiseDate": "<dateTime>",
  "promiseAmount": "<double>",
  "sequenceNumber": "<integer>",
  "note": "<string>",
  "isPaid": "<boolean>",
  "loanAccountPaymentId": "<long>"
}'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": {
        "id": "<long>",
        "guid": "<uuid>",
        "isActive": "<boolean>",
        "createDate": "<dateTime>",
        "createUserId": "<long>",
        "updateDate": "<dateTime>",
        "updateUserId": "<long>",
        "activityId": "<long>",
        "loanAccountId": "<long>",
        "personId": "<long>",
        "relationType": "SPOUSE",
        "promiseDate": "<dateTime>",
        "promiseAmount": "<double>",
        "sequenceNumber": "<integer>",
        "note": "<string>",
        "isPaid": "<boolean>",
        "loanAccountPaymentId": "<long>",
        "giveName": "<string>",
        "accountNumber": "<string>",
        "activityCreateDate": "<dateTime>"
    }
}
```
</details>

---

#### **_Deactivate a PromisePayment_**

**POST** `/api/v3/PromisePayment/Deactivate`

#### Description

Deactivates the specified PromisePayment.

##### Query Parameters

| Parameter       | Type | Description |
| :-------------- | :--- | :---------- |
| `no parameters` |      |             |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X POST "http://localhost:7080/api/v3/PromisePayment/Deactivate" -H 'Accept: text/plain' -data '{
  "guid": "<uuid>",
  "updateUserId": "<long>"
}'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": {
        "nullable": true
    }
}
```
</details>

---

## ProxyServices

#### **_Promise Payment Calculated_**

**GET** `/api/v3/ProxyServices/PromisePaymentCalculate`

#### Description

##### Query Parameters

| Parameter | Type   | Description |
| :-------- | :----- | :---------- |
| `guid`    | `guid` |             |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/ProxyServices/PromisePaymentCalculate?guid=%3Cuuid%3E" -H 'Accept: text/plain'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": "<double>"
}
```
</details>

---

#### **_Retrieve BankAccountBalance list by AccountBranchCode and AccountNumber_**

**GET** `/api/v3/ProxyServices/GetBankAccountBalanceList`

#### Description

Fetches BankAccountBalances related to AccountBranchCode and AccountNumber.

##### Query Parameters

| Parameter           | Type     | Description |
| :------------------ | :------- | :---------- |
| `AccountBranchCode` | `string` |             |
| `AccountNumber`     | `string` |             |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/ProxyServices/GetBankAccountBalanceList?AccountBranchCode=%3Cstring%3E&AccountNumber=%3Cstring%3E" -H 'Accept: text/plain'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": [
        {
            "accountBalance": "<double>",
            "accountBranchCode": "<integer>",
            "accountNumber": "<integer>",
            "accountSuffix": "<integer>",
            "currencyCode": "<string>",
            "productCode": "<string>"
        },
        {
            "accountBalance": "<double>",
            "accountBranchCode": "<integer>",
            "accountNumber": "<integer>",
            "accountSuffix": "<integer>",
            "currencyCode": "<string>",
            "productCode": "<string>"
        }
    ]
}
```
</details>

---

#### **_Retrieve BankAccountCaution list by AccountBranchCode and AccountNumber_**

**GET** `/api/v3/ProxyServices/GetBankAccountCautionList`

#### Description

Fetches BankAccountCautions related to AccountBranchCode and AccountNumber.

##### Query Parameters

| Parameter           | Type     | Description |
| :------------------ | :------- | :---------- |
| `AccountBranchCode` | `string` |             |
| `AccountNumber`     | `string` |             |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/ProxyServices/GetBankAccountCautionList?AccountBranchCode=%3Cstring%3E&AccountNumber=%3Cstring%3E" -H 'Accept: text/plain'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": [
        {
            "cautionAmount": "<integer>",
            "cautionCurrencyCode": "<string>",
            "cautionKind": "<string>",
            "cautionKindText": "<string>",
            "cautionSuffix": "<integer>",
            "cautionTranBranchCode": "<integer>",
            "cautionType": "<string>",
            "cautionsRef": "<integer>",
            "customerNumber": "<integer>"
        },
        {
            "cautionAmount": "<integer>",
            "cautionCurrencyCode": "<string>",
            "cautionKind": "<string>",
            "cautionKindText": "<string>",
            "cautionSuffix": "<integer>",
            "cautionTranBranchCode": "<integer>",
            "cautionType": "<string>",
            "cautionsRef": "<integer>",
            "customerNumber": "<integer>"
        }
    ]
}
```
</details>

---

#### **_Retrieve BankAccountLoan list by AccountBranchCode and AccountNumber and AccountSuffix_**

**GET** `/api/v3/ProxyServices/GetBankAccountLoanList`

#### Description

Fetches BankAccountLoans related to AccountBranchCode and AccountNumber and AccountSuffix.

##### Query Parameters

| Parameter           | Type      | Description |
| :------------------ | :-------- | :---------- |
| `AccountBranchCode` | `string`  |             |
| `AccountNumber`     | `string`  |             |
| `AccountSuffix`     | `integer` |             |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/ProxyServices/GetBankAccountLoanList?AccountBranchCode=%3Cstring%3E&AccountNumber=%3Cstring%3E&AccountSuffix=%3Cinteger%3E" -H 'Accept: text/plain'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": [
        {
            "delayDayNumber": "<integer>",
            "installmentAmount": "<double>",
            "installmentDate": "<string>",
            "paidCode": "<string>",
            "seqNum": "<integer>",
            "totalDelayAmount": "<double>",
            "totalPaymentAmount": "<double>",
            "isPromisePayment": "<boolean>",
            "promisePaymentGuid": "<uuid>"
        },
        {
            "delayDayNumber": "<integer>",
            "installmentAmount": "<double>",
            "installmentDate": "<string>",
            "paidCode": "<string>",
            "seqNum": "<integer>",
            "totalDelayAmount": "<double>",
            "totalPaymentAmount": "<double>",
            "isPromisePayment": "<boolean>",
            "promisePaymentGuid": "<uuid>"
        }
    ]
}
```
</details>

---

#### **_Retrieve BankAccountLoanFuture list by AccountBranchCode, AccountNumber and AccountSuffix_**

**GET** `/api/v3/ProxyServices/GetBankAccountLoanFutureList`

#### Description

Fetches BankAccountLoansFuture related to AccountBranchCode and AccountNumber and AccountSuffix and ForwardDay.

##### Query Parameters

| Parameter           | Type      | Description |
| :------------------ | :-------- | :---------- |
| `AccountBranchCode` | `string`  |             |
| `AccountNumber`     | `string`  |             |
| `AccountSuffix`     | `integer` |             |
| `ForwardDay`        | `string`  |             |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/ProxyServices/GetBankAccountLoanFutureList?AccountBranchCode=%3Cstring%3E&AccountNumber=%3Cstring%3E&AccountSuffix=%3Cinteger%3E&ForwardDay=%3Cstring%3E" -H 'Accept: text/plain'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": [
        {
            "delayDayNumber": "<integer>",
            "installmentAmount": "<double>",
            "installmentDate": "<string>",
            "paidCode": "<string>",
            "seqNum": "<integer>",
            "totalDelayAmount": "<double>",
            "totalPaymentAmount": "<double>",
            "isPromisePayment": "<boolean>",
            "promisePaymentGuid": "<uuid>"
        },
        {
            "delayDayNumber": "<integer>",
            "installmentAmount": "<double>",
            "installmentDate": "<string>",
            "paidCode": "<string>",
            "seqNum": "<integer>",
            "totalDelayAmount": "<double>",
            "totalPaymentAmount": "<double>",
            "isPromisePayment": "<boolean>",
            "promisePaymentGuid": "<uuid>"
        }
    ]
}
```
</details>

---

#### **_Retrieve BankLoanCloseAmount list by AccountBranchCode, AccountNumber and AccountSuffix_**

**GET** `/api/v3/ProxyServices/GetBankLoanCloseAmount`

#### Description

Fetches BankAccountLoans related to AccountBranchCode and AccountNumber and AccountSuffix.

##### Query Parameters

| Parameter           | Type      | Description |
| :------------------ | :-------- | :---------- |
| `AccountBranchCode` | `string`  |             |
| `AccountNumber`     | `string`  |             |
| `AccountSuffix`     | `integer` |             |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/ProxyServices/GetBankLoanCloseAmount?AccountBranchCode=%3Cstring%3E&AccountNumber=%3Cstring%3E&AccountSuffix=%3Cinteger%3E" -H 'Accept: text/plain'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": "<double>"
}
```
</details>

---

#### **_Retrieve CardDetailandStatement by customerId and cardNumber_**

**GET** `/api/v3/ProxyServices/GetOnlineCardDetail`

#### Description

Fetches BankAccountLoans related to customerId and cardNumber.

##### Query Parameters

| Parameter    | Type     | Description |
| :----------- | :------- | :---------- |
| `customerId` | `string` |             |
| `cardNumber` | `string` |             |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://home.ermanseneren.com:7020/api/v3/ProxyServices/GetOnlineCardDetail?customerId=%3Cstring%3E&cardNumber=%3Cstring%3E" -H 'Accept: text/plain'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": "<double>"
}

````
</details>

---

## User


#### **_Retrieve a user by Guid_**

**GET** `/api/v3/User/GetByGuid`

#### Description

Returns a specific user identified by GUID, including related details.

##### Query Parameters

| Parameter         | Type   | Description       |
| :---------------- | :----- | :---------------- |
| `guid` | `guid` | (**_required_**) |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/User/GetByGuid?guid=%3Cuuid%3E" -H 'Accept: text/plain'
````

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": {
        "id": "<long>",
        "guid": "<uuid>",
        "isActive": "<boolean>",
        "createDate": "<dateTime>",
        "createUserId": "<long>",
        "updateDate": "<dateTime>",
        "updateUserId": "<long>",
        "agentNumber": "<string>",
        "identityNumber": "<string>",
        "firstName": "<string>",
        "middleName": "<string>",
        "lastName": "<string>",
        "role": "Agent",
        "roleNumber": "<integer>",
        "userGroupMembers": [
            {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "userGroupsId": "<long>",
                "userId": "<long>"
            },
            {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "userGroupsId": "<long>",
                "userId": "<long>"
            }
        ],
        "worklistUsers": [
            {
                "worklistId": "<long>",
                "userId": "<long>"
            },
            {
                "worklistId": "<long>",
                "userId": "<long>"
            }
        ],
        "activities": [
            {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "userId": "<long>",
                "type": "CALL_CLOSE",
                "workActionId": "<long>",
                "note": "<string>",
                "pinned": "<boolean>",
                "status": "NEW_ENTITY",
                "uuid": "<string>",
                "resultId": "<long>",
                "result": {
                    "id": "<long>",
                    "guid": "<uuid>",
                    "isActive": "<boolean>",
                    "createDate": "<dateTime>",
                    "createUserId": "<long>",
                    "updateDate": "<dateTime>",
                    "updateUserId": "<long>",
                    "result": "<string>",
                    "subResult": "<boolean>",
                    "nextAction": "WAIT_RETRY",
                    "type": "PROMISEPAYMENT",
                    "nextActionDelay": "<integer>",
                    "nextActionMaxTry": "<integer>"
                },
                "subResultId": "<long>",
                "subResult": {
                    "id": "<long>",
                    "guid": "<uuid>",
                    "isActive": "<boolean>",
                    "createDate": "<dateTime>",
                    "createUserId": "<long>",
                    "updateDate": "<dateTime>",
                    "updateUserId": "<long>",
                    "activityResultId": "<long>",
                    "subResult": "<string>",
                    "nextAction": "WAIT_RETRY",
                    "nextActionDelay": "<integer>",
                    "nextActionMaxTry": "<integer>"
                },
                "scheduleDate": "<dateTime>"
            },
            {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "userId": "<long>",
                "type": "CALL_AUTO",
                "workActionId": "<long>",
                "note": "<string>",
                "pinned": "<boolean>",
                "status": "NEW_ENTITY",
                "uuid": "<string>",
                "resultId": "<long>",
                "result": {
                    "id": "<long>",
                    "guid": "<uuid>",
                    "isActive": "<boolean>",
                    "createDate": "<dateTime>",
                    "createUserId": "<long>",
                    "updateDate": "<dateTime>",
                    "updateUserId": "<long>",
                    "result": "<string>",
                    "subResult": "<boolean>",
                    "nextAction": "WAIT_RETRY",
                    "type": "PROMISEPAYMENT",
                    "nextActionDelay": "<integer>",
                    "nextActionMaxTry": "<integer>"
                },
                "subResultId": "<long>",
                "subResult": {
                    "id": "<long>",
                    "guid": "<uuid>",
                    "isActive": "<boolean>",
                    "createDate": "<dateTime>",
                    "createUserId": "<long>",
                    "updateDate": "<dateTime>",
                    "updateUserId": "<long>",
                    "activityResultId": "<long>",
                    "subResult": "<string>",
                    "nextAction": "LOOK_AT_SUB",
                    "nextActionDelay": "<integer>",
                    "nextActionMaxTry": "<integer>"
                },
                "scheduleDate": "<dateTime>"
            }
        ]
    }
}
```
</details>

---

#### **_Retrieve a user guid and Id by userIdentityNumber_**

**GET** `/api/v3/User/GetByIdentityNumber`

#### Description

Returns a specific user identified by userIdentityNumber, including related details.

##### Query Parameters

| Parameter            | Type     | Description      |
| :------------------- | :------- | :--------------- |
| `userIdentityNumber` | `string` | (**_required_**) |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/User/GetByIdentityNumber?userIdentityNumber=%3Cstring%3E" -H 'Accept: text/plain'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": {
        "id": "<long>",
        "guid": "<uuid>"
    }
}
```
</details>

---

#### **_Retrieve all users_**

**GET** `/api/v3/User/GetAll`

#### Description

Returns a paginated list of all users.

##### Query Parameters

| Parameter   | Type      | Description |
| :---------- | :-------- | :---------- |
| `offset`    | `integer` |             |
| `limit`     | `integer` |             |
| `sortBy`    | `string`  |             |
| `sortOrder` | `string`  |             |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/User/GetAll?Offset=%3Cinteger%3E&Limit=%3Cinteger%3E&sortBy=%3Cstring%3E&sortOrder=asc" -H 'Accept: text/plain'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": [
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "agentNumber": "<string>",
            "identityNumber": "<string>",
            "firstName": "<string>",
            "middleName": "<string>",
            "lastName": "<string>",
            "role": "TeamLeader",
            "roleNumber": "<integer>"
        },
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "agentNumber": "<string>",
            "identityNumber": "<string>",
            "firstName": "<string>",
            "middleName": "<string>",
            "lastName": "<string>",
            "role": "TeamLeader",
            "roleNumber": "<integer>"
        }
    ],
    "totalRowCount": "<integer>",
    "totalPageCount": "<integer>",
    "offset": "<integer>",
    "limit": "<integer>"
}
```
</details>

---

#### **_Retrieve all userGroups_**

**GET** `/api/v3/User/GetAllUserGroups`

#### Description

Returns a paginated list of all usergroups.

##### Query Parameters

| Parameter       | Type | Description |
| :-------------- | :--- | :---------- |
| `no parameters` |      |             |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/User/GetAllUserGroups" -H 'Accept: text/plain'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": [
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "name": "<string>",
            "description": "<string>"
        },
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "name": "<string>",
            "description": "<string>"
        }
    ]
}
```
</details>

---

#### **_Retrieve all users including deactivated_**

**GET** `/api/v3/User/GetAllWithDeActivate`

#### Description

Returns a paginated list of all users, including those who are deactivated.

##### Query Parameters

| Parameter | Type      | Description |
| :-------- | :-------- | :---------- |
| `offset`  | `integer` |             |
| `limit`   | `integer` |             |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/User/GetAllWithDeActivate?Offset=%3Cinteger%3E&Limit=%3Cinteger%3E" -H 'Accept: text/plain'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": [
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "agentNumber": "<string>",
            "identityNumber": "<string>",
            "firstName": "<string>",
            "middleName": "<string>",
            "lastName": "<string>",
            "role": "TeamLeader",
            "roleNumber": "<integer>"
        },
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "agentNumber": "<string>",
            "identityNumber": "<string>",
            "firstName": "<string>",
            "middleName": "<string>",
            "lastName": "<string>",
            "role": "TeamLeader",
            "roleNumber": "<integer>"
        }
    ],
    "totalRowCount": "<integer>",
    "totalPageCount": "<integer>",
    "offset": "<integer>",
    "limit": "<integer>"
}
```
</details>

---

#### **_Get summary statistics about users_**

**GET** `/api/v3/User/Summary`

#### Description

Provides statistical summary data for a specific user over a given period.

##### Query Parameters

| Parameter   | Type     | Description |
| :---------- | :------- | :---------- |
| `userGuid`  | `guid`   |             |
| `startDate` | `string` |             |
| `endDate`   | `string` |             |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/User/Summary?userGuid=%3Cuuid%3E&startDate=%3CdateTime%3E&endDate=%3CdateTime%3E" -H 'Accept: text/plain'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": {
        "pendingCalls": "<integer>",
        "completedCall": "<integer>",
        "promiseToPay": "<integer>",
        "totalCollection": "<integer>"
    }
}
```
</details>

---

#### **_Update a user_**

**POST** `/api/v3/User/Update`

#### Description

Updates the details of an existing user.

##### Query Parameters

| Parameter       | Type | Description |
| :-------------- | :--- | :---------- |
| `no parameters` |      |             |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X POST "http://localhost:7080/api/v3/User/Update" -H 'Accept: text/plain' -data '{
  "guid": "<uuid>",
  "isActive": "<boolean>",
  "updateUserId": "<long>",
  "agentNumber": "<string>",
  "identityNumber": "<string>",
  "firstName": "<string>",
  "middleName": "<string>",
  "lastName": "<string>",
  "role": "Admin"
}'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": {
        "id": "<long>",
        "guid": "<uuid>",
        "isActive": "<boolean>",
        "createDate": "<dateTime>",
        "createUserId": "<long>",
        "updateDate": "<dateTime>",
        "updateUserId": "<long>",
        "agentNumber": "<string>",
        "identityNumber": "<string>",
        "firstName": "<string>",
        "middleName": "<string>",
        "lastName": "<string>",
        "role": "System",
        "roleNumber": "<integer>"
    }
}
```
</details>

---

#### **_Updates a user's worklists_**

**POST** `/api/v3/User/UpdateUserWorklists`

#### Description

Updates the worklists assigned to a specific user.

##### Query Parameters

| Parameter       | Type | Description |
| :-------------- | :--- | :---------- |
| `no parameters` | ``   |             |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X POST "http://localhost:7080/api/v3/User/UpdateUserWorklists" -H 'Accept: text/plain' -data '{
  "userId": "<long>",
  "worklistIds": [
    "<integer>",
    "<integer>"
  ]
}'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": {
        "nullable": true
    }
}
```
</details>

---

#### **_Deactivate a user_**

**POST** `/api/v3/User/Deactivate`

#### Description

Deactivates a specific user, rendering them inactive in the system.

##### Query Parameters

| Parameter       | Type | Description |
| :-------------- | :--- | :---------- |
| `no parameters` |      |             |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X POST "http://localhost:7080/api/v3/User/Deactivate" -H 'Accept: text/plain' -data '{
  "guid": "<uuid>",
  "updateUserId": "<long>"
}'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": {
        "nullable": true
    }
}
```
</details>

---

#### **_Import users_**

**POST** `/api/v3/User/Synchronize`

#### Description

Create user or update with the specified details.

##### Query Parameters

| Parameter       | Type | Description |
| :-------------- | :--- | :---------- |
| `no parameters` |      |             |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X POST "http://localhost:7080/api/v3/User/Synchronize" -H 'Accept: text/plain' -data '{
  "updateUserId": "<long>"
}'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": [
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "agentNumber": "<string>",
            "identityNumber": "<string>",
            "firstName": "<string>",
            "middleName": "<string>",
            "lastName": "<string>",
            "role": "System",
            "roleNumber": "<integer>"
        },
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "agentNumber": "<string>",
            "identityNumber": "<string>",
            "firstName": "<string>",
            "middleName": "<string>",
            "lastName": "<string>",
            "role": "Manager",
            "roleNumber": "<integer>"
        }
    ]
}
```
</details>

---

## WorkAction

#### **_Retrieve a work action by Guid_**

**GET** `/api/v3/WorkAction/GetByGuid`

#### Description

Fetches a detailed view of a specific work action identified by GUID.

##### Query Parameters

| Parameter | Type   | Description      |
| :-------- | :----- | :--------------- |
| `guid`    | `guid` | (**_required_**) |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/WorkAction/GetByGuid?guid=%3Cuuid%3E" -H 'Accept: text/plain'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": {
        "id": "<long>",
        "guid": "<uuid>",
        "isActive": "<boolean>",
        "createDate": "<dateTime>",
        "createUserId": "<long>",
        "updateDate": "<dateTime>",
        "updateUserId": "<long>",
        "status": "NEW_ENTITY",
        "worklistId": "<long>",
        "worklist": {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "name": "<string>",
            "type": "MANUAL",
            "auto": "<boolean>",
            "targetName": "<string>",
            "callingList": "<string>",
            "personal": "<boolean>"
        },
        "personId": "<long>",
        "person": {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "segment": "<string>",
            "customerId": "<long>",
            "customerNumber": "<long>",
            "relationCustNum": "<long>",
            "relationType": "CHILD",
            "identityNumber": "<string>",
            "name": "<string>",
            "middleName": "<string>",
            "surname": "<string>",
            "firmName": "<string>",
            "personnelFlag": "<boolean>",
            "vipFlag": "<boolean>",
            "birthDate": "<dateTime>",
            "birthPlace": "<string>",
            "workflowCode": "<string>",
            "gender": "Female",
            "dateOfDeath": "<dateTime>",
            "coreLastUpdateDate": "<dateTime>",
            "workIsMailing": "<boolean>",
            "nplFlag": "<boolean>",
            "selfCuredFlag": "<boolean>",
            "nplDate": "<dateTime>",
            "lastKrsSearchDate": "<dateTime>",
            "currentKkbScore": "<integer>",
            "creditCardUsageRate": "<double>",
            "kmhUsageRate": "<double>",
            "collectionScore": "<string>",
            "lastMonthApplicationCount": "<integer>",
            "otherBankMortgageLoanPaymentPerformance": "<string>",
            "blockageFlag": "<boolean>",
            "hepsiDpdMaxLm": "<integer>",
            "sumNumFailL3m": "<integer>",
            "tumKredilerDpdMaxMin6": "<integer>",
            "avgAsinitsBurganOverOutsV12lm": "<string>",
            "hepsiDpdMaxL12m": "<integer>",
            "hepsiDpdLm": "<integer>",
            "hepsiDpdMaxV3lm": "<string>",
            "hepsiTotalOutsV3lm": "<string>",
            "hepsiDpdAmtOutsVlm": "<string>",
            "hepsiDpdAmtOutsMax12": "<double>",
            "modelType": "<string>",
            "finalRatio": "<double>",
            "totalCashRisk": "<double>",
            "totalLimit": "<double>",
            "totalRisk": "<double>",
            "totalPursuable": "<double>",
            "minPursuable": "<double>",
            "totalAssets": "<double>",
            "totalColleteral": "<double>",
            "totalLimitUtilRatio": "<double>",
            "allMaxDpd": "<integer>",
            "engagementGuarantorInfo": "<string>"
        },
        "loanAccountId": "<long>",
        "loanAccount": {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "isExistPromisePayment": "<boolean>",
            "bucket": "B0",
            "leadAccountFlag": "<boolean>",
            "accountNumber": "<string>",
            "branchCode": "<integer>",
            "customerNumber": "<integer>",
            "personId": "<long>",
            "accountReference": "<string>",
            "usageDate": "<dateTime>",
            "accountSuffix": "<integer>",
            "type": "TASIT_KREDISI",
            "productCode": "<string>",
            "currencyCode": "<string>",
            "currentAccountIbanNumber": "<string>",
            "accDpd": "<integer>",
            "bucket1DueAmount": "<double>",
            "bucket1RemainingAmount": "<double>",
            "bucket1DueDate": "<dateTime>",
            "bucket2DueAmount": "<double>",
            "bucket2RemainingAmount": "<double>",
            "bucket2DueDate": "<dateTime>",
            "bucket3DueAmount": "<double>",
            "bucket3RemainingAmount": "<double>",
            "bucket3DueDate": "<dateTime>",
            "rollbackFlag": "<string>",
            "restructuredFlag": "<string>",
            "lastPaymentAmount": "<double>",
            "lastPaymentDate": "<dateTime>",
            "muacceliyetDate": "<dateTime>",
            "coreLastUpdateDate": "<dateTime>",
            "stagingImportId": "<long>",
            "maturityDate": "<dateTime>",
            "balance": "<double>",
            "balanceTl": "<double>",
            "pursuable": "<double>",
            "pursuableTl": "<double>",
            "accountLimit": "<double>",
            "accountLimitTl": "<double>",
            "principalAmount": "<double>",
            "dueDate": "<dateTime>",
            "installmentNumber": "<integer>",
            "remainingInstallmentNumber": "<integer>",
            "maxDpd": "<integer>",
            "nextDueDate": "<dateTime>",
            "restructuredCount": "<integer>",
            "cautionAmount": "<double>",
            "delayRate": "<double>",
            "channelDetail": "<string>",
            "dealerName": "<string>",
            "dealerProductName": "<string>",
            "cautionName": "<string>",
            "firstPaymentFlag": "<string>",
            "insuranceFlag": "<string>",
            "insuranceName": "<string>",
            "campaignName": "<string>",
            "nplSuffix": "<integer>",
            "nplDate": "<dateTime>",
            "yySuffix": "<integer>",
            "yyDate": "<dateTime>"
        },
        "template": "<string>",
        "templateParameter": "<string>",
        "contactPersonId": "<long>",
        "contactPerson": {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "segment": "<string>",
            "customerId": "<long>",
            "customerNumber": "<long>",
            "relationCustNum": "<long>",
            "relationType": "OWNER",
            "identityNumber": "<string>",
            "name": "<string>",
            "middleName": "<string>",
            "surname": "<string>",
            "firmName": "<string>",
            "personnelFlag": "<boolean>",
            "vipFlag": "<boolean>",
            "birthDate": "<dateTime>",
            "birthPlace": "<string>",
            "workflowCode": "<string>",
            "gender": "Female",
            "dateOfDeath": "<dateTime>",
            "coreLastUpdateDate": "<dateTime>",
            "workIsMailing": "<boolean>",
            "nplFlag": "<boolean>",
            "selfCuredFlag": "<boolean>",
            "nplDate": "<dateTime>",
            "lastKrsSearchDate": "<dateTime>",
            "currentKkbScore": "<integer>",
            "creditCardUsageRate": "<double>",
            "kmhUsageRate": "<double>",
            "collectionScore": "<string>",
            "lastMonthApplicationCount": "<integer>",
            "otherBankMortgageLoanPaymentPerformance": "<string>",
            "blockageFlag": "<boolean>",
            "hepsiDpdMaxLm": "<integer>",
            "sumNumFailL3m": "<integer>",
            "tumKredilerDpdMaxMin6": "<integer>",
            "avgAsinitsBurganOverOutsV12lm": "<string>",
            "hepsiDpdMaxL12m": "<integer>",
            "hepsiDpdLm": "<integer>",
            "hepsiDpdMaxV3lm": "<string>",
            "hepsiTotalOutsV3lm": "<string>",
            "hepsiDpdAmtOutsVlm": "<string>",
            "hepsiDpdAmtOutsMax12": "<double>",
            "modelType": "<string>",
            "finalRatio": "<double>",
            "totalCashRisk": "<double>",
            "totalLimit": "<double>",
            "totalRisk": "<double>",
            "totalPursuable": "<double>",
            "minPursuable": "<double>",
            "totalAssets": "<double>",
            "totalColleteral": "<double>",
            "totalLimitUtilRatio": "<double>",
            "allMaxDpd": "<integer>",
            "engagementGuarantorInfo": "<string>"
        },
        "contactRole": "GUARANTOR",
        "contactPoint": "<string>",
        "expireDate": "<dateTime>",
        "priority": "<integer>",
        "activities": [
            {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "userId": "<long>",
                "type": "CALL_MANUAL",
                "workActionId": "<long>",
                "note": "<string>",
                "pinned": "<boolean>",
                "status": "SUCCESS",
                "uuid": "<string>",
                "resultId": "<long>",
                "result": {
                    "id": "<long>",
                    "guid": "<uuid>",
                    "isActive": "<boolean>",
                    "createDate": "<dateTime>",
                    "createUserId": "<long>",
                    "updateDate": "<dateTime>",
                    "updateUserId": "<long>",
                    "result": "<string>",
                    "subResult": "<boolean>",
                    "nextAction": "WAIT_RETRY",
                    "type": "INTERVIEW_RESULT",
                    "nextActionDelay": "<integer>",
                    "nextActionMaxTry": "<integer>"
                },
                "subResultId": "<long>",
                "subResult": {
                    "id": "<long>",
                    "guid": "<uuid>",
                    "isActive": "<boolean>",
                    "createDate": "<dateTime>",
                    "createUserId": "<long>",
                    "updateDate": "<dateTime>",
                    "updateUserId": "<long>",
                    "activityResultId": "<long>",
                    "subResult": "<string>",
                    "nextAction": "LOOK_AT_SUB",
                    "nextActionDelay": "<integer>",
                    "nextActionMaxTry": "<integer>"
                },
                "scheduleDate": "<dateTime>"
            },
            {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "userId": "<long>",
                "type": "SMS",
                "workActionId": "<long>",
                "note": "<string>",
                "pinned": "<boolean>",
                "status": "PENDING",
                "uuid": "<string>",
                "resultId": "<long>",
                "result": {
                    "id": "<long>",
                    "guid": "<uuid>",
                    "isActive": "<boolean>",
                    "createDate": "<dateTime>",
                    "createUserId": "<long>",
                    "updateDate": "<dateTime>",
                    "updateUserId": "<long>",
                    "result": "<string>",
                    "subResult": "<boolean>",
                    "nextAction": "LOOK_AT_SUB",
                    "type": "ESCALATION",
                    "nextActionDelay": "<integer>",
                    "nextActionMaxTry": "<integer>"
                },
                "subResultId": "<long>",
                "subResult": {
                    "id": "<long>",
                    "guid": "<uuid>",
                    "isActive": "<boolean>",
                    "createDate": "<dateTime>",
                    "createUserId": "<long>",
                    "updateDate": "<dateTime>",
                    "updateUserId": "<long>",
                    "activityResultId": "<long>",
                    "subResult": "<string>",
                    "nextAction": "STOP",
                    "nextActionDelay": "<integer>",
                    "nextActionMaxTry": "<integer>"
                },
                "scheduleDate": "<dateTime>"
            }
        ]
    }
}
```
</details>

---

#### **_Retrieve work actions by workList Guid_**

**GET** `/api/v3/WorkAction/GetByWorkListGuid`

#### Description

Fetches a paginated list of work actions associated with a specific worklist GUID.

##### Query Parameters

| Parameter             | Type      | Description      |
| :-------------------- | :-------- | :--------------- |
| `WorkListGuid`        | `string`  | (**_required_**) |
| `name`                | `string`  |                  |
| `IdentityNumber`      | `string`  |                  |
| `AccountNumber`       | `string`  |                  |
| `CustomerNumber`      | `integer` |                  |
| `Status`              | `string`  |                  |
| `BucketEnum`          | `string`  |                  |
| `ActivityResultId`    | `integer` |                  |
| `ActivitySubresultId` | `integer` |                  |
| `offset`              | `integer` |                  |
| `Limit`               | `integer` |                  |
| `sortBy`              | `string`  |                  |
| `sortOrder`           | `string`  |                  |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/WorkAction/GetByWorkListGuid?WorkListGuid=%3Cuuid%3E&Name=%3Cstring%3E&IdentityNumber=%3Cstring%3E&AccountNumber=%3Cstring%3E&CustomerNumber=%3Clong%3E&Status=SUCCESS&BucketEnum=B2&ActivityResultId=%3Clong%3E&ActivitySubResultId=%3Clong%3E&Offset=%3Cinteger%3E&Limit=%3Cinteger%3E&sortBy=%3Cstring%3E&sortOrder=asc" -H 'Accept: text/plain'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": [
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "status": "PROCESSING",
            "worklistId": "<long>",
            "personId": "<long>",
            "loanAccountId": "<long>",
            "template": "<string>",
            "templateParameter": "<string>",
            "contactPersonId": "<long>",
            "contactRole": "FATHER",
            "contactPoint": "<string>",
            "expireDate": "<dateTime>",
            "lastActivity": {
                "id": "<long>",
                "createDate": "<dateTime>",
                "note": "<string>",
                "type": "PUSH",
                "user": {
                    "firstName": "<string>",
                    "middleName": "<string>",
                    "lastName": "<string>"
                },
                "result": {
                    "id": "<long>",
                    "type": "INTERVIEW_RESULT",
                    "result": "<string>"
                },
                "subResult": {
                    "id": "<long>",
                    "subResult": "<string>"
                }
            },
            "leadAccount": {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "bucket": "B1",
                "leadAccountFlag": "<boolean>",
                "accountNumber": "<string>",
                "branchCode": "<integer>",
                "customerNumber": "<integer>",
                "personId": "<long>",
                "accountReference": "<string>",
                "usageDate": "<dateTime>",
                "accountSuffix": "<integer>",
                "type": "VADESIZ",
                "productCode": "<string>",
                "currencyCode": "<string>",
                "currentAccountIbanNumber": "<string>",
                "accDpd": "<integer>",
                "bucket1DueAmount": "<double>",
                "bucket1RemainingAmount": "<double>",
                "bucket1DueDate": "<dateTime>",
                "bucket2DueAmount": "<double>",
                "bucket2RemainingAmount": "<double>",
                "bucket2DueDate": "<dateTime>",
                "bucket3DueAmount": "<double>",
                "bucket3RemainingAmount": "<double>",
                "bucket3DueDate": "<dateTime>",
                "rollbackFlag": "<string>",
                "restructuredFlag": "<string>",
                "lastPaymentAmount": "<double>",
                "lastPaymentDate": "<dateTime>",
                "muacceliyetDate": "<dateTime>",
                "coreLastUpdateDate": "<dateTime>",
                "totalRemainingAmount": "<double>",
                "stagingImportId": "<long>"
            },
            "loanAccount": {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "bucket": "B0",
                "leadAccountFlag": "<boolean>",
                "accountNumber": "<string>",
                "branchCode": "<integer>",
                "customerNumber": "<integer>",
                "personId": "<long>",
                "accountReference": "<string>",
                "usageDate": "<dateTime>",
                "accountSuffix": "<integer>",
                "type": "VADELI",
                "productCode": "<string>",
                "currencyCode": "<string>",
                "currentAccountIbanNumber": "<string>",
                "accDpd": "<integer>",
                "bucket1DueAmount": "<double>",
                "bucket1RemainingAmount": "<double>",
                "bucket1DueDate": "<dateTime>",
                "bucket2DueAmount": "<double>",
                "bucket2RemainingAmount": "<double>",
                "bucket2DueDate": "<dateTime>",
                "bucket3DueAmount": "<double>",
                "bucket3RemainingAmount": "<double>",
                "bucket3DueDate": "<dateTime>",
                "rollbackFlag": "<string>",
                "restructuredFlag": "<string>",
                "lastPaymentAmount": "<double>",
                "lastPaymentDate": "<dateTime>",
                "muacceliyetDate": "<dateTime>",
                "coreLastUpdateDate": "<dateTime>",
                "totalRemainingAmount": "<double>",
                "stagingImportId": "<long>"
            },
            "person": {
                "segment": "<string>",
                "relationType": "ATTORNEY",
                "identityNumber": "<string>",
                "name": "<string>",
                "middleName": "<string>",
                "surname": "<string>",
                "firmName": "<string>",
                "guid": "<uuid>",
                "phoneNumbers": [
                    {
                        "id": "<long>",
                        "guid": "<uuid>",
                        "isActive": "<boolean>",
                        "createDate": "<dateTime>",
                        "createUserId": "<long>",
                        "updateDate": "<dateTime>",
                        "updateUserId": "<long>",
                        "phoneNumberText": "<string>",
                        "type": "Mobile",
                        "name": "<string>",
                        "isDefault": "<boolean>",
                        "personId": "<long>",
                        "lastSuccessfulCallDate": "<dateTime>"
                    },
                    {
                        "id": "<long>",
                        "guid": "<uuid>",
                        "isActive": "<boolean>",
                        "createDate": "<dateTime>",
                        "createUserId": "<long>",
                        "updateDate": "<dateTime>",
                        "updateUserId": "<long>",
                        "phoneNumberText": "<string>",
                        "type": "Mobile",
                        "name": "<string>",
                        "isDefault": "<boolean>",
                        "personId": "<long>",
                        "lastSuccessfulCallDate": "<dateTime>"
                    }
                ]
            },
            "worklist": {
                "name": "<string>",
                "type": "MANUAL",
                "guid": "<uuid>"
            }
        },
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "status": "SUCCESS",
            "worklistId": "<long>",
            "personId": "<long>",
            "loanAccountId": "<long>",
            "template": "<string>",
            "templateParameter": "<string>",
            "contactPersonId": "<long>",
            "contactRole": "MOTHER",
            "contactPoint": "<string>",
            "expireDate": "<dateTime>",
            "lastActivity": {
                "id": "<long>",
                "createDate": "<dateTime>",
                "note": "<string>",
                "type": "EMAIL",
                "user": {
                    "firstName": "<string>",
                    "middleName": "<string>",
                    "lastName": "<string>"
                },
                "result": {
                    "id": "<long>",
                    "type": "CALL_RESULT",
                    "result": "<string>"
                },
                "subResult": {
                    "id": "<long>",
                    "subResult": "<string>"
                }
            },
            "leadAccount": {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "bucket": "B2",
                "leadAccountFlag": "<boolean>",
                "accountNumber": "<string>",
                "branchCode": "<integer>",
                "customerNumber": "<integer>",
                "personId": "<long>",
                "accountReference": "<string>",
                "usageDate": "<dateTime>",
                "accountSuffix": "<integer>",
                "type": "IHTIYAC_KREDISI",
                "productCode": "<string>",
                "currencyCode": "<string>",
                "currentAccountIbanNumber": "<string>",
                "accDpd": "<integer>",
                "bucket1DueAmount": "<double>",
                "bucket1RemainingAmount": "<double>",
                "bucket1DueDate": "<dateTime>",
                "bucket2DueAmount": "<double>",
                "bucket2RemainingAmount": "<double>",
                "bucket2DueDate": "<dateTime>",
                "bucket3DueAmount": "<double>",
                "bucket3RemainingAmount": "<double>",
                "bucket3DueDate": "<dateTime>",
                "rollbackFlag": "<string>",
                "restructuredFlag": "<string>",
                "lastPaymentAmount": "<double>",
                "lastPaymentDate": "<dateTime>",
                "muacceliyetDate": "<dateTime>",
                "coreLastUpdateDate": "<dateTime>",
                "totalRemainingAmount": "<double>",
                "stagingImportId": "<long>"
            },
            "loanAccount": {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "bucket": "B0",
                "leadAccountFlag": "<boolean>",
                "accountNumber": "<string>",
                "branchCode": "<integer>",
                "customerNumber": "<integer>",
                "personId": "<long>",
                "accountReference": "<string>",
                "usageDate": "<dateTime>",
                "accountSuffix": "<integer>",
                "type": "TASIT_KREDISI",
                "productCode": "<string>",
                "currencyCode": "<string>",
                "currentAccountIbanNumber": "<string>",
                "accDpd": "<integer>",
                "bucket1DueAmount": "<double>",
                "bucket1RemainingAmount": "<double>",
                "bucket1DueDate": "<dateTime>",
                "bucket2DueAmount": "<double>",
                "bucket2RemainingAmount": "<double>",
                "bucket2DueDate": "<dateTime>",
                "bucket3DueAmount": "<double>",
                "bucket3RemainingAmount": "<double>",
                "bucket3DueDate": "<dateTime>",
                "rollbackFlag": "<string>",
                "restructuredFlag": "<string>",
                "lastPaymentAmount": "<double>",
                "lastPaymentDate": "<dateTime>",
                "muacceliyetDate": "<dateTime>",
                "coreLastUpdateDate": "<dateTime>",
                "totalRemainingAmount": "<double>",
                "stagingImportId": "<long>"
            },
            "person": {
                "segment": "<string>",
                "relationType": "CHILD",
                "identityNumber": "<string>",
                "name": "<string>",
                "middleName": "<string>",
                "surname": "<string>",
                "firmName": "<string>",
                "guid": "<uuid>",
                "phoneNumbers": [
                    {
                        "id": "<long>",
                        "guid": "<uuid>",
                        "isActive": "<boolean>",
                        "createDate": "<dateTime>",
                        "createUserId": "<long>",
                        "updateDate": "<dateTime>",
                        "updateUserId": "<long>",
                        "phoneNumberText": "<string>",
                        "type": "Mobile",
                        "name": "<string>",
                        "isDefault": "<boolean>",
                        "personId": "<long>",
                        "lastSuccessfulCallDate": "<dateTime>"
                    },
                    {
                        "id": "<long>",
                        "guid": "<uuid>",
                        "isActive": "<boolean>",
                        "createDate": "<dateTime>",
                        "createUserId": "<long>",
                        "updateDate": "<dateTime>",
                        "updateUserId": "<long>",
                        "phoneNumberText": "<string>",
                        "type": "Home",
                        "name": "<string>",
                        "isDefault": "<boolean>",
                        "personId": "<long>",
                        "lastSuccessfulCallDate": "<dateTime>"
                    }
                ]
            },
            "worklist": {
                "name": "<string>",
                "type": "CALL",
                "guid": "<uuid>"
            }
        }
    ],
    "totalRowCount": "<integer>",
    "totalPageCount": "<integer>",
    "offset": "<integer>",
    "limit": "<integer>"
}
```
</details>

---

#### **_Retrieve work actions by Person Guid and Date_**

**GET** `/api/v3/WorkAction/GetByPersonGuidAndDate`

#### Description

Fetches a list of work actions associated with a specific worklist GUID.

##### Query Parameters

| Parameter           | Type     | Description      |
| :------------------ | :------- | :--------------- |
| `personGuid`        | `guid`   | (**_required_**) |
| `startDate`         | `string` |                  |
| `loanAccountNumber` | `string` |                  |
| `endDate`           | `string` |                  |
| `sortBy`            | `string` |                  |
| `sortOrder`         | `string` |                  |
| `workListType`      | `string` |                  |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/WorkAction/GetByPersonGuidAndDate?personGuid=%3Cuuid%3E&startDate=%3CdateTime%3E&loanAccountNumber=%3Cstring%3E&endDate=%3CdateTime%3E&sortBy=%3Cstring%3E&sortOrder=asc&worklistType=NO_ACTION" -H 'Accept: text/plain'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": [
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "status": "PENDING",
            "worklistId": "<long>",
            "personId": "<long>",
            "loanAccountId": "<long>",
            "template": "<string>",
            "templateParameter": "<string>",
            "contactPersonId": "<long>",
            "contactRole": "OTHER",
            "contactPoint": "<string>",
            "expireDate": "<dateTime>",
            "lastActivity": {
                "id": "<long>",
                "createDate": "<dateTime>",
                "note": "<string>",
                "type": "PUSH",
                "user": {
                    "firstName": "<string>",
                    "middleName": "<string>",
                    "lastName": "<string>"
                },
                "result": {
                    "id": "<long>",
                    "type": "ESCALATION",
                    "result": "<string>"
                },
                "subResult": {
                    "id": "<long>",
                    "subResult": "<string>"
                }
            },
            "leadAccount": {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "bucket": "B3",
                "leadAccountFlag": "<boolean>",
                "accountNumber": "<string>",
                "branchCode": "<integer>",
                "customerNumber": "<integer>",
                "personId": "<long>",
                "accountReference": "<string>",
                "usageDate": "<dateTime>",
                "accountSuffix": "<integer>",
                "type": "Y_YAPILANRIMA_KONUT",
                "productCode": "<string>",
                "currencyCode": "<string>",
                "currentAccountIbanNumber": "<string>",
                "accDpd": "<integer>",
                "bucket1DueAmount": "<double>",
                "bucket1RemainingAmount": "<double>",
                "bucket1DueDate": "<dateTime>",
                "bucket2DueAmount": "<double>",
                "bucket2RemainingAmount": "<double>",
                "bucket2DueDate": "<dateTime>",
                "bucket3DueAmount": "<double>",
                "bucket3RemainingAmount": "<double>",
                "bucket3DueDate": "<dateTime>",
                "rollbackFlag": "<string>",
                "restructuredFlag": "<string>",
                "lastPaymentAmount": "<double>",
                "lastPaymentDate": "<dateTime>",
                "muacceliyetDate": "<dateTime>",
                "coreLastUpdateDate": "<dateTime>",
                "totalRemainingAmount": "<double>",
                "stagingImportId": "<long>"
            },
            "loanAccount": {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "bucket": "B1",
                "leadAccountFlag": "<boolean>",
                "accountNumber": "<string>",
                "branchCode": "<integer>",
                "customerNumber": "<integer>",
                "personId": "<long>",
                "accountReference": "<string>",
                "usageDate": "<dateTime>",
                "accountSuffix": "<integer>",
                "type": "Y_YAPILANRIMA_KMH",
                "productCode": "<string>",
                "currencyCode": "<string>",
                "currentAccountIbanNumber": "<string>",
                "accDpd": "<integer>",
                "bucket1DueAmount": "<double>",
                "bucket1RemainingAmount": "<double>",
                "bucket1DueDate": "<dateTime>",
                "bucket2DueAmount": "<double>",
                "bucket2RemainingAmount": "<double>",
                "bucket2DueDate": "<dateTime>",
                "bucket3DueAmount": "<double>",
                "bucket3RemainingAmount": "<double>",
                "bucket3DueDate": "<dateTime>",
                "rollbackFlag": "<string>",
                "restructuredFlag": "<string>",
                "lastPaymentAmount": "<double>",
                "lastPaymentDate": "<dateTime>",
                "muacceliyetDate": "<dateTime>",
                "coreLastUpdateDate": "<dateTime>",
                "totalRemainingAmount": "<double>",
                "stagingImportId": "<long>"
            },
            "person": {
                "segment": "<string>",
                "relationType": "GUARDIAN",
                "identityNumber": "<string>",
                "name": "<string>",
                "middleName": "<string>",
                "surname": "<string>",
                "firmName": "<string>",
                "guid": "<uuid>",
                "phoneNumbers": [
                    {
                        "id": "<long>",
                        "guid": "<uuid>",
                        "isActive": "<boolean>",
                        "createDate": "<dateTime>",
                        "createUserId": "<long>",
                        "updateDate": "<dateTime>",
                        "updateUserId": "<long>",
                        "phoneNumberText": "<string>",
                        "type": "MobileSms",
                        "name": "<string>",
                        "isDefault": "<boolean>",
                        "personId": "<long>",
                        "lastSuccessfulCallDate": "<dateTime>"
                    },
                    {
                        "id": "<long>",
                        "guid": "<uuid>",
                        "isActive": "<boolean>",
                        "createDate": "<dateTime>",
                        "createUserId": "<long>",
                        "updateDate": "<dateTime>",
                        "updateUserId": "<long>",
                        "phoneNumberText": "<string>",
                        "type": "Work",
                        "name": "<string>",
                        "isDefault": "<boolean>",
                        "personId": "<long>",
                        "lastSuccessfulCallDate": "<dateTime>"
                    }
                ]
            },
            "worklist": {
                "name": "<string>",
                "type": "MANUAL",
                "guid": "<uuid>"
            }
        },
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "status": "FAILED",
            "worklistId": "<long>",
            "personId": "<long>",
            "loanAccountId": "<long>",
            "template": "<string>",
            "templateParameter": "<string>",
            "contactPersonId": "<long>",
            "contactRole": "RELATIVE",
            "contactPoint": "<string>",
            "expireDate": "<dateTime>",
            "lastActivity": {
                "id": "<long>",
                "createDate": "<dateTime>",
                "note": "<string>",
                "type": "CALL_MANUAL",
                "user": {
                    "firstName": "<string>",
                    "middleName": "<string>",
                    "lastName": "<string>"
                },
                "result": {
                    "id": "<long>",
                    "type": "SCHEDULE",
                    "result": "<string>"
                },
                "subResult": {
                    "id": "<long>",
                    "subResult": "<string>"
                }
            },
            "leadAccount": {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "bucket": "B4",
                "leadAccountFlag": "<boolean>",
                "accountNumber": "<string>",
                "branchCode": "<integer>",
                "customerNumber": "<integer>",
                "personId": "<long>",
                "accountReference": "<string>",
                "usageDate": "<dateTime>",
                "accountSuffix": "<integer>",
                "type": "ZARAR_NITELIKLI_ALACAK",
                "productCode": "<string>",
                "currencyCode": "<string>",
                "currentAccountIbanNumber": "<string>",
                "accDpd": "<integer>",
                "bucket1DueAmount": "<double>",
                "bucket1RemainingAmount": "<double>",
                "bucket1DueDate": "<dateTime>",
                "bucket2DueAmount": "<double>",
                "bucket2RemainingAmount": "<double>",
                "bucket2DueDate": "<dateTime>",
                "bucket3DueAmount": "<double>",
                "bucket3RemainingAmount": "<double>",
                "bucket3DueDate": "<dateTime>",
                "rollbackFlag": "<string>",
                "restructuredFlag": "<string>",
                "lastPaymentAmount": "<double>",
                "lastPaymentDate": "<dateTime>",
                "muacceliyetDate": "<dateTime>",
                "coreLastUpdateDate": "<dateTime>",
                "totalRemainingAmount": "<double>",
                "stagingImportId": "<long>"
            },
            "loanAccount": {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "bucket": "B1",
                "leadAccountFlag": "<boolean>",
                "accountNumber": "<string>",
                "branchCode": "<integer>",
                "customerNumber": "<integer>",
                "personId": "<long>",
                "accountReference": "<string>",
                "usageDate": "<dateTime>",
                "accountSuffix": "<integer>",
                "type": "ZARAR_NITELIKLI_ALACAK",
                "productCode": "<string>",
                "currencyCode": "<string>",
                "currentAccountIbanNumber": "<string>",
                "accDpd": "<integer>",
                "bucket1DueAmount": "<double>",
                "bucket1RemainingAmount": "<double>",
                "bucket1DueDate": "<dateTime>",
                "bucket2DueAmount": "<double>",
                "bucket2RemainingAmount": "<double>",
                "bucket2DueDate": "<dateTime>",
                "bucket3DueAmount": "<double>",
                "bucket3RemainingAmount": "<double>",
                "bucket3DueDate": "<dateTime>",
                "rollbackFlag": "<string>",
                "restructuredFlag": "<string>",
                "lastPaymentAmount": "<double>",
                "lastPaymentDate": "<dateTime>",
                "muacceliyetDate": "<dateTime>",
                "coreLastUpdateDate": "<dateTime>",
                "totalRemainingAmount": "<double>",
                "stagingImportId": "<long>"
            },
            "person": {
                "segment": "<string>",
                "relationType": "SPOUSE",
                "identityNumber": "<string>",
                "name": "<string>",
                "middleName": "<string>",
                "surname": "<string>",
                "firmName": "<string>",
                "guid": "<uuid>",
                "phoneNumbers": [
                    {
                        "id": "<long>",
                        "guid": "<uuid>",
                        "isActive": "<boolean>",
                        "createDate": "<dateTime>",
                        "createUserId": "<long>",
                        "updateDate": "<dateTime>",
                        "updateUserId": "<long>",
                        "phoneNumberText": "<string>",
                        "type": "Home",
                        "name": "<string>",
                        "isDefault": "<boolean>",
                        "personId": "<long>",
                        "lastSuccessfulCallDate": "<dateTime>"
                    },
                    {
                        "id": "<long>",
                        "guid": "<uuid>",
                        "isActive": "<boolean>",
                        "createDate": "<dateTime>",
                        "createUserId": "<long>",
                        "updateDate": "<dateTime>",
                        "updateUserId": "<long>",
                        "phoneNumberText": "<string>",
                        "type": "Fax",
                        "name": "<string>",
                        "isDefault": "<boolean>",
                        "personId": "<long>",
                        "lastSuccessfulCallDate": "<dateTime>"
                    }
                ]
            },
            "worklist": {
                "name": "<string>",
                "type": "MANUAL",
                "guid": "<uuid>"
            }
        }
    ]
}
```
</details>

---

#### **_Retrieve work actions by Person Guid and Date and Grouped with(Person, Account, Worklist.Type, Date.Day)_**

**GET** `/api/v3/WorkAction/GetByPersonGuidAndDateGroupBy`

#### Description

Returns a list of work actions associated with a given Person GUID, grouped by Date, Person, Account, and worklist.Type.

##### Query Parameters

| Parameter           | Type     | Description      |
| :------------------ | :------- | :--------------- |
| `personGuid`        | `guid`   | (**_required_**) |
| `startDate`         | `string` |                  |
| `loanAccountNumber` | `string` |                  |
| `endDate`           | `string` |                  |
| `sortBy`            | `string` |                  |
| `sortOrder`         | `string` |                  |
| `workListType`      | `string` |                  |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/WorkAction/GetByPersonGuidAndDateGroupBy?personGuid=%3Cuuid%3E&startDate=%3CdateTime%3E&loanAccountNumber=%3Cstring%3E&endDate=%3CdateTime%3E&sortBy=%3Cstring%3E&sortOrder=asc&worklistType=NO_ACTION" -H 'Accept: text/plain'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": [
        {
            "status": "PROCESSING",
            "template": "<string>",
            "templateParameter": "<string>",
            "contactRole": "GUARANTOR",
            "contactPoint": "<string>",
            "expireDate": "<dateTime>",
            "createDate": "<dateTime>",
            "worklist": {
                "name": "<string>",
                "type": "EMAIL",
                "guid": "<uuid>"
            },
            "loanAccount": {
                "guid": "<uuid>",
                "accountNumber": "<string>",
                "type": "IHTIYAC_KREDISI"
            }
        },
        {
            "status": "FAILED",
            "template": "<string>",
            "templateParameter": "<string>",
            "contactRole": "FATHER",
            "contactPoint": "<string>",
            "expireDate": "<dateTime>",
            "createDate": "<dateTime>",
            "worklist": {
                "name": "<string>",
                "type": "NO_ACTION",
                "guid": "<uuid>"
            },
            "loanAccount": {
                "guid": "<uuid>",
                "accountNumber": "<string>",
                "type": "OZEL_KARSILIK"
            }
        }
    ]
}
```
</details>

---

#### **_Retrieve work actions by Person Guid_**

**GET** `/api/v3/WorkAction/GetByPersonGuid`

#### Description

Fetches a paginated list of work actions associated with a specific person's GUID.

##### Query Parameters

| Parameter   | Type      | Description      |
| :---------- | :-------- | :--------------- |
| `guid`      | `guid`    | (**_required_**) |
| `offset`    | `integer` |                  |
| `Limit`     | `integer` |                  |
| `sortBy`    | `string`  |                  |
| `sortOrder` | `string`  |                  |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/WorkAction/GetByPersonGuid?guid=%3Cuuid%3E&Offset=%3Cinteger%3E&Limit=%3Cinteger%3E&sortBy=%3Cstring%3E&sortOrder=asc" -H 'Accept: text/plain'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": [
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "status": "PROCESSING",
            "worklistId": "<long>",
            "personId": "<long>",
            "loanAccountId": "<long>",
            "template": "<string>",
            "templateParameter": "<string>",
            "contactPersonId": "<long>",
            "contactRole": "FATHER",
            "contactPoint": "<string>",
            "expireDate": "<dateTime>",
            "lastActivity": {
                "id": "<long>",
                "createDate": "<dateTime>",
                "note": "<string>",
                "type": "PUSH",
                "user": {
                    "firstName": "<string>",
                    "middleName": "<string>",
                    "lastName": "<string>"
                },
                "result": {
                    "id": "<long>",
                    "type": "INTERVIEW_RESULT",
                    "result": "<string>"
                },
                "subResult": {
                    "id": "<long>",
                    "subResult": "<string>"
                }
            },
            "leadAccount": {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "bucket": "B1",
                "leadAccountFlag": "<boolean>",
                "accountNumber": "<string>",
                "branchCode": "<integer>",
                "customerNumber": "<integer>",
                "personId": "<long>",
                "accountReference": "<string>",
                "usageDate": "<dateTime>",
                "accountSuffix": "<integer>",
                "type": "VADESIZ",
                "productCode": "<string>",
                "currencyCode": "<string>",
                "currentAccountIbanNumber": "<string>",
                "accDpd": "<integer>",
                "bucket1DueAmount": "<double>",
                "bucket1RemainingAmount": "<double>",
                "bucket1DueDate": "<dateTime>",
                "bucket2DueAmount": "<double>",
                "bucket2RemainingAmount": "<double>",
                "bucket2DueDate": "<dateTime>",
                "bucket3DueAmount": "<double>",
                "bucket3RemainingAmount": "<double>",
                "bucket3DueDate": "<dateTime>",
                "rollbackFlag": "<string>",
                "restructuredFlag": "<string>",
                "lastPaymentAmount": "<double>",
                "lastPaymentDate": "<dateTime>",
                "muacceliyetDate": "<dateTime>",
                "coreLastUpdateDate": "<dateTime>",
                "totalRemainingAmount": "<double>",
                "stagingImportId": "<long>"
            },
            "loanAccount": {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "bucket": "B0",
                "leadAccountFlag": "<boolean>",
                "accountNumber": "<string>",
                "branchCode": "<integer>",
                "customerNumber": "<integer>",
                "personId": "<long>",
                "accountReference": "<string>",
                "usageDate": "<dateTime>",
                "accountSuffix": "<integer>",
                "type": "VADELI",
                "productCode": "<string>",
                "currencyCode": "<string>",
                "currentAccountIbanNumber": "<string>",
                "accDpd": "<integer>",
                "bucket1DueAmount": "<double>",
                "bucket1RemainingAmount": "<double>",
                "bucket1DueDate": "<dateTime>",
                "bucket2DueAmount": "<double>",
                "bucket2RemainingAmount": "<double>",
                "bucket2DueDate": "<dateTime>",
                "bucket3DueAmount": "<double>",
                "bucket3RemainingAmount": "<double>",
                "bucket3DueDate": "<dateTime>",
                "rollbackFlag": "<string>",
                "restructuredFlag": "<string>",
                "lastPaymentAmount": "<double>",
                "lastPaymentDate": "<dateTime>",
                "muacceliyetDate": "<dateTime>",
                "coreLastUpdateDate": "<dateTime>",
                "totalRemainingAmount": "<double>",
                "stagingImportId": "<long>"
            },
            "person": {
                "segment": "<string>",
                "relationType": "ATTORNEY",
                "identityNumber": "<string>",
                "name": "<string>",
                "middleName": "<string>",
                "surname": "<string>",
                "firmName": "<string>",
                "guid": "<uuid>",
                "phoneNumbers": [
                    {
                        "id": "<long>",
                        "guid": "<uuid>",
                        "isActive": "<boolean>",
                        "createDate": "<dateTime>",
                        "createUserId": "<long>",
                        "updateDate": "<dateTime>",
                        "updateUserId": "<long>",
                        "phoneNumberText": "<string>",
                        "type": "Mobile",
                        "name": "<string>",
                        "isDefault": "<boolean>",
                        "personId": "<long>",
                        "lastSuccessfulCallDate": "<dateTime>"
                    },
                    {
                        "id": "<long>",
                        "guid": "<uuid>",
                        "isActive": "<boolean>",
                        "createDate": "<dateTime>",
                        "createUserId": "<long>",
                        "updateDate": "<dateTime>",
                        "updateUserId": "<long>",
                        "phoneNumberText": "<string>",
                        "type": "Mobile",
                        "name": "<string>",
                        "isDefault": "<boolean>",
                        "personId": "<long>",
                        "lastSuccessfulCallDate": "<dateTime>"
                    }
                ]
            },
            "worklist": {
                "name": "<string>",
                "type": "MANUAL",
                "guid": "<uuid>"
            }
        },
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "status": "SUCCESS",
            "worklistId": "<long>",
            "personId": "<long>",
            "loanAccountId": "<long>",
            "template": "<string>",
            "templateParameter": "<string>",
            "contactPersonId": "<long>",
            "contactRole": "MOTHER",
            "contactPoint": "<string>",
            "expireDate": "<dateTime>",
            "lastActivity": {
                "id": "<long>",
                "createDate": "<dateTime>",
                "note": "<string>",
                "type": "EMAIL",
                "user": {
                    "firstName": "<string>",
                    "middleName": "<string>",
                    "lastName": "<string>"
                },
                "result": {
                    "id": "<long>",
                    "type": "CALL_RESULT",
                    "result": "<string>"
                },
                "subResult": {
                    "id": "<long>",
                    "subResult": "<string>"
                }
            },
            "leadAccount": {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "bucket": "B2",
                "leadAccountFlag": "<boolean>",
                "accountNumber": "<string>",
                "branchCode": "<integer>",
                "customerNumber": "<integer>",
                "personId": "<long>",
                "accountReference": "<string>",
                "usageDate": "<dateTime>",
                "accountSuffix": "<integer>",
                "type": "IHTIYAC_KREDISI",
                "productCode": "<string>",
                "currencyCode": "<string>",
                "currentAccountIbanNumber": "<string>",
                "accDpd": "<integer>",
                "bucket1DueAmount": "<double>",
                "bucket1RemainingAmount": "<double>",
                "bucket1DueDate": "<dateTime>",
                "bucket2DueAmount": "<double>",
                "bucket2RemainingAmount": "<double>",
                "bucket2DueDate": "<dateTime>",
                "bucket3DueAmount": "<double>",
                "bucket3RemainingAmount": "<double>",
                "bucket3DueDate": "<dateTime>",
                "rollbackFlag": "<string>",
                "restructuredFlag": "<string>",
                "lastPaymentAmount": "<double>",
                "lastPaymentDate": "<dateTime>",
                "muacceliyetDate": "<dateTime>",
                "coreLastUpdateDate": "<dateTime>",
                "totalRemainingAmount": "<double>",
                "stagingImportId": "<long>"
            },
            "loanAccount": {
                "id": "<long>",
                "guid": "<uuid>",
                "isActive": "<boolean>",
                "createDate": "<dateTime>",
                "createUserId": "<long>",
                "updateDate": "<dateTime>",
                "updateUserId": "<long>",
                "bucket": "B0",
                "leadAccountFlag": "<boolean>",
                "accountNumber": "<string>",
                "branchCode": "<integer>",
                "customerNumber": "<integer>",
                "personId": "<long>",
                "accountReference": "<string>",
                "usageDate": "<dateTime>",
                "accountSuffix": "<integer>",
                "type": "TASIT_KREDISI",
                "productCode": "<string>",
                "currencyCode": "<string>",
                "currentAccountIbanNumber": "<string>",
                "accDpd": "<integer>",
                "bucket1DueAmount": "<double>",
                "bucket1RemainingAmount": "<double>",
                "bucket1DueDate": "<dateTime>",
                "bucket2DueAmount": "<double>",
                "bucket2RemainingAmount": "<double>",
                "bucket2DueDate": "<dateTime>",
                "bucket3DueAmount": "<double>",
                "bucket3RemainingAmount": "<double>",
                "bucket3DueDate": "<dateTime>",
                "rollbackFlag": "<string>",
                "restructuredFlag": "<string>",
                "lastPaymentAmount": "<double>",
                "lastPaymentDate": "<dateTime>",
                "muacceliyetDate": "<dateTime>",
                "coreLastUpdateDate": "<dateTime>",
                "totalRemainingAmount": "<double>",
                "stagingImportId": "<long>"
            },
            "person": {
                "segment": "<string>",
                "relationType": "CHILD",
                "identityNumber": "<string>",
                "name": "<string>",
                "middleName": "<string>",
                "surname": "<string>",
                "firmName": "<string>",
                "guid": "<uuid>",
                "phoneNumbers": [
                    {
                        "id": "<long>",
                        "guid": "<uuid>",
                        "isActive": "<boolean>",
                        "createDate": "<dateTime>",
                        "createUserId": "<long>",
                        "updateDate": "<dateTime>",
                        "updateUserId": "<long>",
                        "phoneNumberText": "<string>",
                        "type": "Mobile",
                        "name": "<string>",
                        "isDefault": "<boolean>",
                        "personId": "<long>",
                        "lastSuccessfulCallDate": "<dateTime>"
                    },
                    {
                        "id": "<long>",
                        "guid": "<uuid>",
                        "isActive": "<boolean>",
                        "createDate": "<dateTime>",
                        "createUserId": "<long>",
                        "updateDate": "<dateTime>",
                        "updateUserId": "<long>",
                        "phoneNumberText": "<string>",
                        "type": "Home",
                        "name": "<string>",
                        "isDefault": "<boolean>",
                        "personId": "<long>",
                        "lastSuccessfulCallDate": "<dateTime>"
                    }
                ]
            },
            "worklist": {
                "name": "<string>",
                "type": "CALL",
                "guid": "<uuid>"
            }
        }
    ],
    "totalRowCount": "<integer>",
    "totalPageCount": "<integer>",
    "offset": "<integer>",
    "limit": "<integer>"
}
```
</details>

---

#### **_Retrieve work actions by LoanAccount Guid_**

**GET** `/api/v3/WorkAction/GetByLoanAccountGuid`

#### Description

Fetches a paginated list of work actions linked to a specific loan account GUID.

##### Query Parameters

| Parameter   | Type      | Description      |
| :---------- | :-------- | :--------------- |
| `guid`      | `guid`    | (**_required_**) |
| `offset`    | `integer` |                  |
| `Limit`     | `integer` |                  |
| `sortBy`    | `string`  |                  |
| `sortOrder` | `string`  |                  |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/WorkAction/GetByLoanAccountGuid?guid=%3Cuuid%3E&Offset=%3Cinteger%3E&Limit=%3Cinteger%3E&sortBy=%3Cstring%3E&sortOrder=asc" -H 'Accept: text/plain'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": [
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "status": "PROCESSING",
            "worklistId": "<long>",
            "personId": "<long>",
            "loanAccountId": "<long>",
            "template": "<string>",
            "templateParameter": "<string>",
            "contactPersonId": "<long>",
            "contactRole": "OWNER",
            "contactPoint": "<string>",
            "expireDate": "<dateTime>"
        },
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "status": "SUCCESS",
            "worklistId": "<long>",
            "personId": "<long>",
            "loanAccountId": "<long>",
            "template": "<string>",
            "templateParameter": "<string>",
            "contactPersonId": "<long>",
            "contactRole": "GUARDIAN",
            "contactPoint": "<string>",
            "expireDate": "<dateTime>"
        }
    ],
    "totalRowCount": "<integer>",
    "totalPageCount": "<integer>",
    "offset": "<integer>",
    "limit": "<integer>"
}
```
</details>

---

#### **_Retrieve work actions by User with userIdentityNumber_**

**GET** `/api/v3/WorkAction/GetByUserIdentityNumber`

#### Description

Fetches a paginated list of work actions linked to a specific user's userId.

##### Query Parameters

| Parameter             | Type      | Description      |
| :-------------------- | :-------- | :--------------- |
| `userIdentityNumber`  | `string`  | (**_required_**) |
| `name`                | `string`  |                  |
| `IdentityNumber`      | `string`  |                  |
| `AccountNumber`       | `string`  |                  |
| `CustomerNumber`      | `integer` |                  |
| `workListGuid`        | `string`  |                  |
| `Status`              | `string`  |                  |
| `BucketEnum`          | `string`  |                  |
| `ActivityResultId`    | `integer` |                  |
| `ActivitySubresultId` | `integer` |                  |
| `offset`              | `integer` |                  |
| `Limit`               | `integer` |                  |
| `sortBy`              | `string`  |                  |
| `sortOrder`           | `string`  |                  |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/WorkAction/GetByUserIdentityNumber?userIdentityNumber=%3Cstring%3E&Name=%3Cstring%3E&IdentityNumber=%3Cstring%3E&AccountNumber=%3Cstring%3E&CustomerNumber=%3Clong%3E&WorkListGuid=%3Cstring%3E&Status=SUCCESS&BucketEnum=B2&ActivityResultId=%3Clong%3E&ActivitySubResultId=%3Clong%3E&Offset=%3Cinteger%3E&Limit=%3Cinteger%3E&sortBy=%3Cstring%3E&sortOrder=asc" -H 'Accept: text/plain'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": [
        {
            "status": "SUCCESS",
            "worklistId": "<long>",
            "worklist": {
                "name": "<string>",
                "type": "SMS",
                "guid": "<uuid>"
            },
            "personId": "<long>",
            "person": {
                "segment": "<string>",
                "relationType": "MOTHER",
                "identityNumber": "<string>",
                "name": "<string>",
                "middleName": "<string>",
                "surname": "<string>",
                "firmName": "<string>",
                "guid": "<uuid>",
                "phoneNumbers": [
                    {
                        "id": "<long>",
                        "guid": "<uuid>",
                        "isActive": "<boolean>",
                        "createDate": "<dateTime>",
                        "createUserId": "<long>",
                        "updateDate": "<dateTime>",
                        "updateUserId": "<long>",
                        "phoneNumberText": "<string>",
                        "type": "Work",
                        "name": "<string>",
                        "isDefault": "<boolean>",
                        "personId": "<long>",
                        "lastSuccessfulCallDate": "<dateTime>"
                    },
                    {
                        "id": "<long>",
                        "guid": "<uuid>",
                        "isActive": "<boolean>",
                        "createDate": "<dateTime>",
                        "createUserId": "<long>",
                        "updateDate": "<dateTime>",
                        "updateUserId": "<long>",
                        "phoneNumberText": "<string>",
                        "type": "Fax",
                        "name": "<string>",
                        "isDefault": "<boolean>",
                        "personId": "<long>",
                        "lastSuccessfulCallDate": "<dateTime>"
                    }
                ]
            },
            "loanAccountId": "<long>",
            "loanAccount": {
                "guid": "<uuid>",
                "accountNumber": "<string>",
                "type": "KONUT_KREDISI"
            },
            "lastActivity": {
                "id": "<long>",
                "createDate": "<dateTime>",
                "note": "<string>",
                "type": "MEMO",
                "user": {
                    "firstName": "<string>",
                    "middleName": "<string>",
                    "lastName": "<string>"
                },
                "result": {
                    "id": "<long>",
                    "type": "CALL_RESULT",
                    "result": "<string>"
                },
                "subResult": {
                    "id": "<long>",
                    "subResult": "<string>"
                }
            },
            "id": "<long>",
            "guid": "<uuid>"
        },
        {
            "status": "SUCCESS",
            "worklistId": "<long>",
            "worklist": {
                "name": "<string>",
                "type": "MANUAL",
                "guid": "<uuid>"
            },
            "personId": "<long>",
            "person": {
                "segment": "<string>",
                "relationType": "SPOUSE",
                "identityNumber": "<string>",
                "name": "<string>",
                "middleName": "<string>",
                "surname": "<string>",
                "firmName": "<string>",
                "guid": "<uuid>",
                "phoneNumbers": [
                    {
                        "id": "<long>",
                        "guid": "<uuid>",
                        "isActive": "<boolean>",
                        "createDate": "<dateTime>",
                        "createUserId": "<long>",
                        "updateDate": "<dateTime>",
                        "updateUserId": "<long>",
                        "phoneNumberText": "<string>",
                        "type": "Other",
                        "name": "<string>",
                        "isDefault": "<boolean>",
                        "personId": "<long>",
                        "lastSuccessfulCallDate": "<dateTime>"
                    },
                    {
                        "id": "<long>",
                        "guid": "<uuid>",
                        "isActive": "<boolean>",
                        "createDate": "<dateTime>",
                        "createUserId": "<long>",
                        "updateDate": "<dateTime>",
                        "updateUserId": "<long>",
                        "phoneNumberText": "<string>",
                        "type": "Other",
                        "name": "<string>",
                        "isDefault": "<boolean>",
                        "personId": "<long>",
                        "lastSuccessfulCallDate": "<dateTime>"
                    }
                ]
            },
            "loanAccountId": "<long>",
            "loanAccount": {
                "guid": "<uuid>",
                "accountNumber": "<string>",
                "type": "VADESIZ"
            },
            "lastActivity": {
                "id": "<long>",
                "createDate": "<dateTime>",
                "note": "<string>",
                "type": "EMAIL",
                "user": {
                    "firstName": "<string>",
                    "middleName": "<string>",
                    "lastName": "<string>"
                },
                "result": {
                    "id": "<long>",
                    "type": "ESCALATION",
                    "result": "<string>"
                },
                "subResult": {
                    "id": "<long>",
                    "subResult": "<string>"
                }
            },
            "id": "<long>",
            "guid": "<uuid>"
        }
    ],
    "totalRowCount": "<integer>",
    "totalPageCount": "<integer>",
    "offset": "<integer>",
    "limit": "<integer>"
}
```
</details>

---

#### **_Retrieve a work action by Person.CustomerNumber. Rule: Should be WorklistType.CALL, descending WorkAction.CreateDate_**

**GET** `/api/v3/WorkAction/GetWorkActionByPersonCustomerNumber`

#### Description

Fetches a list of work actions associated with a specific Person.CustomerNumber

##### Query Parameters

| Parameter        | Type      | Description      |
| :--------------- | :-------- | :--------------- |
| `customerNumber` | `integer` | (**_required_**) |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/WorkAction/GetWorkActionByPersonCustomerNumber?customerNumber=%3Clong%3E" -H 'Accept: text/plain'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": {
        "id": "<long>",
        "guid": "<uuid>",
        "isActive": "<boolean>",
        "createDate": "<dateTime>",
        "createUserId": "<long>",
        "updateDate": "<dateTime>",
        "updateUserId": "<long>",
        "status": "SUCCESS",
        "worklistId": "<long>",
        "personId": "<long>",
        "loanAccountId": "<long>",
        "template": "<string>",
        "templateParameter": "<string>",
        "contactPersonId": "<long>",
        "contactRole": "RELATIVE",
        "contactPoint": "<string>",
        "expireDate": "<dateTime>"
    }
}
```
</details>

---

#### **_Retrieve a work action by Person.IdentityNumber. Rule: Should be WorklistType.CALL, descending WorkAction.CreateDate_**

**GET** `/api/v3/WorkAction/GetWorkActionByPersonIdentityNumber`

#### Description

Fetches a list of work actions associated with a specific Person.IdentityNumber.

##### Query Parameters

| Parameter        | Type     | Description      |
| :--------------- | :------- | :--------------- |
| `identityNumber` | `string` | (**_required_**) |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/WorkAction/GetWorkActionByPersonIdentityNumber?identityNumber=%3Cstring%3E" -H 'Accept: text/plain'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": {
        "id": "<long>",
        "guid": "<uuid>",
        "isActive": "<boolean>",
        "createDate": "<dateTime>",
        "createUserId": "<long>",
        "updateDate": "<dateTime>",
        "updateUserId": "<long>",
        "status": "SUCCESS",
        "worklistId": "<long>",
        "personId": "<long>",
        "loanAccountId": "<long>",
        "template": "<string>",
        "templateParameter": "<string>",
        "contactPersonId": "<long>",
        "contactRole": "RELATIVE",
        "contactPoint": "<string>",
        "expireDate": "<dateTime>"
    }
}
```
</details>

---

#### **_Retrieve a work action by LoanAccount.AccountNumber. Rule: Desc WorkAction.IsActive and then by desc Worklist.Type and then by desc WorkAction.CreateDate_**

**GET** `/api/v3/WorkAction/GetWorkActionByAccountAccountNumber`

#### Description

Fetches a list of work actions associated with a specific LoanAccount.AccountNumber.

##### Query Parameters

| Parameter       | Type     | Description      |
| :-------------- | :------- | :--------------- |
| `accountNumber` | `string` | (**_required_**) |
| `worklistType`  | `string` |                  |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/WorkAction/GetWorkActionByAccountAccountNumber?accountNumber=%3Cstring%3E&worklistType=NO_ACTION" -H 'Accept: text/plain'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": {
        "id": "<long>",
        "guid": "<uuid>",
        "isActive": "<boolean>",
        "createDate": "<dateTime>",
        "createUserId": "<long>",
        "updateDate": "<dateTime>",
        "updateUserId": "<long>",
        "status": "SUCCESS",
        "worklistId": "<long>",
        "personId": "<long>",
        "loanAccountId": "<long>",
        "template": "<string>",
        "templateParameter": "<string>",
        "contactPersonId": "<long>",
        "contactRole": "RELATIVE",
        "contactPoint": "<string>",
        "expireDate": "<dateTime>"
    }
}
```
</details>

---

#### **_Retrieve a work action by Person.CustomerNumber and ContactPerson.IdentityNumber and Activity.Uuid_**

**GET** `/api/v3/WorkAction/FindWorkAction`

#### Description

Fetches a detailed view of a specific work action identified by GUID.

##### Query Parameters

| Parameter                     | Type      | Description |
| :---------------------------- | :-------- | :---------- |
| `CustomerNumber`              | `integer` |             |
| `ContactPersonIdentityNumber` | `string`  |             |
| `ActivityUuid`                | `string`  |             |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/WorkAction/FindWorkAction?CustomerNumber=%3Clong%3E&ContactPersonIdentityNumber=%3Cstring%3E&ActivityUuid=%3Cstring%3E" -H 'Accept: text/plain'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": {
        "id": "<long>",
        "guid": "<uuid>",
        "isActive": "<boolean>",
        "createDate": "<dateTime>",
        "createUserId": "<long>",
        "updateDate": "<dateTime>",
        "updateUserId": "<long>",
        "stagingImportId": "<long>",
        "status": "PROCESSING",
        "worklist": {
            "name": "<string>",
            "type": "MANUAL",
            "guid": "<uuid>"
        },
        "worklistId": "<long>",
        "person": {
            "guid": "<uuid>",
            "name": "<string>",
            "middleName": "<string>",
            "surname": "<string>",
            "firmName": "<string>"
        },
        "personId": "<long>",
        "loanAccountId": "<long>",
        "template": "<string>",
        "templateParameter": "<string>",
        "contactPersonId": "<long>",
        "contactRole": "GUARDIAN",
        "contactPoint": "<string>",
        "expireDate": "<dateTime>",
        "priority": "<integer>"
    }
}
```
</details>

---

#### **_Create a work action_**

**POST** `/api/v3/WorkAction/Create`

#### Description

Creates a new work action based on the provided data.

##### Query Parameters

| Parameter       | Type | Description |
| :-------------- | :--- | :---------- |
| `no parameters` |      |             |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X POST "http://localhost:7080/api/v3/WorkAction/Create" -H 'Accept: text/plain' -data '{
  "stagingImportId": "<long>",
  "status": "NEW_ENTITY",
  "worklistId": "<long>",
  "personId": "<long>",
  "loanAccountId": "<long>",
  "leadAccountId": "<long>",
  "template": "<string>",
  "templateParameter": "<string>",
  "contactPersonId": "<long>",
  "contactRole": "SPOUSE",
  "contactPoint": "<string>",
  "expireDate": "<dateTime>",
  "priority": "<integer>"
}'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": {
        "id": "<long>",
        "guid": "<uuid>",
        "isActive": "<boolean>",
        "createDate": "<dateTime>",
        "createUserId": "<long>",
        "updateDate": "<dateTime>",
        "updateUserId": "<long>",
        "status": "SUCCESS",
        "worklistId": "<long>",
        "personId": "<long>",
        "loanAccountId": "<long>",
        "template": "<string>",
        "templateParameter": "<string>",
        "contactPersonId": "<long>",
        "contactRole": "RELATIVE",
        "contactPoint": "<string>",
        "expireDate": "<dateTime>"
    }
}
```
</details>

---

#### **_Update a work action_**

**POST** `/api/v3/WorkAction/Update`

#### Description

Updates an existing work action with the provided new details.

##### Query Parameters

| Parameter       | Type | Description |
| :-------------- | :--- | :---------- |
| `no parameters` |      |             |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X POST "http://localhost:7080/api/v3/WorkAction/Update" -H 'Accept: text/plain' -data '{
  "guid": "<uuid>",
  "isActive": "<boolean>",
  "updateUserId": "<long>",
  "stagingImportId": "<long>",
  "status": "PENDING",
  "worklistId": "<long>",
  "personId": "<long>",
  "loanAccountId": "<long>",
  "template": "<string>",
  "templateParameter": "<string>",
  "contactPersonId": "<long>",
  "contactRole": "AGENT",
  "contactPoint": "<string>",
  "expireDate": "<dateTime>",
  "priority": "<integer>"
}'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": {
        "id": "<long>",
        "guid": "<uuid>",
        "isActive": "<boolean>",
        "createDate": "<dateTime>",
        "createUserId": "<long>",
        "updateDate": "<dateTime>",
        "updateUserId": "<long>",
        "status": "SUCCESS",
        "worklistId": "<long>",
        "personId": "<long>",
        "loanAccountId": "<long>",
        "template": "<string>",
        "templateParameter": "<string>",
        "contactPersonId": "<long>",
        "contactRole": "RELATIVE",
        "contactPoint": "<string>",
        "expireDate": "<dateTime>"
    }
}
```
</details>

---

#### **_Update a work action by Id_**

**POST** `/api/v3/WorkAction/UpdateById`

#### Description

Updates an existing work action with the provided new details.

##### Query Parameters

| Parameter       | Type | Description |
| :-------------- | :--- | :---------- |
| `no parameters` |      |             |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X POST "http://localhost:7080/api/v3/WorkAction/UpdateById" -H 'Accept: text/plain' -data '{
  "id": "<long>",
  "isActive": "<boolean>",
  "updateUserId": "<long>",
  "stagingImportId": "<long>",
  "status": "FAILED",
  "worklistId": "<long>",
  "personId": "<long>",
  "loanAccountId": "<long>",
  "template": "<string>",
  "templateParameter": "<string>",
  "contactPersonId": "<long>",
  "contactRole": "OTHER",
  "contactPoint": "<string>",
  "expireDate": "<dateTime>",
  "priority": "<integer>"
}'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": {
        "id": "<long>",
        "guid": "<uuid>",
        "isActive": "<boolean>",
        "createDate": "<dateTime>",
        "createUserId": "<long>",
        "updateDate": "<dateTime>",
        "updateUserId": "<long>",
        "status": "SUCCESS",
        "worklistId": "<long>",
        "personId": "<long>",
        "loanAccountId": "<long>",
        "template": "<string>",
        "templateParameter": "<string>",
        "contactPersonId": "<long>",
        "contactRole": "RELATIVE",
        "contactPoint": "<string>",
        "expireDate": "<dateTime>"
    }
}
```
</details>

---

#### **_Move work actions to a different worklist_**

**POST** `/api/v3/WorkAction/MoveActions`

#### Description

Transfers selected work actions to a different worklist based on the provided parameters.

##### Query Parameters

| Parameter       | Type | Description |
| :-------------- | :--- | :---------- |
| `no parameters` |      |             |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X POST "http://localhost:7080/api/v3/WorkAction/MoveActions" -H 'Accept: text/plain' -data '{
  "worklistId": "<long>",
  "workActionIds": [
    "<long>",
    "<long>"
  ],
  "updateUserId": "<long>"
}'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": {
        "nullable": true
    }
}
```
</details>

---

#### **_Deactivate a work action_**

**POST** `/api/v3/WorkAction/Deactivate`

#### Description

Deactivates a specific work action, rendering it inactive within the system.

##### Query Parameters

| Parameter       | Type | Description |
| :-------------- | :--- | :---------- |
| `no parameters` |      |             |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X POST "http://localhost:7080/api/v3/WorkAction/Deactivate" -H 'Accept: text/plain' -data '{
  "guid": "<uuid>",
  "updateUserId": "<long>"
}'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": {
        "nullable": true
    }
}
```
</details>

---

#### **_Change WorkAction status_**

**POST** `/api/v3/WorkAction/UpdateStatusWorkActionById`

#### Description

##### Query Parameters

| Parameter       | Type | Description |
| :-------------- | :--- | :---------- |
| `no parameters` |      |             |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X POST "http://localhost:7080/api/v3/WorkAction/UpdateStatusWorkActionById" -H 'Accept: text/plain' -data '{
  "id": "<long>",
  "status": "PENDING"
}'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": {
        "id": "<long>",
        "guid": "<uuid>",
        "isActive": "<boolean>",
        "createDate": "<dateTime>",
        "createUserId": "<long>",
        "updateDate": "<dateTime>",
        "updateUserId": "<long>",
        "status": "SUCCESS",
        "worklistId": "<long>",
        "personId": "<long>",
        "loanAccountId": "<long>",
        "template": "<string>",
        "templateParameter": "<string>",
        "contactPersonId": "<long>",
        "contactRole": "RELATIVE",
        "contactPoint": "<string>",
        "expireDate": "<dateTime>"
    }
}
```
</details>

---

## Worklist

#### **_Retrieve a worklist by Guid_**

**GET** `/api/v3/Worklist/GetByGuid`

#### Description

Fetches a detailed worklist including relational data based on a specific GUID.

##### Query Parameters

| Parameter | Type   | Description      |
| :-------- | :----- | :--------------- |
| `guid`    | `guid` | (**_required_**) |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/Worklist/GetByGuid?guid=%3Cuuid%3E" -H 'Accept: text/plain'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": {
        "id": "<long>",
        "guid": "<uuid>",
        "isActive": "<boolean>",
        "createDate": "<dateTime>",
        "createUserId": "<long>",
        "updateDate": "<dateTime>",
        "updateUserId": "<long>",
        "name": "<string>",
        "type": "EMAIL",
        "auto": "<boolean>",
        "targetName": "<string>",
        "callingList": "<string>",
        "personal": "<boolean>",
        "worklistUsers": [
            {
                "worklistId": "<long>",
                "userId": "<long>"
            },
            {
                "worklistId": "<long>",
                "userId": "<long>"
            }
        ],
        "worklistUserGroups": [
            {
                "worklistId": "<long>",
                "userGroupId": "<long>"
            },
            {
                "worklistId": "<long>",
                "userGroupId": "<long>"
            }
        ]
    }
}
```
</details>

---

#### **_Retrieve all worklist_**

**GET** `/api/v3/Worklist/GetAll`

#### Description

Fetches all worklists with pagination support.

##### Query Parameters

| Parameter | Type      | Description |
| :-------- | :-------- | :---------- |
| `offset`  | `integer` |             |
| `limit`   | `integer` |             |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/Worklist/GetAll?Offset=%3Cinteger%3E&Limit=%3Cinteger%3E" -H 'Accept: text/plain'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": [
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "name": "<string>",
            "type": "MANUAL",
            "auto": "<boolean>",
            "targetName": "<string>",
            "callingList": "<string>",
            "personal": "<boolean>",
            "workActionsCount": "<integer>"
        },
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "name": "<string>",
            "type": "NO_ACTION",
            "auto": "<boolean>",
            "targetName": "<string>",
            "callingList": "<string>",
            "personal": "<boolean>",
            "workActionsCount": "<integer>"
        }
    ],
    "totalRowCount": "<integer>",
    "totalPageCount": "<integer>",
    "offset": "<integer>",
    "limit": "<integer>"
}
```
</details>

---

#### **_Retrieve all worklists with users_**

**GET** `/api/v3/Worklist/GetAllWithUsers`

#### Description

Fetches all worklists support.

##### Query Parameters

| Parameter       | Type | Description |
| :-------------- | :--- | :---------- |
| `no parameters` |     |            |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/Worklist/GetAllWithUsers" -H 'Accept: text/plain'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": [
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "name": "<string>",
            "type": "SMS",
            "auto": "<boolean>",
            "targetName": "<string>",
            "callingList": "<string>",
            "personal": "<boolean>",
            "users": [
                {
                    "id": "<long>",
                    "guid": "<uuid>",
                    "isActive": "<boolean>",
                    "createDate": "<dateTime>",
                    "createUserId": "<long>",
                    "updateDate": "<dateTime>",
                    "updateUserId": "<long>",
                    "agentNumber": "<string>",
                    "identityNumber": "<string>",
                    "firstName": "<string>",
                    "middleName": "<string>",
                    "lastName": "<string>",
                    "role": "System",
                    "roleNumber": "<integer>"
                },
                {
                    "id": "<long>",
                    "guid": "<uuid>",
                    "isActive": "<boolean>",
                    "createDate": "<dateTime>",
                    "createUserId": "<long>",
                    "updateDate": "<dateTime>",
                    "updateUserId": "<long>",
                    "agentNumber": "<string>",
                    "identityNumber": "<string>",
                    "firstName": "<string>",
                    "middleName": "<string>",
                    "lastName": "<string>",
                    "role": "System",
                    "roleNumber": "<integer>"
                }
            ],
            "userGroups": [
                {
                    "id": "<long>",
                    "guid": "<uuid>",
                    "isActive": "<boolean>",
                    "createDate": "<dateTime>",
                    "createUserId": "<long>",
                    "updateDate": "<dateTime>",
                    "updateUserId": "<long>",
                    "name": "<string>",
                    "description": "<string>"
                },
                {
                    "id": "<long>",
                    "guid": "<uuid>",
                    "isActive": "<boolean>",
                    "createDate": "<dateTime>",
                    "createUserId": "<long>",
                    "updateDate": "<dateTime>",
                    "updateUserId": "<long>",
                    "name": "<string>",
                    "description": "<string>"
                }
            ]
        },
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "name": "<string>",
            "type": "IVN",
            "auto": "<boolean>",
            "targetName": "<string>",
            "callingList": "<string>",
            "personal": "<boolean>",
            "users": [
                {
                    "id": "<long>",
                    "guid": "<uuid>",
                    "isActive": "<boolean>",
                    "createDate": "<dateTime>",
                    "createUserId": "<long>",
                    "updateDate": "<dateTime>",
                    "updateUserId": "<long>",
                    "agentNumber": "<string>",
                    "identityNumber": "<string>",
                    "firstName": "<string>",
                    "middleName": "<string>",
                    "lastName": "<string>",
                    "role": "Admin",
                    "roleNumber": "<integer>"
                },
                {
                    "id": "<long>",
                    "guid": "<uuid>",
                    "isActive": "<boolean>",
                    "createDate": "<dateTime>",
                    "createUserId": "<long>",
                    "updateDate": "<dateTime>",
                    "updateUserId": "<long>",
                    "agentNumber": "<string>",
                    "identityNumber": "<string>",
                    "firstName": "<string>",
                    "middleName": "<string>",
                    "lastName": "<string>",
                    "role": "Agent",
                    "roleNumber": "<integer>"
                }
            ],
            "userGroups": [
                {
                    "id": "<long>",
                    "guid": "<uuid>",
                    "isActive": "<boolean>",
                    "createDate": "<dateTime>",
                    "createUserId": "<long>",
                    "updateDate": "<dateTime>",
                    "updateUserId": "<long>",
                    "name": "<string>",
                    "description": "<string>"
                },
                {
                    "id": "<long>",
                    "guid": "<uuid>",
                    "isActive": "<boolean>",
                    "createDate": "<dateTime>",
                    "createUserId": "<long>",
                    "updateDate": "<dateTime>",
                    "updateUserId": "<long>",
                    "name": "<string>",
                    "description": "<string>"
                }
            ]
        }
    ]
}
```
</details>

---

#### **_Retrieve personal or shared worklist_**

**GET** `/api/v3/Worklist/GetByPersonal`

#### Description

Fetches worklists filtered by whether they are personal or shared.

##### Query Parameters

| Parameter       | Type | Description |
| :-------------- | :--- | :---------- |
| `isPersonal` |     `boolean` |            |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/Worklist/GetByPersonal?isPersonal=%3Cboolean%3E" -H 'Accept: text/plain'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": [
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "name": "<string>",
            "type": "CALL",
            "auto": "<boolean>",
            "targetName": "<string>",
            "callingList": "<string>",
            "personal": "<boolean>"
        },
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "name": "<string>",
            "type": "NO_ACTION",
            "auto": "<boolean>",
            "targetName": "<string>",
            "callingList": "<string>",
            "personal": "<boolean>"
        }
    ]
}
```
</details>

---

#### **_Retrieve worklists by User with userIdentityNumber_**

**GET** `/api/v3/Worklist/GetByUserIdentityNumber`

#### Description

Fetches worklists associated with a specific user based on the user's with userIdentityNumber.

##### Query Parameters

| Parameter       | Type | Description |
| :-------------- | :--- | :---------- |
| `userIdentityNumber` |     `string` | (**_required_**)            |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/Worklist/GetByUserIdentityNumber?userIdentityNumber=%3Cstring%3E" -H 'Accept: text/plain'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": [
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "name": "<string>",
            "type": "CALL",
            "auto": "<boolean>",
            "targetName": "<string>",
            "callingList": "<string>",
            "personal": "<boolean>"
        },
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "name": "<string>",
            "type": "NO_ACTION",
            "auto": "<boolean>",
            "targetName": "<string>",
            "callingList": "<string>",
            "personal": "<boolean>"
        }
    ]
}
```
</details>

---

#### **_Retrieve worklists by User Group Guid_**

**GET** `/api/v3/Worklist/GetByUserGroupGuid`

#### Description

Fetches worklists associated with a specific user group based on the group's GUID.

##### Query Parameters

| Parameter       | Type | Description |
| :-------------- | :--- | :---------- |
| `userGroupGuid` |     `guid` |             |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/Worklist/GetByUserGroupGuid?userGroupGuid=%3Cuuid%3E" -H 'Accept: text/plain'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": [
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "name": "<string>",
            "type": "CALL",
            "auto": "<boolean>",
            "targetName": "<string>",
            "callingList": "<string>",
            "personal": "<boolean>"
        },
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "name": "<string>",
            "type": "NO_ACTION",
            "auto": "<boolean>",
            "targetName": "<string>",
            "callingList": "<string>",
            "personal": "<boolean>"
        }
    ]
}
```
</details>

---

#### **_Retrieve worklists by Type_**

**GET** `/api/v3/Worklist/GetByType`

#### Description

Fetches worklists associated with a specific user group based on the type.

##### Query Parameters

| Parameter       | Type | Description |
| :-------------- | :--- | :---------- |
| `worklistTypeEnum` |     `string` |         |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X GET "http://localhost:7080/api/v3/Worklist/GetByType?worklistTypeEnum=NO_ACTION" -H 'Accept: text/plain'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": [
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "name": "<string>",
            "type": "CALL",
            "auto": "<boolean>",
            "targetName": "<string>",
            "callingList": "<string>",
            "personal": "<boolean>"
        },
        {
            "id": "<long>",
            "guid": "<uuid>",
            "isActive": "<boolean>",
            "createDate": "<dateTime>",
            "createUserId": "<long>",
            "updateDate": "<dateTime>",
            "updateUserId": "<long>",
            "name": "<string>",
            "type": "NO_ACTION",
            "auto": "<boolean>",
            "targetName": "<string>",
            "callingList": "<string>",
            "personal": "<boolean>"
        }
    ]
}
```
</details>

---

#### **_Create a new worklist_**

**POST** `/api/v3/Worklist/Create`

#### Description

Creates a new worklist based on the provided information.

##### Query Parameters

| Parameter       | Type | Description |
| :-------------- | :--- | :---------- |
| `no parameters` |      |             |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X POST "http://localhost:7080/api/v3/Worklist/Create" -H 'Accept: text/plain' -data '{
  "name": "<string>",
  "type": "PUSH",
  "auto": "<boolean>",
  "targetName": "<string>",
  "callingList": "<string>",
  "personal": "<boolean>"
}'
````

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": {
        "id": "<long>",
        "guid": "<uuid>",
        "isActive": "<boolean>",
        "createDate": "<dateTime>",
        "createUserId": "<long>",
        "updateDate": "<dateTime>",
        "updateUserId": "<long>",
        "name": "<string>",
        "type": "SMS",
        "auto": "<boolean>",
        "targetName": "<string>",
        "callingList": "<string>",
        "personal": "<boolean>"
    }
}
```
</details>

---

#### **_Update an existing worklist_**

**POST** `/api/v3/Worklist/Update`

#### Description

Updates an existing worklist with new details as provided.

##### Query Parameters

| Parameter       | Type | Description |
| :-------------- | :--- | :---------- |
| `no parameters` |      |             |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X POST "http://localhost:7080/api/v3/Worklist/Update" -H 'Accept: text/plain' -data '{
  "guid": "<uuid>",
  "isActive": "<boolean>",
  "updateUserId": "<long>",
  "name": "<string>",
  "type": "PUSH",
  "auto": "<boolean>",
  "targetName": "<string>",
  "callingList": "<string>",
  "personal": "<boolean>"
}'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": {
        "id": "<long>",
        "guid": "<uuid>",
        "isActive": "<boolean>",
        "createDate": "<dateTime>",
        "createUserId": "<long>",
        "updateDate": "<dateTime>",
        "updateUserId": "<long>",
        "name": "<string>",
        "type": "NO_ACTION",
        "auto": "<boolean>",
        "targetName": "<string>",
        "callingList": "<string>",
        "personal": "<boolean>",
        "workActionsCount": "<integer>"
    }
}
```
</details>

---

#### **_Update users associated with a spesific worklist_**

**POST** `/api/v3/Worklist/UpdateWorklistUsers`

#### Description

Updates the list of users associated with a particular worklist.

##### Query Parameters

| Parameter       | Type | Description |
| :-------------- | :--- | :---------- |
| `no parameters` |      |             |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X POST "http://localhost:7080/api/v3/Worklist/UpdateWorklistUsers" -H 'Accept: text/plain' -data '{
  "worklistId": "<long>",
  "userIds": [
    "<integer>",
    "<integer>"
  ]
}'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": {
        "nullable": true
    }
}
```
</details>

---

#### **_Update user groups associated with a spesific worklist_**

**POST** `/api/v3/Worklist/UpdateWorklistUserGroups`

#### Description

Updates the list of user groups associated with a particular worklist.

##### Query Parameters

| Parameter       | Type | Description |
| :-------------- | :--- | :---------- |
| `no parameters` |      |             |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X POST "http://localhost:7080/api/v3/Worklist/UpdateWorklistUserGroups" -H 'Accept: text/plain' -data '{
  "worklistId": "<long>",
  "userGroupIds": [
    "<integer>",
    "<integer>"
  ]
}'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": {
        "nullable": true
    }
}
```
</details>

---

#### **_Deactivate an existing worklist_**

**POST** `/api/v3/Worklist/Deactivate`

#### Description

Deactivates a worklist, rendering it inactive in the system.

##### Query Parameters

| Parameter       | Type | Description |
| :-------------- | :--- | :---------- |
| `no parameters` |      |             |

##### Headers

| Key            | Value              |
| :------------- | :----------------- |
| `Content-Type` | `application/json` |

##### Request

```bash
curl -X POST "http://localhost:7080/api/v3/Worklist/Deactivate" -H 'Accept: text/plain' -data '{
  "guid": "<uuid>",
  "updateUserId": "<long>"
}'
```

<details>
<summary><h4></h4> Example Response</h4></summary>
  
```json
{
    "statusCode": "<integer>",
    "message": "<string>",
    "dateTime": "<dateTime>",
    "data": {
        "nullable": true
    }
}
```
</details>

---










