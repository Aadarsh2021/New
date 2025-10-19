# 🏢 Ledger Management System

A comprehensive full-stack application for managing account ledgers and property flows, built with modern web technologies.

## 📁 Project Structure

This repository contains two main projects:

- **`Account-Ledger-Software/`** - Backend API server for ledger management
- **`property-flow-design/`** - Frontend React application with modern UI

## 🚀 Quick Start

### Prerequisites

- Node.js (>=18.0.0)
- npm or yarn
- Supabase account (for database)
- Firebase account (for authentication)

### Backend Setup (Account-Ledger-Software)

```bash
cd Account-Ledger-Software
npm install
```

#### Environment Variables

Create a `.env` file in the Account-Ledger-Software directory:

```env
# Supabase Configuration
SUPABASE_URL=your_supabase_url
SUPABASE_ANON_KEY=your_supabase_anon_key
SUPABASE_SERVICE_ROLE_KEY=your_supabase_service_role_key

# JWT Configuration
JWT_SECRET=your_jwt_secret_key

# Server Configuration
PORT=5000
NODE_ENV=development

# Firebase Configuration (optional)
FIREBASE_PROJECT_ID=your_firebase_project_id
FIREBASE_PRIVATE_KEY=your_firebase_private_key
FIREBASE_CLIENT_EMAIL=your_firebase_client_email

# Redis Configuration (optional)
REDIS_URL=your_redis_url
```

#### Database Setup

1. Set up your Supabase database
2. Run the SQL schema from `supabase-schema.sql`
3. Apply database optimizations from `optimize-database.sql`

#### Start the Backend Server

```bash
# Development mode
npm run dev

# Production mode
npm start
```

The backend API will be available at `http://localhost:5000`

### Frontend Setup (property-flow-design)

```bash
cd property-flow-design
npm install
```

#### Environment Variables

Create a `.env` file in the property-flow-design directory:

```env
# API Configuration
VITE_API_URL=http://localhost:5000
VITE_API_BASE_URL=http://localhost:5000

# Supabase Configuration
VITE_SUPABASE_URL=your_supabase_url
VITE_SUPABASE_ANON_KEY=your_supabase_anon_key

# Firebase Configuration
VITE_FIREBASE_API_KEY=your_firebase_api_key
VITE_FIREBASE_AUTH_DOMAIN=your_firebase_auth_domain
VITE_FIREBASE_PROJECT_ID=your_firebase_project_id
VITE_FIREBASE_STORAGE_BUCKET=your_firebase_storage_bucket
VITE_FIREBASE_MESSAGING_SENDER_ID=your_firebase_messaging_sender_id
VITE_FIREBASE_APP_ID=your_firebase_app_id
```

#### Start the Frontend Application

```bash
# Development mode
npm run dev

# Build for production
npm run build

# Preview production build
npm run preview
```

The frontend application will be available at `http://localhost:5173`

## 🏗️ Architecture

### Backend (Account-Ledger-Software)

- **Framework**: Express.js with Node.js
- **Database**: Supabase (PostgreSQL)
- **Authentication**: JWT + Firebase Admin
- **Security**: Helmet, CORS, Rate limiting
- **Performance**: Redis caching, compression, query optimization
- **Monitoring**: Morgan logging, performance middleware

#### Key Features

- 🔐 **Authentication & Authorization**
  - JWT-based authentication
  - Firebase Admin integration
  - Role-based access control
  - Session management

- 📊 **Ledger Management**
  - Party management (customers/vendors)
  - Transaction recording
  - Trial balance generation
  - Commission tracking
  - Report generation

- 🚀 **Performance Optimizations**
  - Redis caching layer
  - Database query optimization
  - Rate limiting
  - Request compression
  - Connection pooling

- 🛡️ **Security Features**
  - Input validation
  - SQL injection prevention
  - CORS protection
  - Security headers (Helmet)

### Frontend (property-flow-design)

- **Framework**: React 18 with TypeScript
- **Build Tool**: Vite
- **UI Library**: Radix UI + Tailwind CSS
- **State Management**: Redux Toolkit
- **Data Fetching**: TanStack Query
- **Routing**: React Router v6
- **Forms**: React Hook Form + Zod validation

#### Key Features

- 🎨 **Modern UI/UX**
  - Responsive design with Tailwind CSS
  - Accessible components with Radix UI
  - Dark/light theme support
  - Smooth animations and transitions

- 📱 **User Experience**
  - Lazy loading for performance
  - Error boundaries for stability
  - Loading states and skeletons
  - Toast notifications

- 🔧 **Developer Experience**
  - TypeScript for type safety
  - ESLint for code quality
  - Hot module replacement
  - Code splitting and optimization

## 🛠️ API Endpoints

### Authentication
- `POST /api/auth/login` - User login
- `POST /api/auth/register` - User registration
- `POST /api/auth/verify` - Token verification
- `POST /api/auth/logout` - User logout

### Party Management
- `GET /api/parties` - Get all parties
- `POST /api/parties` - Create new party
- `PUT /api/parties/:id` - Update party
- `DELETE /api/parties/:id` - Delete party

### Ledger Operations
- `GET /api/ledger` - Get ledger entries
- `POST /api/ledger` - Create ledger entry
- `GET /api/trial-balance` - Generate trial balance
- `GET /api/reports/party/:id` - Party report

### Admin Operations
- `GET /api/admin/users` - Get all users
- `POST /api/admin/users/approve` - Approve user
- `GET /api/admin/dashboard` - Admin dashboard data

## 📊 Database Schema

The application uses PostgreSQL with the following main tables:

- **users** - User accounts and authentication
- **parties** - Customer/vendor information
- **transactions** - Ledger entries
- **commission_transactions** - Commission tracking
- **user_settings** - User preferences

## 🔧 Development Scripts

### Backend Scripts
```bash
npm run dev          # Start development server
npm start           # Start production server
npm run lint        # Run ESLint
npm run lint:fix    # Fix ESLint errors
npm run cleanup     # Clean console logs
npm run build:prod  # Production build
```

### Frontend Scripts
```bash
npm run dev         # Start development server
npm run build       # Build for production
npm run build:dev   # Build for development
npm run preview     # Preview production build
npm run lint        # Run ESLint
```

## 🚀 Deployment

### Backend Deployment (Vercel)

1. Install Vercel CLI: `npm i -g vercel`
2. Deploy: `vercel --prod`
3. Set environment variables in Vercel dashboard

### Frontend Deployment

1. Build the project: `npm run build`
2. Deploy the `dist` folder to your hosting service
3. Configure environment variables

## 📝 Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/amazing-feature`
3. Commit your changes: `git commit -m 'Add amazing feature'`
4. Push to the branch: `git push origin feature/amazing-feature`
5. Open a Pull Request

## 🐛 Troubleshooting

### Common Issues

1. **CORS Errors**: Check allowed origins in backend CORS configuration
2. **Database Connection**: Verify Supabase credentials and network connectivity
3. **Authentication Issues**: Check JWT secret and token expiration settings
4. **Build Failures**: Ensure all environment variables are set correctly

### Performance Issues

- Check database query performance
- Monitor Redis cache hit rates
- Verify rate limiting settings
- Review frontend bundle size

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👥 Team

- **Account Ledger Team** - Development and maintenance

## 🤝 Support

For support and questions:
- Create an issue in this repository
- Check the troubleshooting section above
- Review the API documentation

---

**Built with ❤️ using modern web technologies**
