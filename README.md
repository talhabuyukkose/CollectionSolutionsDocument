<h1 align="center"> COLLECTION APP</h1>

This project is a software system designed to manage communication channels for a bank, ensuring payments from customers who have missed their payments. The system enables agent personnel to make automatic calls to customers and send notifications via SMS, email, and IVR.

> ## Documentation  

* [Features](#Features)  
* [Properties](#Properties)  
* [Goals](#Goals)
* [Installation](#Installation)
* CollectionAppCli
   * [Repository](https://github.com/sadeyazilim/SolutionCollectionApp/tree/Development/CollectionApp.Cli)
* [CollectionApp.Core](#collectionapp-core)
   * [Repository](https://github.com/sadeyazilim/SolutionCollectionApp/tree/Development/CollectionApp.Core)
   * [CollectionApp.Core.Domain](https://github.com/sadeyazilim/SolutionCollectionApp/tree/Development/CollectionApp.Core.Domain)
* [CollectionApp.Data](https://github.com/aysegulsum/CollectionSolutionsDocument/blob/main/CollectionData.md)  
   * [Repository](https://github.com/sadeyazilim/SolutionCollectionApp/tree/Development/CollectionApp.Data)
* [CollectionApp.Infrastructure](#Inf)
   * [Repository](https://github.com/sadeyazilim/SolutionCollectionApp/tree/Development/CollectionApp.Infrastructure)
* [CollectionApp.NUnit](#NU)
   * [Repository](https://github.com/sadeyazilim/SolutionCollectionApp/tree/Development/CollectionApp.NUnit)
* [CollectionApp.RestApi](https://github.com/aysegulsum/CollectionSolutionsDocument/blob/main/RestApi.md)
   <!--* [SetUp](https://github.com/aysegulsum/CollectionSolutionsDocument/blob/main/RestApi.md#-setup-and-run)-->
   * [Endpoints](https://github.com/aysegulsum/CollectionSolutionsDocument/blob/main/endpoints.md)
   * [Repository](https://github.com/sadeyazilim/SolutionCollectionApp/tree/Development/CollectionApp.RestApi)
* [CollectionApp.WorkerCti](https://github.com/aysegulsum/CollectionSolutionsDocument/blob/main/Workers.md#-collectionappworkercti)
   * [Repository](https://github.com/sadeyazilim/SolutionCollectionApp/tree/Development/CollectionApp.WorkerCti)
* [CollectionApp.WorkerEmail](https://github.com/aysegulsum/CollectionSolutionsDocument/blob/main/Workers.md#-collectionappworkeremail)
   * [Repository](https://github.com/sadeyazilim/SolutionCollectionApp/tree/Development/CollectionApp.WorkerEmail)
* [CollectionApp.WorkerImporter](https://github.com/aysegulsum/CollectionSolutionsDocument/blob/main/Workers.md#-collectionappworkerimporter)
   * [Repository](https://github.com/sadeyazilim/SolutionCollectionApp/tree/Development/CollectionApp.WorkerImporter)
* [CollectionApp.WorkerIvn](https://github.com/aysegulsum/CollectionSolutionsDocument/blob/main/Workers.md#-collectionappworkerivn)
   * [Repository](https://github.com/sadeyazilim/SolutionCollectionApp/tree/Development/CollectionApp.WorkerIvn)
* [CollectionApp.WorkerKafka](https://github.com/aysegulsum/CollectionSolutionsDocument/blob/main/Workers.md#-collectionappworkerkafka)
   * [Repository](https://github.com/sadeyazilim/SolutionCollectionApp/tree/Development/CollectionApp.WorkerKafka)
* [CollectionApp.WorkerSms](https://github.com/aysegulsum/CollectionSolutionsDocument/blob/main/Workers.md#-collectionappworkersms)
   * [Repository](https://github.com/sadeyazilim/SolutionCollectionApp/tree/Development/CollectionApp.WorkerSms)


> ## Features

- **Automatic Calls:** Allows agent personnel to make automatic calls to customers.
- **Notification Management:** Sends notifications to customers via SMS, email, and IVR.
- **Situation Management:** Guides bank personnel on the steps to take based on the customer's situation using the software.
- **Data Transfer:** Daily data transfers from the bank to the project.
- **Task Allocation:** Calculates daily tasks and directs the necessary work to agents.
- **Reporting:** Provides daily reports on the operations.


> ## Properties
* __.NET 8__ is used in this project as the primary development platform.
* __Onion Architecture__  is employed in this project to organize the codebase effectively. 
* __Redis__  is integrated into this project as a caching mechanism and data store.
* __Docker__  is used to streamline the development and deployment processes of the application.
* __Swagger__ is used for API documentation and testing.

> ## Goals

&nbsp; A company which cannot receive payments from customers and wants to reach customers at regular intervals through SMS, e-mail or call to inform them about the payment. This project is being developed to speed up this process.   
&nbsp; Customers who need to be reached to inform are classified according to how to contact them. E-mail, SMS and IVN calls are sent through the system. The customers to be reached by call are listed so that the bank can contact them one by one.

<h2 align="center" id="collectionapp-core"> CollectionApp.Core</h2>

&nbsp; Core is the central layer that contains the core business logic and rules, in other words, the heart of the project.  

>## Packages
The list of packages which is used:
```sh
 "StackExchange.Redis" Version="2.7.33" 
 "Serilog.Sinks.Async" Version="1.5.0" 
 "Microsoft.Extensions.Diagnostics.HealthChecks" Version="8.0.4"
 "Microsoft.AspNetCore.SignalR.Client" Version="8.0.4" 
 "AutoMapper" Version="13.0.1" 
 
```
> ## Installation

### Requirements

- .NET 8 SDK
- PostgreSQL server

### Steps

1. **Clone the repository:**
    ```bash
    git clone [https://github.com/username/project_name.git](https://github.com/sadeyazilim/SolutionCollectionApp.git)
    ```

2. **Navigate to the project directory:**
    ```bash
    cd .\CollectionApp.RestApi\
    ```

3. **Restore the .NET dependencies:**
    ```bash
    dotnet restore
    ```

4. **Set up the database:**
    - Update the `appsettings.json` file with your database connection string:
        ```json
        {
          "ConnectionStrings": {
             "CollectionDatabase": "UserID=postgres; Password=11111111; Host=localhost; Port=7632; Database=collappdb; Pooling=true;"
           }
        }
        ```

    - Apply the database migrations:
        ```bash
        dotnet ef migrations add firstmigration --startup-project --context CollectionDbContext
        ```

5. **Run the project:**
    ```bash
    dotnet run
    ```

### Additional Tools

- **Entity Framework Core:** Used for database operations.
- **ASP.NET Core:** For building the web API and handling requests.

## Usage

- **Initiate Automatic Calls:** 
    - [Steps to initiate automatic calls]

- **Send Notifications:**
    - [Steps to send notifications]

- **View Reports:**
    - [Steps to view reports]
<h2 align="center" id="Inf"> CollectionApp.Infrastructure</h2>


<h2 align="center" id="NU"> CollectionApp.NUnit</h2>

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

<!--
Not exist:
   CollectionApp.WorkerPush
   CollectionApp.SmsWorker
   CollectionApp.DaprAdapter
-->
