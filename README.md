# Sushi Restaurant Advanced Database Systems

This repository contains a web application for managing a sushi restaurant, developed as part of an Advanced Database Systems project. The app includes features for authentication, branch and company statistics, menu management, reservations, and more.

## Project Structure

- `app.js` - Express application setup with session and passport.
- `index.js` - Entry point that starts the server.
- `database_script/` - Contains SQL scripts for database initialization, stored procedures, and triggers.
- `src/` - Source code folder with configuration, controllers, routes, services, middlewares, utilities, and views.

## Features

- User authentication with Passport.js (local strategy).
- Session management stored in a SQLite/Postgres (via Knex) backed table.
- CRUD operations for branches, menus, and reservations.
- Statistics dashboards for branches and company-wide metrics.
- EJS-based templating for views.

## Technologies

- Node.js & Express
- Passport.js for authentication
- Knex.js for database queries
- EJS for server-rendered views
- Tailwind CSS for styling
- SQLite / PostgreSQL (configurable via `src/config/db.js`)

## Setup Instructions

1. Clone the repository:
   ```bash
   git clone <repo-url>
   cd Advanced-Database-Systems_Sushi-Restaurant
   ```
2. Install dependencies:
   ```bash
   npm install
   ```
3. Copy `.env.example` to `.env` and configure environment variables (e.g. `PORT`, `DATABASE_URL`, `SESSION_SECRET`).
4. Set up the database using the SQL scripts in `database_script/`.
   - Run `index.sql` to create tables.
   - Use `stored_procedure.sql` and `trigger.sql` as needed.
5. Start the development server:
   ```bash
   npm run dev
   ```

## Environment Variables

| Variable         | Description                          |
|------------------|--------------------------------------|
| `PORT`           | Server port (default: 3002)          |
| `DATABASE_URL`   | Connection string for the database   |
| `SESSION_SECRET` | Secret key for express-session       |

## Middleware

- `auth-middleware.js` - Protects routes and attaches profile information to requests.
- `connect-flash` for flash messages.

## Views

EJS templates are organized under `src/views/`. Layouts and partials are used to maintain consistency across pages, including error pages and statistic dashboards.

## Notes

- Ensure that you run database migrations or use the provided `index.sql` script before starting the server.
- For production use, set `secure: true` for cookies and configure a proper session store.

## Contribution

Feel free to fork the repository and submit pull requests for new features or bug fixes.

