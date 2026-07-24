# NEXPLUS - Professional Trading Terminal Platform

## Overview

NEXPLUS is a **professional-grade trading terminal platform** designed for currency traders, built with modern web technologies and cloud deployment.

### Vision
Create a trading platform that matches professional trading terminals in functionality and user experience, while remaining accessible and scalable.

---

## Architecture

```
NEXPLUS/
├── client/                 # React + Vite Frontend
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── services/
│   │   └── App.jsx
│   └── vite.config.js
│
├── server/                 # Node.js + Express Backend
│   ├── src/
│   │   ├── config/
│   │   ├── controllers/
│   │   ├── middleware/
│   │   ├── routes/
│   │   ├── services/
│   │   └── server.js
│   ├── package.json
│   └── .env.example
│
├── database/
│   └── schema.prisma
│
├── docs/
│   ├── API.md
│   ├── ARCHITECTURE.md
│   ├── SETUP.md
│   └── DEPLOYMENT.md
│
├── .github/workflows/
│   └── ci.yml
│
├── render.yaml
├── .gitignore
└── README.md
```

---

## Tech Stack

### Frontend
- **React 18** - UI library
- **Vite** - Build tool
- **Tailwind CSS** - Styling
- **React Router** - Navigation
- **Axios** - HTTP client

### Backend
- **Node.js 22 LTS** - Runtime
- **Express** - Web framework
- **Prisma ORM** - Database
- **PostgreSQL** - Database
- **JWT** - Authentication
- **bcrypt** - Password hashing
- **Helmet** - Security
- **Winston** - Logging

### Infrastructure
- **PostgreSQL** - Database
- **Render** - Cloud deployment
- **GitHub Actions** - CI/CD
- **Docker** - Containerization

---

## Phase 1 - Foundation (Current)

### Features
✅ User Authentication (Signup/Login)
✅ Secure Password Management (bcrypt)
✅ JWT-based Sessions
✅ Professional Dashboard
✅ Dark Mode UI
✅ Responsive Design
✅ API Documentation
✅ Deployment Ready (Render)

### Security
- Password hashing with bcrypt
- JWT tokens with 24h expiration
- Input validation
- XSS protection
- CORS configuration
- Rate limiting
- Helmet security headers

---

## Getting Started

