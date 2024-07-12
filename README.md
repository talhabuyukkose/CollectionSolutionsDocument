<h1 align="center"> COLLECTION SOLUTIONS</h1>

> ## Properties
* __.NET 8__ is used in this project as the primary development platform.
* __MVC Architecture__  is employed in this project to organize the codebase effectively. 
* __Redis__  is integrated into this project as a caching mechanism and data store. 

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
-->
