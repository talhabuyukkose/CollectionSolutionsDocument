<h2 align="center" id="RestApi"> CollectionApp.RestApi</h2>
<h3 id="api"> Setup and Run</h3>

You can clone this repository using:

```sh
git https://github.com/sadeyazilim/SolutionCollectionApp/tree/Development/CollectionApp.RestApi.git
```
Navigate to project directory:
```sh
cd SolutionCollectionApp/tree/Development/CollectionApp.RestApi
```
Restore the dependencies:
```sh
dotnet restore
```
Run the project:
```sh
dotnet run
```

>> ### Setup in Docker Environment
   Build the Docker image:
   ```sh
   docker build -t CollectionApp.RestApi .
   ```
   Run the Docker container:
   ```sh
   docker run -d -p 5000:80 CollectionApp.RestApi
   ```

>## Requests, Answers and Obligations
### Activity

 * GetByGuid  
Fetches a specific activity using its GUID, including related entities.  
Parameters: 
                        
   * guid (string) __required__ 

* GetByLoanAccountGuid  
Fetches activities related to a specific LoanAccount GUID.
Parameters: 
                        
   * guid (string) __required__ 
   * offset (integer)
   * limit (integer)
   * activityTypeEnum (string)

* GetByPersonGuid  
Fetches activities related to a specific Person GUID.  
Parameters: 
                        
   * guid (string) __required__ 
   * offset (integer)
   * limit (integer)
   * activityTypeEnum (string)

* GetByWorkActionGuid  
Fetches activities related to a specific WorkAction GUID.  
Parameters: 
                        
   * guid (string) __required__ 
   * offset (integer)
   * limit (integer)
   * activityTypeEnum (string)
   * IsShowSystemUsersActivity (boolean)

* GetByUserIdentityNumber  
Fetches activities related to a specific User with userIdentityNumber.  
Parameters: 
                        
   * userIdentityNumber (string) __required__ 
   * offset (integer)
   * limit (integer)
   * activityTypeEnum (string)

* GetByPersonGuidAndDateOnlyAgent  
Fetches a list of activities associated with a specific person GUID.  
Parameters: 
                        
   * personGuid (string) __required__ 
   * loanAccountNumber (string)
   * startDate (string)
   * endDate (string)
   * sortBy (string)
   * sortOrder (string)
   * offset (integer)
   * limit (integer)
   * userId (integer)
   * ResultId (integer)
   * SubResultId (integer)
   * activityType (string)

* Create  
Creates a new activity with the provided details.
No parameters.

* Update  
Updates an existing activity with the specified details.  
No parameters.

* Deactivate  
Deactivates a specified activity.  
No parameters.

### Const

* GetAllEnums  
The method return all enums.  
No parameters.  

* GetActivityResults  
Fetches a list of all ActivityResults.  
No parameters.   

* GetSegments  
Fetches a list of all segments.  
No parameters. 

* GetActivityResultById  
Fetches a specific ActivityResult by its Id.  
No parameters.  

* GetActivitySubResultById  
Fetches a specific ActivitySubResult by its Id.  
No parameters.  

* GetActivitySubResults  
Fetches a list of all ActivitySubResults.  
No parameters.  

* GetLastWorkDay  
Returns a last work day of any month in any year.  
Parameters: 
                        
   * year (integer)
   * month (integer)

### Cti

* CallPermit  
Parameters: 
                        
   * guid (string)  

* SetCallStart  
No parameters.  

* SetCallResult  
No parameters.  

### Customer
* GetLoanAccountPaymentByLoanAccountGuid  
Fetches a detailed Loan Account Payments using its loanAccountGuid identifier.  
Parameters: 
                        
   * loanAccountGuid (string) __required__  

* GetAllAccountsBaseEntityByPersonGuid  
Fetches a detailed base account using its personGUID identifier.  
Parameters: 
                        
   * personGuid (string) __required__  

* GetLoanAccountByGuid  
Fetches a detailed loan account using its GUID identifier.  
Parameters: 
                        
   * loanAccountGuid (string) __required__    

* GetBaseAccountByAccountNumber  
Fetches a detailed loan account using its GUID identifier.  
Parameters: 
                        
   * accountNumber (string) __required__  

* GetLoanAccountsByPersonGuid  
Fetches loan accounts associated with a specific person's GUID.  
Parameters: 
                        
   * personGuid (string) __required__  

* GetLoanAccountsByCustomerNumber  
Fetches loan accounts associated with a specific customer number.  
Parameters: 
                        
   * customerNumber (integer) __required__  

