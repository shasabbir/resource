## ⚙️ Setup & Initialization

### 🟢 Create a New Project
```bash
dotnet new console -n MyApp              # Console app
dotnet new webapi -n MyApi               # Web API
dotnet new mvc -n MyMvcApp               # MVC app
dotnet new classlib -n MyLibrary         # Class library
dotnet new sln -n MySolution             # Create solution file
dotnet new list                          # Get list of templates
```

### 🟢 Add Project to Solution
```bash
dotnet sln MySolution.sln add MyApp/MyApp.csproj
```

---

## 📦 Package Management

### 🔵 Add Package
```bash
dotnet add package <PackageName>
dotnet add package Newtonsoft.Json --version 13.0.1
```

### 🔵 List Installed Packages
```bash
dotnet list package
```

### 🔵 Remove Package
```bash
dotnet remove package <PackageName>
```

---

## 🛠️ Build & Run

### 🔧 Build Project
```bash
dotnet build                           # Builds current project
dotnet build MyApp.csproj              # Builds specific project
```

### ▶️ Run Project
```bash
dotnet run                             # Runs current project
dotnet run --project MyApp.csproj      # Runs specific project
```

---

## 🧪 Testing

### 🔍 Create Test Project
```bash
dotnet new xunit -n MyTests
dotnet add reference ../MyApp/MyApp.csproj
```

### ✅ Run Tests
```bash
dotnet test
```

---

## 🧱 Project & Solution Management

### 📂 Restore Dependencies
```bash
dotnet restore
```

### 🔍 List Templates
```bash
dotnet new list
```

### 📝 Update Project SDK
```bash
dotnet new globaljson --sdk-version 7.0.100
```

---

## 🌍 Publish & Deployment

### 📦 Publish for Deployment
```bash
dotnet publish -c Release -o ./publish
dotnet publish -r win-x64 --self-contained true
```

| Option | Description |
|--------|-------------|
| `-c Release` | Use release configuration |
| `-o <path>` | Output directory |
| `-r <RID>` | Runtime Identifier (e.g., win-x64, linux-x64) |
| `--self-contained` | Bundle .NET runtime |

---

## 🧾 Tooling & Templates

### 🛠️ Install Global Tool
```bash
dotnet tool install -g dotnet-ef
```

### 🧼 Update Tool
```bash
dotnet tool update -g dotnet-ef
```

### 📜 List Tools
```bash
dotnet tool list -g
```

---

## 🗃️ Entity Framework Core (EF Core)

### ➕ Add EF Core
```bash
dotnet add package Microsoft.EntityFrameworkCore.SqlServer
dotnet add package Microsoft.EntityFrameworkCore.Tools
```

### 🧱 Migrations
```bash
dotnet ef migrations add InitialCreate
dotnet ef database update
dotnet ef database drop
```

---

## 🧰 Advanced

### 🔎 Project Info
```bash
dotnet --info                         # Show installed SDK info
dotnet list reference                 # List project references
dotnet list package --vulnerable      # Check package vulnerabilities
```

### 🧪 Benchmarking with BenchmarkDotNet
```bash
dotnet add package BenchmarkDotNet
```

---

## ⚙️ Common Options
| Option | Description |
|--------|-------------|
| `-n` or `--name` | Name the project |
| `-o` or `--output` | Output directory |
| `--no-restore` | Skip restoring packages |
| `--no-build` | Skip build step |
| `-v` or `--verbosity` | Set verbosity: quiet, minimal, normal, detailed, diagnostic |

