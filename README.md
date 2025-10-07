# CLDV6212 Assessment 2 – Azure MVC and Functions Solution

This repository contains both **Part 1 (ASP.NET Core MVC Web App)** and **Part 2 (Azure Functions App)** for the CLDV6212 Practical Assessment. The project demonstrates full integration between an MVC front-end and Azure serverless backend services.

---

## 📘 Project Overview

The **ABC Retailers** solution showcases the use of Microsoft Azure cloud services for a retail management system.
It includes:

* An **ASP.NET Core MVC Web Application** for user interaction and CRUD operations.
* An **Azure Functions App** that handles serverless operations using **Table**, **Blob**, **Queue**, and **File** storage.

This aligns with the assessment brief’s outcomes for cloud integration, serverless architecture, and distributed design.

---

## 🧩 Solution Structure

```
CLDV6212_Solution/
│
├── ABCRetailers.WebApp/              # Part 1 - MVC Front-End
│   ├── Controllers/
│   ├── Models/
│   ├── Services/
│   ├── Views/
│   ├── wwwroot/
│   ├── appsettings.json
│   └── Program.cs
│
└── FunctionsApp/                     # Part 2 - Azure Functions Back-End
    ├── Functions/
    │   ├── CustomersFunction.cs
    │   ├── ProductsFunction.cs
    │   ├── OrdersFunction.cs
    │   ├── OrdersQueueTrigger.cs
    │   └── UploadsFunction.cs
    ├── Helpers/
    │   ├── HttpJson.cs
    │   ├── MultipartHelper.cs
    │   └── Map.cs
    ├── Models/
    │   └── ApiModels.cs
    ├── Entities/
    │   └── TableEntities.cs
    ├── Services/
    │   ├── TableService.cs
    │   ├── BlobService.cs
    │   ├── QueueService.cs
    │   └── FileService.cs
    ├── local.settings.json
    ├── host.json
    ├── FunctionsApp.csproj
    └── README.txt
```

---

## 🧱 Technologies Used

* **.NET 8 (ASP.NET Core MVC & Azure Functions Isolated Worker)**
* **Azure Storage Services:**

  * Table Storage
  * Blob Storage
  * Queue Storage
  * File Share
* **Azure Functions**
* **Azure Portal & Storage Explorer**
* **Visual Studio 2022 / VS Code**
* **C# / JSON / HTTP / REST**

---

## ⚙️ Configuration

### 1. Environment Variables / local.settings.json

In both projects, set your Azure Storage connection string and constants:

```json
{
  "IsEncrypted": false,
  "Values": {
    "AzureWebJobsStorage": "<your-connection-string>",
    "StorageConnectionString": "<your-connection-string>",
    "FUNCTIONS_WORKER_RUNTIME": "dotnet-isolated",
    "CustomersTableName": "Customers",
    "ProductsTableName": "Products",
    "OrdersTableName": "Orders",
    "BlobContainerName": "product-images",
    "QueueName": "OrdersQueue",
    "FileShareName": "abcfileshare"
  }
}
```

In the MVC app’s **appsettings.json**:

```json
{
  "ConnectionStrings": {
    "AzureStorage1": "<your-connection-string>"
  },
  "FunctionsApiBaseUrl": "http
```
