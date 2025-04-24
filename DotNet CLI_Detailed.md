

## 🧱 PROJECT STRUCTURE & CREATION

### 🔨 Create New Projects with Templates
```bash
dotnet new console -n MyConsoleApp                     # Basic console app
dotnet new webapi -n MyApi                             # REST API project
dotnet new mvc -n MyMvcApp                             # ASP.NET Core MVC
dotnet new razor -n RazorPagesApp                      # Razor Pages
dotnet new classlib -n MyLibrary                       # Class library
dotnet new xunit -n MyTestProject                      # xUnit test project
dotnet new sln -n MySolution                           # Create a new solution
```

### 🗂️ Add/Remove Projects to/from a Solution
```bash
dotnet sln add path/to/project.csproj
dotnet sln remove path/to/project.csproj
```

---

## 📦 DEPENDENCY MANAGEMENT

### 🔍 Add, Remove, List Packages
```bash
dotnet add package Dapper                             # Add NuGet package
dotnet add package Microsoft.EntityFrameworkCore.SqlServer
dotnet remove package Dapper                          # Remove package
dotnet list package                                   # List all installed
dotnet list package --outdated                        # Check for updates
dotnet list package --vulnerable                      # Show known vulnerabilities
```

---

## 🧰 BUILD & RUN

### 🔧 Compile
```bash
dotnet build                                           # Build current project
dotnet build MyApp.csproj -c Release                   # Build with config
dotnet build --no-restore                              # Skip restore
```

### ▶️ Run App
```bash
dotnet run                                             # Runs current
dotnet run --project MyApp.csproj --configuration Release
```

---

## ♻️ RESTORE, CLEAN, UPDATE

```bash
dotnet restore                                         # Restore all packages
dotnet clean                                           # Clean the build artifacts
dotnet update                                          # Update SDK (preview)
```

---

## 🔬 TESTING (xUnit, MSTest, NUnit)

```bash
dotnet new xunit -n UnitTestApp
dotnet add reference ../MyApp/MyApp.csproj
dotnet test                                            # Run tests
dotnet test --filter FullyQualifiedName~MyTestClass   # Filter specific test class
```

---

## 🛠️ EF CORE IN-DEPTH

### 📦 Install EF Core Tools
```bash
dotnet tool install --global dotnet-ef
dotnet tool update -g dotnet-ef
```

### ⚙️ Migrations & DB Commands
```bash
dotnet ef migrations add InitialCreate
dotnet ef migrations remove
dotnet ef database update                             # Apply latest migration
dotnet ef database drop --force                       # Drop DB
dotnet ef dbcontext list                              # List DB contexts
dotnet ef migrations list                             # List applied migrations
dotnet ef dbcontext scaffold "YourConnectionString" Microsoft.EntityFrameworkCore.SqlServer -o Models
```

---

## 📁 PROJECT REFERENCES & FILES

### ➕ Reference Project
```bash
dotnet add reference ../MyLibrary/MyLibrary.csproj
```

### 🔍 View Project References
```bash
dotnet list reference
```

---

## 📤 PUBLISH & DEPLOY

### 🔧 Basic Publish
```bash
dotnet publish -c Release -o ./publish
```

### 🔧 Self-Contained Publish
```bash
dotnet publish -r win-x64 --self-contained true -c Release -o ./publish
```

### 🔧 Trim & Optimize
```bash
dotnet publish -c Release -r win-x64 --self-contained true /p:PublishTrimmed=true
```

| Option                        | Description                       |
|------------------------------|-----------------------------------|
| `--self-contained`           | Include .NET runtime              |
| `--runtime win-x64`          | Publish for Windows 64-bit        |
| `/p:PublishTrimmed=true`     | Reduce unused code                |

---

## 🧱 GLOBAL TOOLS

### 🧰 Install, List, Update Tools
```bash
dotnet tool install -g dotnet-ef
dotnet tool list -g
dotnet tool update -g dotnet-ef
```

---

## 🔎 SDK INFORMATION

```bash
dotnet --version                                    # Current SDK version
dotnet --info                                       # Environment info
dotnet sdk check                                    # Check for available SDK updates
```

---

## 🧰 TEMPLATE MANAGEMENT

```bash
dotnet new list                                     # Show all templates
dotnet new -i MyTemplate::1.0.0                     # Install custom template
dotnet new -u MyTemplate                            # Uninstall template
dotnet new <template> --help                        # Template usage help
```

---

## 🧪 ADVANCED DEV UTILITIES

### 🔁 Watch for File Changes
```bash
dotnet watch run                                    # Auto-restarts app on changes
dotnet watch test                                   # Auto-runs tests on changes
```

### 📤 Global JSON
```bash
dotnet new globaljson --sdk-version 7.0.203         # Pin project to SDK version
```

---

## 🔍 MORE TOOLS WORTH EXPLORING

| Tool                      | Description                                |
|---------------------------|--------------------------------------------|
| `dotnet-dump`             | Collect and analyze dumps                  |
| `dotnet-gcdump`           | Get GC dump for live apps                  |
| `dotnet-trace`            | Performance tracing                        |
| `dotnet-counters`         | Monitor CPU, memory, GC, etc.              |
| `dotnet-watch`            | File watcher for .NET projects             |

---
