# Pronia - E-Commerce Web Application

A modern, full-featured e-commerce platform built with ASP.NET Core 8.0 MVC.

---

## ⚠️ IMPORTANT: Database Setup Required Before Running

**Before you run the project, you must first import the provided database backup file (`Pronia.bacpac`) to your SQL Server. The application will NOT work without this step.**

---

## 🗄️ Database Setup (BACPAC) - **MUST DO FIRST**

The project includes a ready-to-use database backup file (`Pronia.bacpac`) in the root folder.

### Prerequisites
- SQL Server Management Studio (SSMS) 18.0 or later
- SQL Server (LocalDB, Express, or full version)

### Step 1: Import Database (DO THIS BEFORE RUNNING)

1. Open **SQL Server Management Studio**
2. Connect to your SQL Server instance:
   - `(localdb)\MSSQLLocalDB` (for LocalDB)
   - `localhost` or `.\SQLEXPRESS` (for full SQL Server)
3. In **Object Explorer**, right-click on **Databases**
4. Select **Import Data-tier Application...**
5. In the wizard:
   - Select **Import from local disk**
   - Click **Browse** and select `Pronia.bacpac` from the project root folder
   - Set **Database name:** `ProniaDb`
   - Click **Next** and then **Finish**
6. Wait for the import to complete (may take 1-2 minutes)

### Step 2: Verify Database Import

```sql
-- Check if database was created
SELECT name FROM sys.databases WHERE name = 'ProniaDb';

-- Check if tables exist
USE ProniaDb;
SELECT TABLE_NAME FROM INFORMATION_SCHEMA.TABLES;
```

### Step 3: Update Connection String

After importing the database, update `appsettings.json` with your connection string:

```json
{
  "ConnectionStrings": {
    "Default": "Server=(localdb)\\MSSQLLocalDB;Database=ProniaDb;Trusted_Connection=True;MultipleActiveResultSets=true;TrustServerCertificate=true;"
  }
}
```

> **Note:** If you are using a different SQL Server instance, change the Server value:
> - `Server=localhost` (for default instance)
> - `Server=.\SQLEXPRESS` (for SQL Express)
> - `Server=YOUR_PC_NAME\SQLEXPRESS` (for named instance)

---

## 🚀 Running the Project (After Database Setup)

1. **Restore dependencies:**
   ```bash
   dotnet restore
   ```

2. **Run the application:**
   ```bash
   dotnet run
   ```

3. **Access the application:**
   - Open browser: `https://localhost:7237`
   - Login with admin credentials: `admin@pronia.com` / `Admin123!`

---

## 📋 Features

- **User Management:** Registration, login, password reset (with Identity)
- **Product Catalog:** Add, edit, delete products and filter by categories
- **Shopping Cart & Orders:** Users can add products to cart and place orders
- **Admin Panel:** Manage products, categories, users, and orders
- **Contact Form:** Collect messages from users via contact page
- **Responsive Design:** Proper display on all devices (mobile, tablet, desktop)

---

## 🛠️ Technologies Used

| Category | Technology |
|---|---|
| **Backend** | ASP.NET Core 8.0 |
| **ORM** | Entity Framework Core 8.0 |
| **Database** | SQL Server |
| **Auth** | ASP.NET Core Identity |
| **Frontend** | HTML5, CSS3, Bootstrap / Tailwind CSS |
| **JavaScript** | jQuery, AJAX |
| **Icons** | Font Awesome 6 |

---

## ⚙️ Configuration

Full `appsettings.json` example:

```json
{
  "ConnectionStrings": {
    "Default": "Server=(localdb)\\MSSQLLocalDB;Database=ProniaDb;Trusted_Connection=True;MultipleActiveResultSets=true;TrustServerCertificate=true;"
  },
  "AppUrl": "https://localhost:7237"
}
```

---

## 📁 Project Structure

```text
Pronia/
├── Areas/Admin/          # Admin panel
├── Controllers/          # MVC Controllers
├── Views/                # Razor Views
├── Models/               # Data models
├── Data/                 # AppDbContext
├── Services/             # Services
├── wwwroot/              # Static files
├── Migrations/           # EF Core migrations
├── Program.cs            # Application entry point
├── appsettings.json      # Configuration
└── Pronia.bacpac         # Database backup (IMPORT FIRST!)
```

---

## 📸 Screenshots

| Homepage & Product Details | Admin Panel & Cart |
| :---: | :---: |
| <img src="https://github.com/user-attachments/assets/f326f9ff-639b-4d9c-8559-1a8a4fcb0610" width="100%" /> | <img src="https://github.com/user-attachments/assets/a188469b-6a4a-4b64-ba03-62030c11f255" width="100%" /> |
| <img src="https://github.com/user-attachments/assets/2b4f004b-6cda-49b5-a4a3-a7f6fd42dc59" width="100%" /> | <img src="https://github.com/user-attachments/assets/89b5d8db-95c4-409b-a124-7e20b7bbc03e" width="100%" /> |
| <img src="https://github.com/user-attachments/assets/09cca2d2-a313-4772-b175-7fd7c7855103" width="100%" /> | |

---

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 👨‍💻 Developer

**Orkhan Mirzeyev**
- **GitHub:** [@Orkhan0919](https://github.com/Orkhan0919)
- **Email:** mirzeyev005orxan@gmail.com

---

## 🙏 Acknowledgments

- ASP.NET Core
- Entity Framework Core
- SQL Server
- Tailwind CSS / Bootstrap

⭐ **Star this repository if you find it useful!**
