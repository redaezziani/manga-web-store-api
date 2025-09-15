# 📚 Manga Web Store

A modern, full-featured manga e-commerce platform built with NestJS, providing a comprehensive solution for manga enthusiasts to browse, purchase, and manage their manga collections.

## 🚀 Technology Stack

![NestJS](https://img.shields.io/badge/nestjs-%23E0234E.svg?style=for-the-badge&logo=nestjs&logoColor=white)
![TypeScript](https://img.shields.io/badge/typescript-%23007ACC.svg?style=for-the-badge&logo=typescript&logoColor=white)
![Prisma](https://img.shields.io/badge/Prisma-3982CE?style=for-the-badge&logo=Prisma&logoColor=white)
![MySQL](https://img.shields.io/badge/mysql-%2300f.svg?style=for-the-badge&logo=mysql&logoColor=white)
![MariaDB](https://img.shields.io/badge/MariaDB-003545?style=for-the-badge&logo=mariadb&logoColor=white)
![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white)
![JWT](https://img.shields.io/badge/JWT-black?style=for-the-badge&logo=JSON%20web%20tokens)
![Swagger](https://img.shields.io/badge/-Swagger-%23Clojure?style=for-the-badge&logo=swagger&logoColor=white)
![Jest](https://img.shields.io/badge/-jest-%23C21325?style=for-the-badge&logo=jest&logoColor=white)
![ESLint](https://img.shields.io/badge/ESLint-4B3263?style=for-the-badge&logo=eslint&logoColor=white)
![Prettier](https://img.shields.io/badge/prettier-%23F7B93E.svg?style=for-the-badge&logo=prettier&logoColor=black)
![Cloudinary](https://img.shields.io/badge/Cloudinary-3448C5?style=for-the-badge&logo=Cloudinary&logoColor=white)

## ✨ Features

### 🔐 Authentication & Authorization
- User registration and login with JWT authentication
- Email verification system
- Password reset functionality
- Role-based access control (User, Admin, Moderator)
- Login history tracking
- Two-factor authentication support

### 📖 Manga Management
- Comprehensive manga catalog with categories
- Multi-language support (English/Arabic)
- Volume management with preview images
- Advanced search and filtering
- Category-based organization
- Stock management

### 🛒 E-commerce Functionality
- Shopping cart management
- Wishlist functionality
- Order processing and tracking
- Secure checkout process
- Order history and status tracking
- Inventory management

### 🎨 Additional Features
- File upload with Cloudinary integration
- Email notifications via SMTP
- Excel data import/export
- RESTful API with Swagger documentation
- Comprehensive error handling
- Data validation with class-validator

## 🏗️ Architecture

The application follows a modular architecture built with NestJS:

```
src/
├── auth/           # Authentication & authorization
├── cart/           # Shopping cart management
├── common/         # Shared utilities and DTOs
├── database/       # Database connection and Prisma service
├── integration/    # External integrations (Excel, etc.)
├── manga/          # Manga catalog management
├── order/          # Order processing
├── smtp/           # Email service
├── storage/        # File upload and storage
├── volume/         # Manga volume management
└── wishlist/       # User wishlist functionality
```

## 🚀 Quick Start

### Prerequisites

- Node.js (v18 or higher)
- npm or yarn
- Docker and Docker Compose
- MariaDB/MySQL database

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/redaezziani/manga-web-store.git
   cd manga-web-store
   ```

2. **Install dependencies**
   ```bash
   npm install --legacy-peer-deps
   ```

3. **Set up environment variables**
   ```bash
   cp .env.example .env
   # Edit .env with your configuration
   ```

4. **Start the database**
   ```bash
   docker-compose up -d
   ```

5. **Run database migrations**
   ```bash
   npx prisma migrate dev
   npx prisma generate
   ```

6. **Seed the database**
   ```bash
   npm run seed
   ```

7. **Start the application**
   ```bash
   # Development
   npm run start:dev

   # Production
   npm run start:prod
   ```

## 🗃️ Database Schema

The application uses Prisma ORM with the following main entities:

- **User Management**: Users, Email Verification, Password Reset, Login History
- **Manga Catalog**: Manga, Categories, Volumes, Preview Images
- **E-commerce**: Cart, Cart Items, Orders, Order Items, Wishlist
- **Reviews**: User reviews and ratings

## 📚 API Documentation

Once the application is running, visit:
- **Swagger UI**: `http://localhost:7000/api/docs`
- **API Base URL**: `http://localhost:7000/api/v1`

## 🧪 Testing

```bash
# Run unit tests
npm run test

# Run e2e tests
npm run test:e2e

# Run tests with coverage
npm run test:cov
```

## 🎨 Code Quality

```bash
# Lint code
npm run lint

# Format code
npm run format
```

## 🌍 Environment Variables

Key environment variables to configure:

```env
# Database
DATABASE_URL="mysql://manga_user:userpass123@localhost:3306/mangastore"

# JWT
JWT_SECRET="your-super-secret-jwt-key"
JWT_EXPIRES_IN="1h"

# SMTP (for email)
SMTP_HOST="your-smtp-host"
SMTP_PORT=587
SMTP_USER="your-email"
SMTP_PASS="your-password"

# Cloudinary (for file uploads)
CLOUDINARY_CLOUD_NAME="your-cloud-name"
CLOUDINARY_API_KEY="your-api-key"
CLOUDINARY_API_SECRET="your-api-secret"

# Application
PORT=7000
```

## 🐳 Docker Deployment

The project includes Docker configuration for easy deployment:

```bash
# Start services
docker-compose up -d

# View logs
docker-compose logs -f

# Stop services
docker-compose down
```

## 📂 Project Structure

```
manga-web-store/
├── prisma/                 # Database schema and migrations
├── src/                    # Source code
├── test/                   # Test files
├── docker-compose.yml      # Docker services configuration
├── package.json           # Dependencies and scripts
└── README.md              # Project documentation
```

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the UNLICENSED License.

## 👥 Support

For support and questions:
- Create an issue in the GitHub repository
- Contact the development team

---

**Happy coding! 🚀📚**