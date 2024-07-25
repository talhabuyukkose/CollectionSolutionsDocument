<h2 align="center" id="data"> CollectionApp.Data</h2>

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