# 💰 Personal Finance Dashboard

A modern, full-stack web application for comprehensive personal finance management. Track your income, expenses, and account balances in one centralized dashboard with secure authentication and real-time updates.

![Next.js](https://img.shields.io/badge/Next.js-15.4.1-black?style=flat-square&logo=next.js)
![TypeScript](https://img.shields.io/badge/TypeScript-5.0-blue?style=flat-square&logo=typescript)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-14+-blue?style=flat-square&logo=postgresql)
![Prisma](https://img.shields.io/badge/Prisma-6.11.1-2D3748?style=flat-square&logo=prisma)
![Vercel](https://img.shields.io/badge/Deployed%20on-Vercel-black?style=flat-square&logo=vercel)

## 🌟 Features

### 👤 **User Management**
- **Secure Registration & Login** - JWT-based authentication with bcrypt password hashing
- **User Profiles** - Personalized settings with currency and timezone preferences
- **Session Management** - Secure token-based sessions with automatic expiration

### 🏦 **Account Management**
- **Multiple Account Types** - Support for checking, savings, credit, and investment accounts
- **Real-time Balance Tracking** - Automatic balance calculations based on transactions
- **Account Overview** - Visual dashboard showing all account balances and types
- **Account Status Management** - Enable/disable accounts as needed

### 💸 **Transaction Tracking**
- **Comprehensive Transaction Types** - Income, expenses, transfers, and refunds
- **Category Organization** - Organize transactions by custom categories
- **Transaction History** - Complete audit trail with timestamps
- **Balance Updates** - Automatic account balance adjustments
- **Date Tracking** - Detailed transaction dating system

### 📊 **Dashboard & Analytics**
- **Unified Dashboard** - All accounts and recent transactions in one view
- **Real-time Updates** - Live balance and transaction updates
- **Financial Overview** - Quick insights into spending patterns
- **Responsive Design** - Works seamlessly on desktop and mobile

## 🛠 Tech Stack

### **Frontend**
- **[Next.js 15.4.1](https://nextjs.org)** - React framework with App Router
- **[React 19](https://react.dev)** - Modern React with latest features
- **[TypeScript](https://www.typescriptlang.org)** - Type-safe JavaScript
- **[Tailwind CSS](https://tailwindcss.com)** - Utility-first CSS framework

### **Backend**
- **[Next.js API Routes](https://nextjs.org/docs/app/building-your-application/routing/route-handlers)** - Serverless API endpoints
- **[Prisma ORM](https://www.prisma.io)** - Type-safe database access
- **[PostgreSQL](https://www.postgresql.org)** - Robust relational database
- **[bcryptjs](https://github.com/dcodeIO/bcrypt.js)** - Password hashing
- **[jsonwebtoken](https://github.com/auth0/node-jsonwebtoken)** - JWT authentication

### **Database Schema**
- **Users** - Authentication and profile management
- **Accounts** - Multiple account types with balance tracking
- **Transactions** - Comprehensive transaction logging
- **Enums** - Type-safe account and transaction categories

### **Deployment & Infrastructure**
- **[Vercel](https://vercel.com)** - Serverless deployment platform
- **[Neon](https://neon.tech)** - Serverless PostgreSQL database
- **[GitHub](https://github.com)** - Version control and CI/CD

## 🚀 Live Demo

**Production URL:** [https://finance-dashboard-1herxsg9a-prahlaads-projects.vercel.app](https://finance-dashboard-1herxsg9a-prahlaads-projects.vercel.app)

## 📁 Project Structure

```
finance-dashboard/
├── src/
│   └── app/
│       ├── api/                 # API Routes
│       │   ├── auth/login/      # Authentication endpoints
│       │   ├── users/           # User management
│       │   ├── accounts/        # Account CRUD operations
│       │   ├── transactions/    # Transaction management
│       │   └── me/              # User profile
│       ├── dashboard/           # Dashboard page
│       ├── signup/              # Registration page
│       ├── lib/
│       │   ├── components/      # Reusable React components
│       │   ├── types/           # TypeScript type definitions
│       │   └── enums/           # Application enums
│       ├── layout.tsx           # Root layout component
│       └── page.tsx             # Login page
├── prisma/
│   ├── schema.prisma           # Database schema
│   └── migrations/             # Database migrations
├── lib/
│   └── prisma.ts               # Prisma client configuration
├── public/                     # Static assets
└── package.json                # Dependencies and scripts
```

## 🏗 Installation & Setup

### Prerequisites
- **Node.js** 18+
- **npm** or **yarn**
- **PostgreSQL** 14+ (for local development)

### 1. Clone the Repository
```bash
git clone https://github.com/prahlaadr/finance-dashboard.git
cd finance-dashboard
```

### 2. Install Dependencies
```bash
npm install
```

### 3. Environment Configuration
Create a `.env.local` file in the root directory:

```env
# Database
DATABASE_URL="postgresql://username:password@localhost:5432/finance_dashboard"

# Authentication
JWT_SECRET="your-super-secret-jwt-key-here"
NEXTAUTH_SECRET="your-nextauth-secret-here"
NEXTAUTH_URL="http://localhost:3000"
```

### 4. Database Setup
```bash
# Generate Prisma client
npx prisma generate

# Run database migrations
npx prisma migrate dev --name init

# (Optional) Open Prisma Studio
npx prisma studio
```

### 5. Start Development Server
```bash
npm run dev
```

Visit [http://localhost:3000](http://localhost:3000) to see the application.

## 🚀 Deployment

### Deploy to Vercel

1. **Connect to Vercel**
```bash
npx vercel
```

2. **Add Database**
- Go to Vercel Dashboard → Storage
- Add Neon PostgreSQL database

3. **Configure Environment Variables**
```env
DATABASE_URL="your-production-database-url"
JWT_SECRET="your-production-jwt-secret"
NEXTAUTH_SECRET="your-production-nextauth-secret"
NEXTAUTH_URL="https://your-domain.vercel.app"
```

4. **Run Production Migrations**
```bash
npx prisma migrate deploy
```

### Alternative Deployment Options
- **Railway** - Full-stack deployment with built-in PostgreSQL
- **Netlify + Supabase** - Static hosting with managed PostgreSQL
- **Docker** - Containerized deployment

## 🧪 API Documentation

### Authentication Endpoints
- `POST /api/users` - User registration
- `POST /api/auth/login` - User login
- `GET /api/me` - Get current user (protected)

### Account Management
- `GET /api/accounts` - List user accounts (protected)
- `POST /api/accounts` - Create new account (protected)

### Transaction Management
- `GET /api/transactions` - List transactions (protected)
- `POST /api/transactions` - Create transaction (protected)

### Authentication
All protected endpoints require a valid JWT token in the Authorization header:
```
Authorization: Bearer <your-jwt-token>
```

## 🔒 Security Features

- **Password Hashing** - bcrypt with salt rounds
- **JWT Authentication** - Secure token-based sessions
- **Input Validation** - Server-side validation for all inputs
- **SQL Injection Protection** - Prisma ORM prevents SQL injection
- **CORS Configuration** - Proper cross-origin request handling
- **Environment Variables** - Sensitive data stored securely

## 🧪 Testing

### API Testing
```bash
# Test user registration
curl -X POST http://localhost:3000/api/users \
  -H "Content-Type: application/json" \
  -d '{"email":"test@example.com","password":"password123","name":"Test User"}'

# Test login
curl -X POST http://localhost:3000/api/auth/login \
  -H "Content-Type: application/json" \
  -d '{"email":"test@example.com","password":"password123"}'
```

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- **[Next.js Team](https://nextjs.org)** - For the amazing React framework
- **[Prisma Team](https://prisma.io)** - For the excellent ORM
- **[Vercel](https://vercel.com)** - For seamless deployment
- **[Neon](https://neon.tech)** - For serverless PostgreSQL

---

**Built with ❤️ using modern web technologies**

*For questions or support, please open an issue on GitHub.*
