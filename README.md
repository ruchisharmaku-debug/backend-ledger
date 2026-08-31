# Backend Ledger — Transaction & Account Management System

A secure, bank-style backend system built with Node.js, Express, and MongoDB that handles user authentication, account management, and atomic money transactions with idempotency protection.

## 🚀 Live Demo
[https://backend-ledger-3kks.onrender.com](https://backend-ledger-3kks.onrender.com)

## 🛠️ Tech Stack
- **Runtime:** Node.js, Express.js
- **Database:** MongoDB (Mongoose ODM)
- **Auth:** JWT-based authentication with token blacklisting on logout
- **Security:** bcrypt password hashing, role-based access control (system vs. regular users)

## ✨ Features
- User registration & login with JWT authentication
- Token blacklisting for secure logout
- Account creation and balance tracking
- Atomic fund transfers between accounts
- **Idempotency key support** — prevents duplicate transactions on retry
- System-level initial fund allocation (admin-restricted)
- Insufficient balance and invalid account validation

## 📡 API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/auth/register` | Register a new user |
| POST | `/api/auth/login` | Login and receive JWT |
| POST | `/api/accounts` | Create a new account |
| GET | `/api/accounts` | Get all accounts |
| GET | `/api/accounts/balance/:id` | Get account balance |
| POST | `/api/transactions` | Transfer funds between accounts |
| POST | `/api/transactions/system/initial-funds` | System-only fund allocation |

## ⚙️ Local Setup

\`\`\`bash
git clone https://github.com/ruchisharmaku-debug/backend-ledger.git
cd backend-ledger
npm install
# Add your .env file with MONGO_URI, JWT_SECRET, etc.
npm start
\`\`\`

## 🔒 Environment Variables
Create a `.env` file with:
\`\`\`
PORT=3000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
\`\`\`

## 📌 Learnings
Building this project involved solving real-world backend challenges: designing atomic transaction logic to prevent race conditions, implementing idempotency to handle network retries safely, and structuring auth middleware for both regular and system-level users.

## 👩‍💻 Author
**Ruchi Sharma** — [GitHub](https://github.com/ruchisharmaku-debug)
