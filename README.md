<h1 align="center"> COLLECTION SOLUTIONS</h1>

> ## Properties
* __.NET 8__ is used in this project as the primary development platform.
* __Onion Architecture__  is employed in this project to organize the codebase effectively. 
* __Redis__  is integrated into this project as a caching mechanism and data store.

> ## Goals

A company which cannot receive payments from customers and wants to reach customers at regular intervals through SMS, e-mail or call to inform them about the payment. This project is being developed to speed up this process.   
       Customers who need to be reached to inform are classified according to how to contact them. E-mail, SMS and IVN calls are sent through the system.             
       The customers to be reached by call are listed so that the bank can contact them one by one.

<h2 align="center"> CollectionApp.Cli</h2>

> ## Setup and Run
You can clone this repository using:

```sh
git https://github.com/sadeyazilim/SolutionCollectionApp/tree/Development/CollectionApp.Cli.git
```
Navigate to project directory:
```sh
cd SolutionCollectionApp/tree/Development/CollectionApp.Cli
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
   docker build -t CollectionApp.Cli .
   ```
   Run the Docker container:
   ```sh
   docker run -d -p 5000:80 CollectionApp.Cli
   ```

>>### Docker Compose Setup
* yml  
Start the container using Docker Compose:
```sh
docker-compose up
```

> ## Packages
The list of packages which is used:
```sh
 "CommandLineParser" Version="2.9.1" 
 "McMaster.Extensions.CommandLineUtils" Version="4.1.1" 
 "Microsoft.Extensions.Configuration.CommandLine" Version="8.0.0" 
 "Microsoft.Extensions.Hosting" Version="8.0.0" 
 "Microsoft.Extensions.Http" Version="8.0.0" 
 "Newtonsoft.Json" Version="13.0.3" 
 "System.ServiceModel.Duplex" Version="6.0.*" 
 "System.ServiceModel.Federation" Version="6.0.*" 
 "System.ServiceModel.Http" Version="6.0.*" 
 "System.ServiceModel.NetTcp" Version="6.0.*" 
 "System.ServiceModel.Security" Version="6.0.*" 
 "System.Text.Json" Version="8.0.4" 
```

<h2 align="center"> CollectionApp.Core</h2>

 Core is the central layer that contains the core business logic and rules, in other words, the heart of the project.

> ## Setup and Run
You can clone this repository using:

```sh
git https://github.com/sadeyazilim/SolutionCollectionApp/tree/Development/CollectionApp.Core.git
```
Navigate to project directory:
```sh
cd SolutionCollectionApp/tree/Development/CollectionApp.Core
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
   docker build -t CollectionApp.Core .
   ```
   Run the Docker container:
   ```sh
   docker run -d -p 5000:80 CollectionApp.Core
   ```

>>### Docker Compose Setup
* yml  
Start the container using Docker Compose:
```sh
docker-compose up
```


>## Packages
The list of packages which is used:
```sh
 "StackExchange.Redis" Version="2.7.33" 
 "Serilog.Sinks.Async" Version="1.5.0" 
 "Microsoft.Extensions.Diagnostics.HealthChecks" Version="8.0.4"
 "Microsoft.AspNetCore.SignalR.Client" Version="8.0.4" 
 "AutoMapper" Version="13.0.1" 
 
```
<h2 align="center"> CollectionApp.Data</h2>

> ## Setup and Run
You can clone this repository using:

```sh
git https://github.com/sadeyazilim/SolutionCollectionApp/tree/Development/CollectionApp.Data.git
```
Navigate to project directory:
```sh
cd SolutionCollectionApp/tree/Development/CollectionApp.Data
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
   docker build -t CollectionApp.Data .
   ```
   Run the Docker container:
   ```sh
   docker run -d -p 5000:80 CollectionApp.Data
   ```

>>### Docker Compose Setup
* yml  
Start the container using Docker Compose:
```sh
docker-compose up
```

>## Packages
The list of packages which is used:

```sh
 "Microsoft.EntityFrameworkCore" Version="8.0.7" 
 "Microsoft.EntityFrameworkCore.Abstractions" Version="8.0.7" 
 "Microsoft.EntityFrameworkCore.Proxies" Version="8.0.7" 
 "Microsoft.EntityFrameworkCore.Relational" Version="8.0.7" 
 "Microsoft.EntityFrameworkCore.SqlServer" Version="8.0.7" 
 "Microsoft.EntityFrameworkCore.Tools" Version="8.0.7">
 "Npgsql.EntityFrameworkCore.PostgreSQL" Version="8.0.4" 
 "runtime.unix.System.Private.Uri" Version="4.3.2" 
 "System.Private.Uri" Version="4.3.2" 
```

> ## Migration Process

#### To create migration using Powershell.
```sh
dotnet ef migrations add InitialMigration
```

#### The last created migration file is applied to the database and schema changes are performed with 
```sh
dotnet ef database update
```

#### If an incorrect migration has been applied, to undo it,
```sh
dotnet ef database update <PreviousMigrationName>
dotnet ef migrations remove
```

#### Return to a specific migration
```sh
dotnet ef database update <MigrationName>
```

<h2 align="center"> CollectionApp.NUnit</h2>


> ## Setup and Run
You can clone this repository using:

