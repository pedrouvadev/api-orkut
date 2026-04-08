# API Orkut

Backend application for Orkut-like social network API.

## Installation

1. Install dependencies:
```bash
npm install
```

2. Set up environment variables:
```bash
cp .env.example .env
```

Edit `.env` file with your database configuration:
- `PORT`: Server port (default: 3000)
- `DATABASE_URL`: PostgreSQL connection string
- `JWT_SECRET`: Secret key for JWT tokens

3. Start the development server:
```bash
npm run dev
```

The server will start at `http://localhost:3000`

## Dependencies

- Express.js - Web framework
- PostgreSQL - Database
- JWT - Authentication
- bcrypt - Password hashing
- joi - Input validation
- dotenv - Environment variables
- nodemon - Development auto-restart
