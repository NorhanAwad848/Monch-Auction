# Monch Auction

A full-stack online auction platform with three user roles: **admin**, **seller** and **bidder**.

- **Sellers** list products for auction with images and categories.
- **Bidders** browse live auctions, place bids, and see their product history.
- **Admins** manage users (including approving pending accounts), categories, roles and auctions from a dashboard.

## Tech stack

| Part | Technologies |
|---|---|
| Frontend (`Front-End/`) | React |
| Backend (`Back-End/`) | Node.js, Express, Sequelize ORM, MySQL |
| Auth & security | JWT authentication, bcrypt password hashing, role-based access middleware |
| File uploads | Multer |

## Project structure

```
Back-End/
  config/        database connection (Sequelize)
  middlewares/   token verification, role checks, validation, uploads
  models/        User, Role, Product, Category, Auction
  routes/        REST API endpoints
  index.js       Express app entry point
Front-End/
  src/pages/     home, auctions, history, expired auctions, admin panel
  src/guards/    route guards for authenticated users
```

## API overview

| Endpoint | Purpose |
|---|---|
| `/api/Auth` | Register and log in |
| `/api/User` | Users |
| `/api/Product` | Products |
| `/api/Aucation` | Auctions and bids |
| `/api/Category` | Categories (admin only) |
| `/api/Role` | Roles (admin only) |

## Running locally

**Backend**

1. Create a MySQL database.
2. Add a `.env` file in `Back-End/`:
   ```
   DB_HOST=localhost
   DB_PORT=3306
   DB_DIALECT=mysql
   DB_USERNAME=your_user
   DB_PASSWORD=your_password
   DB_DATABASE=your_database
   ```
3. Install and start:
   ```
   cd Back-End
   npm install
   npm start
   ```
   The API runs on `http://localhost:4000`.

**Frontend**

```
cd Front-End
npm install
npm start
```

The app opens at `http://localhost:3000`.