* GetCardAccountByGuid  
Fetches a detailed card account using its GUID identifier.  
Parameters: 
                        
   * guid (string) __required__   

* GetCardAccountsByPersonGuid  
Fetches card accounts associated with a specific person's GUID.  
Parameters: 
                        
   * personGuid (string) __required__   

* GetCardAccountsByCustomerNumber  
Fetches card accounts associated with a specific customer number.  
Parameters: 
                        
   * customerNumber (integer) __required__  

* GetPhonesByPersonGuid  
Fetches all phone numbers associated with a given person's GUID. This is useful for retrieving contact details linked to a person record.  
Parameters: 
                        
   * personGuid (string) __required__  

* GetEmailsByPersonGuid  
Fetches all emails associated with a given person's GUID. This endpoint is intended for retrieving all registered email addresses for a specific individual.  
Parameters: 
                        
   * personGuid (string) __required__  

* GetAddressesByPersonGuid  
Fetches all Addresses associated with a given person's GUID. This endpoint is intended for retrieving all registered addresses for a specific individual.  
Parameters: 
                        
   * personGuid (string) __required__  

* CreatePhone  
Registers a new phone number in the system.  
No parameters.  

* UpdatePhone  
Updates an existing phone number in the system.  
No parameters.  

* SetPhoneLastSuccessfulDate  
Updates an existing phone number in the system. 
No parameters.  

* DeletePhone  
Deactivates a phone number, effectively removing it from active use.  
No parameters.   

* CreateEmail  
Registers a new email in the system.  
No parameters. 

* UpdateEmail   
Updates an existing email in the system.  
No parameters. 

* DeleteEmail  
Deactivates an Email, effectively removing it from active use.  
No parameters. 

* CreateAddress   
Creates a new address record in the system.  
No parameters. 

* UpdateAddress  
Updates an existing address record in the system.  
No parameters.  

* DeleteAddress  
Deactivates an address record in the system.  
No parameters.  

* GetBucketChangeByPersonGuid  
Fetches all bucket changes associated with a given person's GUID. This is useful for retrieving contact details linked to a person record.  
Parameters: 
                        
   * personGuid (string) __required__  

* GetBucketChangeByLoanAccountGuid  
Fetches all bucket changes associated with a given LoanAccount's GUID. This is useful for retrieving contact details linked to a LoanAccount record.  
Parameters: 
                        
   * loanAccountGuid (string) __required__  

* GetCustomerByGuid  
Fetches a detailed person using its GUID identifier.  
Parameters: 
                        
   * guid (string) __required__  

* GetCustomerInfoByGuid  
Fetches a detailed person using its GUID identifier.  
Parameters: 
                        
   * guid (string) __required__  

* CustomerSearch  
Fetches person models associated with a specific search. Search term take Customer Number, Identity Number, Phone Numbers, Name, MiddleName, Surname or Company Name  
Parameters: 
                        
   * search (string)
   * segment (string)
   * Offset (integer)
   * Limit (integer)
   * sortBy  (string)
   * sortOrder (string)
   * personFlag (string)
   * bucketEnum (string)  

* GetRelationPersonByCustomerNumber  
Fetches relational person associated with a specific customer number.  
Parameters: 
                        
   * customerNumber (integer) __required__  

### PromisePayment  

* GetByGuid  
Returns a specific PromisePayment identified by GUID, including related details.  
Parameters: 
                        
   * guid (string) __required__

* GetByLoanAccountGuid  
Returns PromisePayments associated with a specific LoanAccount GUID.  
Parameters: 
                        
   * guid (string) __required__  

* GetByActivityGuid  
Returns PromisePayments associated with a specific Activity GUID.  
Parameters: 
                        
   * guid (string) __required__  

* GetByWorkActionGuid  
Returns PromisePayments associated with a specific WorkAction GUID.  
Parameters: 
                        
   * guid (string) __required__  

* GetByWorklistGuid  
Returns paginated PromisePayments associated with a specific Worklist GUID.  
Parameters: 
                        
   * guid (string) __required__  
   * offset (integer)
   * limit (integer)

* GetByPersonGuid  
Returns paginated PromisePayments associated with a specific Person GUID.  
Parameters: 
                        
   * guid (string) __required__  
   * offset (integer)
   * limit (integer)

* GetByUserIdentityNumber  
Returns paginated PromisePayments associated with a specific User with userIdentityNumber.  
Parameters: 
                        
   * userIdentityNumber (string) __required__  
   * offset (integer)
   * limit (integer)

* Create  
Creates new PromisePayments based on the provided data.  
No parameters.  

* Update  
Updates an existing PromisePayment with the specified details.  
No parameters.

