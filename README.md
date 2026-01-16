# 🍽️ WasteFoodDonation

A full-stack web application that bridges the gap between food donors and receivers, helping reduce food waste by facilitating food donations. Built with **Angular 17** (Frontend) and **.NET 8 Web API** (Backend).

![.NET 8](https://img.shields.io/badge/.NET-8.0-512BD4?logo=dotnet)
![Angular](https://img.shields.io/badge/Angular-17-DD0031?logo=angular)
![SQL Server](https://img.shields.io/badge/SQL_Server-2019+-CC2927?logo=microsoftsqlserver)
![License](https://img.shields.io/badge/license-MIT-green)

---

## 📋 Table of Contents

- [Overview](#-overview)
- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Project Structure](#-project-structure)
- [Prerequisites](#-prerequisites)
- [Installation & Setup](#-installation--setup)
  - [Backend (API)](#backend-api)
  - [Frontend (DonateFood)](#frontend-donatefood)
- [API Documentation](#-api-documentation)
- [Database Schema](#-database-schema)
- [Contributing](#-contributing)

---

## 🌟 Overview

**WasteFoodDonation** is a platform designed to minimize food waste by connecting donors (restaurants, events, individuals with excess food) with receivers (NGOs, shelters, people in need). The application provides a seamless experience for:

- **Donors** to list available food items with details and expiration dates
- **Receivers** to browse and request food donations
- **Automated cleanup** of expired donations to maintain data integrity

---

## ✨ Features

### User Management
- 🔐 **Secure Authentication** - JWT-based authentication with ASP.NET Core Identity
- 📝 **User Registration** - Create accounts with email and phone verification
- 👤 **User Profiles** - Manage personal information and preferences

### Donation Management
- 🍕 **Create Donations** - List food items with type, description, and expiration date
- 📍 **Address Management** - Add pickup locations with full address details
- 📊 **Portfolio Tracking** - Track donation history per user
- ⏰ **Automatic Cleanup** - Background service removes expired donations

### Communication
- 📧 **Email Notifications** - SMTP integration for user notifications
- 📱 **Contact Information** - Share phone numbers for coordination

### User Interface
- 🏠 **Home Page** - Landing page with app information
- 📖 **About Us** - Learn about the platform's mission
- 📞 **Contact Us** - Reach out for support
- 🎯 **Donor Dashboard** - Manage your food donations
- 🤝 **Receiver Dashboard** - Browse available donations

---

## 🛠️ Tech Stack

### Backend (API)
| Technology | Version | Purpose |
|------------|---------|---------|
| .NET | 8.0 | Framework |
| ASP.NET Core Web API | 8.0 | REST API |
| Entity Framework Core | 8.0.7 | ORM |
| SQL Server | 2019+ | Database |
| ASP.NET Core Identity | 8.0.7 | Authentication |
| JWT Bearer | 8.0.7 | Token Authentication |
| Swashbuckle | 6.4.0 | Swagger/OpenAPI |
| Newtonsoft.Json | 13.0.3 | JSON Serialization |

### Frontend (DonateFood)
| Technology | Version | Purpose |
|------------|---------|---------|
| Angular | 17.3.0 | Framework |
| Angular Material | 17.3.10 | UI Components |
| Bootstrap | 5.3.2 | CSS Framework |
| ng-bootstrap | 16.0.0 | Bootstrap Components |
| RxJS | 7.8.0 | Reactive Extensions |
| TypeScript | 5.4.2 | Language |

---

## 📁 Project Structure

```
WasteFoodDonation/
│
├── API/                          # Backend - .NET 8 Web API
│   ├── api/
│   │   ├── Controllers/          # API endpoints
│   │   │   ├── AccountController.cs    # Auth (login/register)
│   │   │   ├── DonorController.cs      # Donor CRUD operations
│   │   │   ├── AddressController.cs    # Address management
│   │   │   ├── PortfolioController.cs  # User portfolios
│   │   │   └── EmailController.cs      # Email services
│   │   ├── Models/               # Entity models
│   │   │   ├── AppUser.cs        # User entity
│   │   │   ├── Donor.cs          # Donation entity
│   │   │   ├── Address.cs        # Address entity
│   │   │   ├── Portfolio.cs      # Portfolio entity
│   │   │   └── SmtpSettings.cs   # Email config
│   │   ├── Dtos/                 # Data Transfer Objects
│   │   ├── Interfaces/           # Service contracts
│   │   ├── Repositories/         # Data access layer
│   │   ├── Service/              # Business logic
│   │   ├── Mappers/              # Entity-DTO mappings
│   │   ├── Data/                 # Database context
│   │   ├── Migrations/           # EF Core migrations
│   │   ├── Program.cs            # Application entry point
│   │   └── appsettings.json      # Configuration
│   └── API.sln                   # Solution file
│
└── DonateFood/                   # Frontend - Angular 17
    ├── src/
    │   ├── app/
    │   │   ├── Content/          # Main app content
    │   │   │   ├── Donation/     # Donor components
    │   │   │   └── Navbar/       # Navigation & views
    │   │   │       ├── AppHome/  # Dashboard home
    │   │   │       └── Receiver/ # Receiver components
    │   │   ├── Login/            # Auth components
    │   │   │   ├── login/        # Login component
    │   │   │   └── register/     # Register component
    │   │   ├── home/             # Public pages
    │   │   │   ├── aboutus/      # About page
    │   │   │   └── contactus/    # Contact page
    │   │   ├── Services/         # Angular services
    │   │   │   ├── AuthServices/ # Authentication
    │   │   │   ├── DonorServices/# Donor operations
    │   │   │   └── PortfolioService/
    │   │   ├── app.routes.ts     # Routing config
    │   │   └── app.config.ts     # App configuration
    │   ├── assets/               # Static assets
    │   └── index.html            # Entry HTML
    ├── angular.json              # Angular CLI config
    └── package.json              # NPM dependencies
```

---

## 📌 Prerequisites

Before you begin, ensure you have the following installed:

- **[.NET 8 SDK](https://dotnet.microsoft.com/download/dotnet/8.0)** - Required for backend
- **[Node.js](https://nodejs.org/)** (v18 or later) - Required for frontend
- **[SQL Server](https://www.microsoft.com/sql-server/)** (2019+) or SQL Server Express
- **[Angular CLI](https://angular.io/cli)** - `npm install -g @angular/cli`
- **[Git](https://git-scm.com/)** - For version control

---

## 🚀 Installation & Setup

### Clone the Repository

```bash
git clone https://github.com/yourusername/WasteFoodDonation.git
cd WasteFoodDonation
```

### Backend (API)

1. **Navigate to the API directory**
   ```bash
   cd API/api
   ```

2. **Update the connection string** in `appsettings.json`:
   ```json
   {
     "ConnectionStrings": {
       "DefaultConnection": "server=YOUR_SERVER;database=Donation_db;trusted_connection=true;TrustServerCertificate=true"
     }
   }
   ```

3. **Configure JWT settings** in `appsettings.json`:
   ```json
   {
     "JWT": {
       "Issuer": "http://localhost:5246",
       "Audience": "http://localhost:5246",
       "SigningKey": "YOUR_SECRET_KEY_MIN_64_CHARACTERS"
     }
   }
   ```

4. **Configure SMTP settings** (optional) for email notifications:
   ```json
   {
     "SmtpSettings": {
       "Server": "smtp.gmail.com",
       "Port": 587,
       "SenderName": "Your Name",
       "SenderEmail": "your-email@gmail.com",
       "Username": "your-email@gmail.com",
       "Password": "your-app-password"
     }
   }
   ```

5. **Apply database migrations**
   ```bash
   dotnet ef database update
   ```

6. **Run the API**
   ```bash
   dotnet run
   ```
   
   The API will be available at: `http://localhost:5246`

### Frontend (DonateFood)

1. **Navigate to the frontend directory**
   ```bash
   cd DonateFood
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Start the development server**
   ```bash
   npm start
   ```
   
   The application will be available at: `http://localhost:4200`

---

## 📚 API Documentation

Once the API is running, access the Swagger UI at:
```
http://localhost:5246/swagger
```

### Available Endpoints

| Method | Endpoint | Description | Auth Required |
|--------|----------|-------------|---------------|
| `POST` | `/api/Account/register` | Register new user | ✅ |
| `POST` | `/api/Account/login` | User login | ✅ |
| `GET` | `/api/Account/{userId}` | Get user by ID | ✅ |
| `GET` | `/api/donor` | Get all donations | ✅ |
| `GET` | `/api/donor/{id}` | Get donation by ID | ✅ |
| `POST` | `/api/donor` | Create new donation | ✅ |
| `DELETE` | `/api/donor/{id}` | Delete donation | ✅ |
| `GET` | `/api/address` | Get all addresses | ✅ |
| `POST` | `/api/address` | Create address | ✅ |
| `GET` | `/api/portfolio` | Get user portfolio | ✅ |

---

## 🗄️ Database Schema

### Entity Relationships

```
┌─────────────┐       ┌─────────────┐       ┌─────────────┐
│   AppUser   │       │    Donor    │       │   Address   │
├─────────────┤       ├─────────────┤       ├─────────────┤
│ Id (PK)     │       │ Id (PK)     │       │ Id (PK)     │
│ UserName    │       │ FoodDetails │◄──────│ DonorId(FK) │
│ Email       │       │ FoodType    │       │ AppUserId   │
│ PhoneNumber │       │ Description │       │ AddressLine │
└──────┬──────┘       │ CreatedOn   │       │ State       │
       │              │ ExpDate     │       │ City        │
       │              └──────┬──────┘       │ Pincode     │
       │                     │              └─────────────┘
       │              ┌──────┴──────┐
       │              │  Portfolio  │
       │              ├─────────────┤
       └──────────────│ AppUserId   │
                      │ DonorId     │
                      └─────────────┘
```

### Key Models

| Model | Description |
|-------|-------------|
| **AppUser** | User account with Identity integration |
| **Donor** | Food donation listing with type and expiry |
| **Address** | Pickup location details |
| **Portfolio** | Links users to their donations |

---

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. **Fork the repository**
2. **Create a feature branch**
   ```bash
   git checkout -b feature/AmazingFeature
   ```
3. **Commit your changes**
   ```bash
   git commit -m 'Add some AmazingFeature'
   ```
4. **Push to the branch**
   ```bash
   git push origin feature/AmazingFeature
   ```
5. **Open a Pull Request**

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 📞 Support

If you have any questions or need help, please:
- Open an issue on GitHub
- Contact the maintainers

---

<p align="center">
  Made with ❤️ to reduce food waste and help those in need
</p>