```sh
git https://github.com/sadeyazilim/SolutionCollectionApp/tree/Development/CollectionApp.NUnit.git
```
Navigate to project directory:
```sh
cd SolutionCollectionApp/tree/Development/CollectionApp.NUnit
```
Run the project:
```sh
dotnet test
```


>## Packages
The list of packages which is used:
```sh
 "Microsoft.EntityFrameworkCore.InMemory" Version="8.0.7" 
 "Microsoft.NET.Test.Sdk" Version="17.10.0" 
 "Moq" Version="4.20.70" 
 "NSubstitute" Version="5.1.0" 
 "NUnit" Version="3.14.0" 
 "NUnit3TestAdapter" Version="4.5.0" 
 "NUnit.Analyzers" Version="4.0.1">
 "coverlet.collector" Version="6.0.2">
 "System.Text.RegularExpressions" Version="4.3.1" 
```
<h2 align="center"> CollectionApp.RestApi</h2>

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
### ProxyServices
### User
### WorkAction
### WorkList





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

<h2 align="center"> CollectionApp.WorkerCti</h2>

 The customers that need to be called are listed here.

>## Packages
The list of packages which is used:
```sh
 "Elastic.Apm" Version="1.26.0"  
 "Microsoft.Extensions.Diagnostics.HealthChecks" Version="8.0.7"  
 "Microsoft.Extensions.Diagnostics.HealthChecks.EntityFrameworkCore" Version="8.0.7"  
 "Microsoft.Extensions.Hosting" Version="8.0.0"  
 "Microsoft.Extensions.Http" Version="8.0.0"  
 "Microsoft.VisualStudio.Azure.Containers.Tools.Targets" Version="1.19.6"  
 "runtime.unix.System.Private.Uri" Version="4.3.2"  
 "System.Private.Uri" Version="4.3.2"  
 "System.Text.Json" Version="8.0.4"  
```

<h2 align="center"> CollectionApp.WorkerEmail</h2>

 Customers who will receive emails are listed here.

>## Packages
The list of packages which is used:
```sh
 "Elastic.Apm" Version="1.26.0"  
 "Microsoft.Extensions.Diagnostics.HealthChecks" Version="8.0.7"  
 "Microsoft.Extensions.Diagnostics.HealthChecks.EntityFrameworkCore" Version="8.0.7"  
 "Microsoft.Extensions.Hosting" Version="8.0.0"  
 "Microsoft.Extensions.Http" Version="8.0.0"  
 "Microsoft.VisualStudio.Azure.Containers.Tools.Targets" Version="1.19.6"  
 "runtime.unix.System.Private.Uri" Version="4.3.2"  
 "System.Private.Uri" Version="4.3.2"  
```
<h2 align="center"> CollectionApp.WorkerImporter</h2>
           
 Pulls customer information which is necessary for transactions from the company.

>## Packages
The list of packages which is used:
```sh
 "Microsoft.EntityFrameworkCore.Design" Version="8.0.7"
 "Microsoft.EntityFrameworkCore.SqlServer" Version="8.0.7"  
 "Microsoft.Extensions.Diagnostics.HealthChecks" Version="8.0.7"  
 "Microsoft.Extensions.Diagnostics.HealthChecks.EntityFrameworkCore" Version="8.0.7"  
 "Microsoft.Extensions.Hosting" Version="8.0.0"  
 "Microsoft.Extensions.Http" Version="8.0.0"  
 "Microsoft.VisualStudio.Azure.Containers.Tools.Targets" Version="1.19.6"  
 "runtime.unix.System.Private.Uri" Version="4.3.2"  
 "System.Private.Uri" Version="4.3.2"  
```

<h2 align="center"> CollectionApp.WorkerIvn</h2>

The customers that need to be called by IVN are listed here.

>## Packages
The list of packages which is used:
```sh
 "Microsoft.Extensions.Diagnostics.HealthChecks.EntityFrameworkCore" Version="8.0.7"  
 "Microsoft.Extensions.Hosting" Version="8.0.0"  
 "System.Text.Json" Version="8.0.4"  
```

<h2 align="center"> CollectionApp.WorkerKafka</h2>

>## Packages
The list of packages which is used:
```sh
 "Confluent.Kafka" Version="1.9.3"  
 "elastic.apm" Version="1.26.0"  
 "Microsoft.Extensions.Diagnostics.HealthChecks.EntityFrameworkCore" Version="8.0.7"  
 "Microsoft.Extensions.Hosting" Version="8.0.0"  
 "Microsoft.VisualStudio.Azure.Containers.Tools.Targets" Version="1.19.6"  
 "System.Text.Json" Version="8.0.4"  
```

<h2 align="center"> CollectionApp.WorkerSms</h2>

 Customers who will receive SMS are listed here.

>## Packages
The list of packages which is used:
```sh
 "Microsoft.Extensions.Diagnostics.HealthChecks.EntityFrameworkCore" Version="8.0.7"  
 "Microsoft.Extensions.Hosting" Version="8.0.0"  
```

<!--
Not exist:
   CollectionApp.WorkerPush
   CollectionApp.SmsWorker
   CollectionApp.DaprAdapter
   CollectionApp.Core.Domain
   CollectionApp.Infrastructure
-->