### Prerequisites
- Node.js 18+ ([Download](https://nodejs.org))
- PostgreSQL 14+ ([Download](https://www.postgresql.org))
- npm 9+
- Git

### Local Development

#### 1. Clone Repository
```bash
git clone https://github.com/aron733/NEXPLUS.git
cd NEXPLUS
```

#### 2. Backend Setup
```bash
cd server
npm install
cp .env.example .env
# Edit .env with your database configuration
npm run generate
npm run migrate
npm run dev
```

#### 3. Frontend Setup (new terminal)
```bash
cd client
npm install
npm run dev
```

#### 4. Access Application
- Frontend: http://localhost:5173
- Backend: http://localhost:3000
- API Health: http://localhost:3000/api/health

---

## Environment Variables

### Backend (.env)
```
NODE_ENV=development
PORT=3000
DATABASE_URL=postgresql://user:password@localhost:5432/nexplus_db
JWT_SECRET=your-secret-key
JWT_EXPIRATION=24h
BCRYPT_ROUNDS=10
CORS_ORIGIN=http://localhost:5173
LOG_LEVEL=debug
```

### Frontend (.env)
```
VITE_API_URL=http://localhost:3000
```

---

## API Endpoints

### Authentication
- `POST /api/auth/register` - Create account
- `POST /api/auth/login` - Login
- `POST /api/auth/logout` - Logout
- `POST /api/auth/refresh` - Refresh token

### Health
- `GET /api/health` - API status

[Complete API Documentation](./docs/API.md)

---

## Deployment

### One-Click Deploy on Render

1. **Connect GitHub Repository**
   - Go to render.com
   - Connect your GitHub account
   - Select NEXPLUS repository

2. **Create PostgreSQL Database**
   - Create new database service
   - Name: nexplus-db
   - Plan: Free or Standard

3. **Deploy Backend**
   - Create Web Service
   - Build: `cd server && npm install && npm run build`
   - Start: `cd server && npm start`
   - Environment variables configured

4. **Deploy Frontend**
   - Create Static Site
   - Build: `cd client && npm install && npm run build`
   - Publish: `client/dist`

5. **Run Migrations**
   - Connect to backend
   - Run: `npm run migrate:prod`

[Full Deployment Guide](./docs/DEPLOYMENT.md)

---

## Project Structure

```
Frontend (React + Vite)
├── Components - Reusable UI components
├── Pages - Login, Register, Dashboard
├── Services - API calls
├── Hooks - Custom React hooks
└── Styles - Tailwind CSS

Backend (Node + Express)
├── Controllers - Route handlers
├── Services - Business logic
├── Middleware - Auth, errors, logging
├── Routes - API endpoints
├── Validators - Data validation
└── Config - Configuration files
```

[Architecture Guide](./docs/ARCHITECTURE.md)

---

## Phase 2 - Terminal Features (Coming Soon)

- 📊 TradingView Charts Integration
- 📈 Watchlist Management
- 📰 Economic News Feed
- 📅 Economic Calendar
- 💰 Risk Calculator
- 📒 Trading Journal
- 🔔 Market Alerts

---

## Phase 3 - AI Engine (Coming Q4 2026)

- 🤖 Multi-timeframe Analysis
- 📈 Trend Detection
- 💡 Smart Entry/Exit Signals
- 📊 Pattern Recognition
- 💬 Telegram Bot Integration

---

## Phase 4 - Premium (Coming Q1 2027)

- 👥 User Management
- 💳 Payment Integration
- 📅 Subscription System
- 🎛️ Admin Dashboard
- 🔌 Public API

---

## Development

### Code Quality
- ESLint for code linting
- Prettier for code formatting
- GitHub Actions for CI/CD
- Automated testing

### Running Tests
```bash
# Backend tests
cd server
npm test

# Frontend tests
cd client
npm test
```

### Code Formatting
```bash
# Backend
cd server
npm run format

# Frontend
cd client
npm run format
```

---

## Documentation

- [API Reference](./docs/API.md) - Complete API documentation
- [Architecture Guide](./docs/ARCHITECTURE.md) - System design and patterns
- [Setup Instructions](./docs/SETUP.md) - Detailed setup guide
- [Deployment Guide](./docs/DEPLOYMENT.md) - Render deployment steps

---

## Security

### Implemented
✅ HTTPS/SSL encryption
✅ Password hashing (bcrypt)
✅ JWT authentication
✅ Input validation & sanitization
✅ CORS protection
✅ Rate limiting
✅ Helmet security headers
✅ SQL injection prevention
✅ XSS protection
✅ Environment variable management

### Compliance
✅ OWASP Top 10 compliance
✅ Data encryption
✅ Regular security audits
✅ Privacy-first approach

---

## Performance Targets

- Page Load: < 2 seconds
- API Response: < 200ms
- Uptime: 99.9%
- Mobile: Fully responsive

---

## Support & Contributing

### Issues & Bugs
Report issues on GitHub: [Create Issue](https://github.com/aron733/NEXPLUS/issues)

### Documentation
- Read [SETUP.md](./docs/SETUP.md) for installation help
- Check [API.md](./docs/API.md) for API questions
- Review [ARCHITECTURE.md](./docs/ARCHITECTURE.md) for system design

### Contributing
We follow a structured development process:
1. Sprint planning
2. Feature development
3. Testing
4. Code review
5. Automated deployment

---

## Roadmap

### Q3 2026 ✅
- Phase 1 Launch
- Authentication + Dashboard
- API Foundation

### Q4 2026 🚀
- Phase 2 Terminal Features
- TradingView Integration
- Market Data

### Q1 2027 🤖
- Phase 3 AI Engine
- Analysis & Signals
- Telegram Bot

### Q2 2027 💰
- Phase 4 Premium
- Payments & Subscriptions
- Admin Dashboard

---

## License

MIT License - See LICENSE file for details

---

## Status

🚀 **Phase 1 Foundation** - Active Development

**Last Updated**: July 24, 2026

Built with ❤️ for traders worldwide