* Deactivate  
Deactivates the specified PromisePayment.  
No parameters.

### ProxyServices

* PromisePaymentCalculate  
Parameters: 
                        
   * guid (string) 

* GetBankAccountBalanceList 
Fetches BankAccountBalances related to AccountBranchCode and AccountNumber.   
Parameters:

   * AccountBranchCode (string)
   * AccountNumber (string)

* GetBankAccountCautionList  
Fetches BankAccountCautions related to AccountBranchCode and AccountNumber.  
Parameters:

   * AccountBranchCode (string)
   * AccountNumber (string)

* GetBankAccountLoanList  
Fetches BankAccountLoans related to AccountBranchCode and AccountNumber and AccountSuffix.  
Parameters:

   * AccountBranchCode (string)
   * AccountNumber (string)
   * AccountSuffix (integer)

* GetBankAccountLoanFutureList  
Fetches BankAccountLoansFuture related to AccountBranchCode and AccountNumber and AccountSuffix and ForwardDay.  
Parameters:

   * AccountBranchCode (string)
   * AccountNumber (string)
   * AccountSuffix (integer)
   * ForwardDay (string)

* GetBankLoanCloseAmount  
Fetches BankAccountLoans related to AccountBranchCode and AccountNumber and AccountSuffix.  
Parameters:

   * AccountBranchCode (string)
   * AccountNumber (string)
   * AccountSuffix (integer)

### User

* GetByGuid
Returns a specific user identified by GUID, including related details.  
Parameters: 
                        
   * guid (string) __required__  

* GetByIdentityNumber  
Returns a specific user identified by userIdentityNumber, including related details.  
Parameters: 
                        
   * userIdentityNumber (string) __required__  

* GetAll  
Returns a paginated list of all users.  
Parameters:  

   * offset (integer)
   * limit (integer)
   * sortBy (string)
   * sortOrder (string)

* GetAllUserGroups  
Returns a paginated list of all usergroups.
No parameters.  

* GetAllWithDeActivate  
Returns a paginated list of all users, including those who are deactivated.  
Parameters:  

   * offset (integer)
   * limit (integer)

* Summary  
Provides statistical summary data for a specific user over a given period.  
Parameters:

   * userGuid (string)
   * startDate (string)
   * endDate (string)

* Update  
Updates the details of an existing user.
No parameters.  

* UpdateUserWorklists  
Updates the worklists assigned to a specific user.  
No parameters.

* Deactivate  
Deactivates a specific user, rendering them inactive in the system.  
No parameters.  

* Synchronize  
Create user or update with the specified details.  
No parameters.

### WorkAction

* GetByGuid
Fetches a detailed view of a specific work action identified by GUID.
Parameters: 
                        
   * guid (string) __required__  

* GetByWorkListGuid  
Fetches a paginated list of work actions associated with a specific worklist GUID.  
Parameters: 
                        
   * WorkListGuid (string) __required__  
   * name (string)
   * IdentityNumber (string)
   * AccountNumber (string)
   * Status (string)
   * BucketEnum (string)
   * ActivityResultId (integer)
   * ActivitySubresultId (integer)
   * offset (integer)
   * Limit (integer)
   * sortBy (string)
   * sortOrder (string) 

* GetByPersonGuidAndDate  
Fetches a list of work actions associated with a specific worklist GUID.  
Parameters:

   * personGuid (string) __required__
   * startDate (string)
   * loanAccountNumber (string)
   * endDate (string)
   * sortBy (string)
   * sortOrder (string) 
   * worklistType (string)

* GetByPersonGuid  
Fetches a paginated list of work actions associated with a specific person's GUID.  
Parameters:

   * guid (string) __required__ 
   * offset (integer)
   * Limit (integer)
   * sortBy (string)
   * sortOrder (string) 

* GetByLoanAccountGuid  
Fetches a paginated list of work actions linked to a specific loan account GUID.  
Parameters:

   * guid (string) __required__ 
   * offset (integer)
   * Limit (integer)
   * sortBy (string)
   * sortOrder (string) 

* GetByUserIdentityNumber  
Fetches a paginated list of work actions linked to a specific user's userId.  
Parameters: 
                        
   * userIdentityNumber (string) __required__  
   * name (string)
   * IdentityNumber (string)
   * AccountNumber (string)
   * WorkListGuid (string)
   * Status (string)
   * BucketEnum (string)
   * ActivityResultId (integer)
   * ActivitySubresultId (integer)
   * offset (integer)
   * Limit (integer)
   * sortBy (string)
   * sortOrder (string)

