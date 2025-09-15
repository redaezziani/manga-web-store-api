# 📚 Manga Web Store API

A modern, feature-rich REST API for managing a manga web store built with NestJS and TypeScript.

[![License](https://img.shields.io/badge/license-UNLICENSED-red.svg)](LICENSE)
[![Node.js](https://img.shields.io/badge/node-%3E%3D18.0.0-brightgreen.svg)](https://nodejs.org/)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](https://github.com/redaezziani/manga-web-store-api/pulls)

## 🏷️ Technology Stack

![NestJS](https://img.shields.io/badge/nestjs-%23E0234E.svg?style=for-the-badge&logo=nestjs&logoColor=white)
![TypeScript](https://img.shields.io/badge/typescript-%23007ACC.svg?style=for-the-badge&logo=typescript&logoColor=white)
![Node.js](https://img.shields.io/badge/node.js-6DA55F?style=for-the-badge&logo=node.js&logoColor=white)
![Prisma](https://img.shields.io/badge/Prisma-3982CE?style=for-the-badge&logo=Prisma&logoColor=white)
![MariaDB](https://img.shields.io/badge/MariaDB-003545?style=for-the-badge&logo=mariadb&logoColor=white)
![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white)
![JWT](https://img.shields.io/badge/JWT-black?style=for-the-badge&logo=JSON%20web%20tokens)
![Swagger](https://img.shields.io/badge/-Swagger-%23Clojure?style=for-the-badge&logo=swagger&logoColor=white)
![Cloudinary](https://img.shields.io/badge/Cloudinary-3448C5?style=for-the-badge&logo=cloudinary&logoColor=white)
![ESLint](https://img.shields.io/badge/ESLint-4B3263?style=for-the-badge&logo=eslint&logoColor=white)
![Prettier](https://img.shields.io/badge/prettier-%23F7B93E.svg?style=for-the-badge&logo=prettier&logoColor=black)
![Jest](https://img.shields.io/badge/-jest-%23C21325?style=for-the-badge&logo=jest&logoColor=white)

## ✨ Features

### 🔐 Authentication & Authorization
- **JWT-based authentication** with Passport.js
- **Role-based access control** (Admin, Moderator, User)
- **Email verification** system
- **Password reset** functionality
- **Login history** tracking with device/location info
- **Two-factor authentication** support
- **Account status management** (Active, Suspended, etc.)

### 📖 Manga Management
- **Manga catalog** with detailed information (title, author, description)
- **Category management** with multi-language support (EN/AR)
- **Volume management** with pricing, stock, and availability
- **Cover image** and preview image uploads
- **Advanced search** and filtering capabilities

### 🛒 E-commerce Features
- **Shopping cart** functionality
- **Wishlist** system for favorite manga
- **Order management** with multiple status tracking
- **Review and rating** system for manga
- **Inventory management** with stock tracking
- **Discount system** for volumes

### 🌐 Additional Features
- **Multi-language support** (English/Arabic)
- **File upload** integration with Cloudinary
- **Email notifications** via Resend
- **API documentation** with Swagger/OpenAPI
- **Pagination** for large datasets
- **Data validation** with class-validator
- **Comprehensive logging** and error handling

## 🚀 Quick Start

### Prerequisites

- **Node.js** (v18 or higher)
- **npm** or **yarn**
- **Docker** and **Docker Compose**
- **MariaDB** (or use Docker Compose)

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/redaezziani/manga-web-store-api.git
   cd manga-web-store-api
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
   docker-compose up -d mariadb
   ```

5. **Set up the database**
   ```bash
   npx prisma generate
   npx prisma db push
   npx prisma db seed
   ```

6. **Start the development server**
   ```bash
   npm run start:dev
   ```

The API will be available at `http://localhost:7000`

## 📊 API Documentation

Once the server is running, you can access the interactive API documentation at:
- **Swagger UI**: `http://localhost:7000/api/docs`

## 🛠️ Development

### Available Scripts

```bash
# Development
npm run start:dev          # Start with file watching
npm run start:debug        # Start in debug mode

# Building
npm run build              # Build the application
npm run start:prod         # Start production build

# Testing
npm run test               # Run unit tests
npm run test:watch         # Run tests in watch mode
npm run test:cov           # Run tests with coverage
npm run test:e2e           # Run end-to-end tests

# Code Quality
npm run lint               # Run ESLint
npm run format             # Format code with Prettier

# Database
npx prisma generate        # Generate Prisma client
npx prisma db push         # Push schema to database
npx prisma db seed         # Seed database with sample data
npx prisma studio          # Open Prisma Studio
```

### Project Structure

```
src/
├── auth/                  # Authentication module
├── cart/                  # Shopping cart functionality
├── common/                # Shared utilities and services
├── database/              # Database configuration
├── integration/           # External service integrations
├── manga/                 # Manga and category management
├── order/                 # Order management
├── smtp/                  # Email service
├── storage/               # File upload and storage
├── volume/                # Manga volume management
├── wishlist/              # User wishlist functionality
├── app.module.ts          # Main application module
└── main.ts                # Application entry point
```

## 🔧 Configuration

### Environment Variables

Create a `.env` file with the following variables:

```env
# Database
DATABASE_URL="mysql://user:password@localhost:3306/mangastore"

# JWT
JWT_SECRET="your-jwt-secret"
JWT_EXPIRES_IN="7d"

# Cloudinary (for file uploads)
CLOUDINARY_CLOUD_NAME="your-cloud-name"
CLOUDINARY_API_KEY="your-api-key"
CLOUDINARY_API_SECRET="your-api-secret"

# Email (Resend)
RESEND_API_KEY="your-resend-api-key"
FROM_EMAIL="noreply@yourdomain.com"

# Application
PORT=7000
```

## 🐳 Docker Deployment

The project includes Docker Compose configuration for easy deployment:

```bash
# Start all services
docker-compose up -d

# View logs
docker-compose logs -f

# Stop services
docker-compose down
```

## 🧪 Testing

The project uses Jest for testing. Test files are located alongside source files with `.spec.ts` extension.

```bash
# Run all tests
npm run test

# Run tests with coverage
npm run test:cov

# Run e2e tests
npm run test:e2e
```

## 📄 API Endpoints

### Authentication
- `POST /api/v1/auth/register` - User registration
- `POST /api/v1/auth/login` - User login
- `POST /api/v1/auth/refresh` - Refresh JWT token
- `POST /api/v1/auth/forgot-password` - Request password reset

### Manga Management
- `GET /api/v1/manga` - Get all manga with pagination
- `GET /api/v1/manga/:id` - Get manga by ID
- `POST /api/v1/manga` - Create new manga (Admin)
- `PUT /api/v1/manga/:id` - Update manga (Admin)
- `DELETE /api/v1/manga/:id` - Delete manga (Admin)

### Categories
- `GET /api/v1/manga/categories` - Get all categories
- `POST /api/v1/manga/categories` - Create category (Admin)

### Cart & Orders
- `GET /api/v1/cart` - Get user cart
- `POST /api/v1/cart/items` - Add item to cart
- `POST /api/v1/orders` - Create order from cart
- `GET /api/v1/orders` - Get user orders

For complete API documentation, visit the Swagger UI when the server is running.

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### Development Guidelines

- Follow TypeScript best practices
- Use ESLint and Prettier for code formatting
- Write tests for new features
- Update documentation when needed
- Follow conventional commit messages

## 📝 License

This project is licensed under the [UNLICENSED](LICENSE) license.

## 👨‍💻 Author

**Reda Ezziani**
- GitHub: [@redaezziani](https://github.com/redaezziani)

## 🙏 Acknowledgments

- [NestJS](https://nestjs.com/) - A progressive Node.js framework
- [Prisma](https://www.prisma.io/) - Next-generation ORM for Node.js
- [MariaDB](https://mariadb.org/) - Reliable and performant database
- [Cloudinary](https://cloudinary.com/) - Image and video management
- [Resend](https://resend.com/) - Email delivery service

---

⭐ **Star this repository if you find it helpful!**