* GetWorkActionByPersonCustomerNumber  
Fetches a list of work actions associated with a specific Person.CustomerNumber  
Parameters: 
                        
   * customerNumber (string) __required__ 

* GetWorkActionByPersonIdentityNumber  
Fetches a list of work actions associated with a specific Person.IdentityNumber.  
Parameters: 
                        
   * identityNumber (string) __required__ 

* GetWorkActionByAccountAccountNumber  
Fetches a list of work actions associated with a specific LoanAccount.AccountNumber.  
Parameters: 
                        
   * accountNumber (string) __required__ 
   * worklistType (string)

* FindWorkAction  
Fetches a detailed view of a specific work action identified by GUID.  
Parameters: 
                        
   * CustomerNumber (integer)
   * ContactPersonIdentityNumber (string)
   * ActivityUuid

* Create  
Creates a new work action based on the provided data.  
No parameters.

* Update  
Updates an existing work action with the provided new details.  
No parameters.

* UpdateById  
Updates an existing work action with the provided new details.  
No parameters.

* MoveActions  
Transfers selected work actions to a different worklist based on the provided parameters.  
No parameters.

* Deactivate  
Deactivates a specific work action, rendering it inactive within the system.  
No parameters.

* UpdateStatusWorkActionById  
No parameters.

### WorkList

* GetByGuid
Fetches a detailed worklist including relational data based on a specific GUID.  
Parameters:

   * guid (string) __required__ 

* GetAll
Fetches all worklists with pagination support.  
Parameters:

   * Offset (integer)
   * Limit (integer)

* GetAllWithUsers  
Fetches all worklists support.  
No parameters.

* GetByPersonal
Fetches worklists filtered by whether they are personal or shared.  
Parameters:

   * isPersonel (boolean)

* GetByUserIdentityNumber  
Fetches worklists associated with a specific user based on the user's with userIdentityNumber.  
Parameters:

   * userIdentityNumber (string) __required__

* GetByUserGroupGuid  
Fetches worklists associated with a specific user group based on the group's GUID.  
Parameters:

   * userGroupGuid (string)

* GetByType
Fetches worklists associated with a specific user group based on the type.  
Parameters:

   * worklistTypeEnum (string)

* Create
Creates a new worklist based on the provided information.  
No parameters.

* Update  
Updates an existing worklist with new details as provided.  
No parameters.  

*  UpdateWorklistUsers  
Updates the list of users associated with a particular worklist.  
No parameters.

* UpdateWorklistUserGroups  
Updates the list of user groups associated with a particular worklist.  
No parameters. 

* Deactivate  
Deactivates a worklist, rendering it inactive in the system.  
No parameters.


<h2>RestApi EndPoints</h2>

## Contents 
*  [Activity Endpoints](#Activity)
* [Const Endpoints](#Const)
* [Cti Endpoints](#Cti)
* [Customer Endpoints](#Customer)
* [PromisePayment Endpoints](#PromisePayment)
* [ProxyServices Endpoints](#ProxyServices)
* [User Endpoints](#User)
* [WorkAction Endpoints](#WorkAction)
* [WorkList Endpoints](#WorkList)

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
     

>## Packages
The list of packages which is used:
```sh
 "Elastic.Apm.NetCoreAll" Version="1.26.0"  
 "Microsoft.AspNetCore.Authentication.JwtBearer" Version="8.0.7"  
 "Microsoft.AspNetCore.OpenApi" Version="8.0.7"  
 "Microsoft.EntityFrameworkCore.Design" Version="8.0.7"
 "Microsoft.EntityFrameworkCore" Version="8.0.7"  
 "Microsoft.Extensions.Diagnostics.HealthChecks" Version="8.0.7"  
 "Microsoft.Extensions.Diagnostics.HealthChecks.Abstractions" Version="8.0.7"  
 "Microsoft.VisualStudio.Azure.Containers.Tools.Targets" Version="1.19.6"  
 "Npgsql.EntityFrameworkCore.PostgreSQL" Version="8.0.4"  
 "Microsoft.IdentityModel.Tokens" Version="7.4.1"  
 "runtime.unix.System.Private.Uri" Version="4.3.2"  
 "Swashbuckle.AspNetCore" Version="6.5.0"  
 "Newtonsoft.Json" Version="13.0.3"  
 "Swashbuckle" Version="6.0.0-rc1-final"  
 "Swashbuckle.AspNetCore.Annotations" Version="6.5.0"  
 "System.IdentityModel.Tokens.Jwt" Version="7.4.1"  
 "System.Private.Uri" Version="4.3.2"  
```
