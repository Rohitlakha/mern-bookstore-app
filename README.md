# mern-bookstore-app

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE) [![Node.js CI](https://img.shields.io/badge/node-%3E%3D14-brightgreen.svg)](https://nodejs.org/) [![Last Commit](https://img.shields.io/github/last-commit/Rohitlakha/mern-bookstore-app)](https://github.com/Rohitlakha/mern-bookstore-app/commits/main) ![Repo Size](https://img.shields.io/github/repo-size/Rohitlakha/mern-bookstore-app)


> **Full‑stack Bookstore web application built with the MERN stack** — MongoDB, Express, React (Vite or CRA), and Node.js. Features user authentication, categorized books (Free, Paid, Prime), admin book management, and a responsive UI styled with Tailwind CSS.

---

## Table of Contents
- [Demo & Screenshots](#demo--screenshots)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Repository Structure](#repository-structure)
- [Requirements](#requirements)
- [Quick Start (A → Z)](#quick-start-a--z)
  - [1. Clone repository](#1-clone-repository)
  - [2. Setup backend](#2-setup-backend)
  - [3. Setup frontend](#3-setup-frontend)
  - [4. Seed database (optional)](#4-seed-database-optional)
  - [5. Run app (development)](#5-run-app-development)
  - [6. Build & deploy (production)](#6-build--deploy-production)
- [Environment Variables](#environment-variables)
- [Common Commands](#common-commands)
- [Testing](#testing)
- [Deployment Suggestions](#deployment-suggestions)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

---

## Demo & Screenshots
> Add screenshots or a demo GIF here to make the repo stand out. Place images in `/assets/screenshots/` and reference them here.

![screenshot-1](assets/screenshots/home.png)

---

## Features
- User registration & login (JWT authentication)
- Role-based access (User / Admin)
- Book categories: Free, Paid, Prime
- Add / Edit / Delete books (Admin)
- Responsive UI built with Tailwind CSS
- Local seeding support for development
- Secure password hashing with bcrypt

---

## Tech Stack
- **Frontend:** React (+ Vite or Create React App), React Router, Tailwind CSS
- **Backend:** Node.js, Express, Mongoose
- **Database:** MongoDB (Atlas or local)
- **Auth:** JSON Web Tokens (JWT)
- **Dev tools:** nodemon, concurrently (optional)

---

## Repository Structure
```
mern-bookstore-app/
├─ backend/
│  ├─ controllers/
│  ├─ models/
│  ├─ routes/
│  ├─ data/                # seed JSON files (books.json, users.json)
│  ├─ server.js (or app.js)
│  ├─ package.json
│  └─ .env.example
├─ frontend/
│  ├─ public/
│  ├─ src/
│  │  ├─ components/
│  │  ├─ pages/
│  │  ├─ assets/
│  │  ├─ App.jsx
│  │  └─ main.jsx (or index.js)
│  ├─ package.json
│  └─ tailwind.config.js
├─ .gitignore
├─ README.md
└─ LICENSE
```

---

## Requirements
- Node.js v14+ (recommended LTS)
- npm v6+ or yarn
- MongoDB (Atlas account or local instance)

---

## Quick Start (A → Z)
Follow these steps to get the project running locally.

### 1. Clone repository
```bash
git clone https://github.com/Rohitlakha/mern-bookstore-app.git
cd mern-bookstore-app
```

### 2. Setup backend
```bash
cd backend
# install dependencies
npm install

# create .env from example
cp .env.example .env    # Linux / macOS
# or on Windows (PowerShell): Copy-Item .env.example .env

# edit .env and add your values (MONGO_URI, JWT_SECRET, PORT, etc.)
```

If you don't have nodemon globally, install as dev dependency:
```bash
npm install --save-dev nodemon
```

**Start backend** (development):
```bash
# option A: using node
node server.js

# option B: using nodemon (auto-restart on changes)
npm run dev   # ensure "dev" script in package.json calls nodemon server.js
```

### 3. Setup frontend
Open a new terminal and from project root:
```bash
cd frontend
npm install

# copy env example
cp .env.example .env
# update REACT_APP_API_URL to point to backend, e.g. http://localhost:5000/api
```

**Start frontend (development)**
If your frontend uses Vite:
```bash
npm run dev
# dev server typically runs at http://localhost:5173
```

If it uses Create React App (CRA):
```bash
npm start
# runs on http://localhost:3000 by default
```

> Tip: Use `concurrently` to run frontend + backend together from repo root. Example `package.json` script in root:
```json
"scripts": {
  "dev": "concurrently \"npm:dev --prefix backend\" \"npm:dev --prefix frontend\""
}
```

### 4. Seed database (optional)
If you added `data/users.json` and `data/books.json`, you can import them into MongoDB.

Using `mongoimport` (local MongoDB):
```bash
mongoimport --uri "mongodb://localhost:27017/bookstore" --collection users --file backend/data/users.json --jsonArray
mongoimport --uri "mongodb://localhost:27017/bookstore" --collection books --file backend/data/books.json --jsonArray
```

Or create a seed route (`/api/seed`) in backend that loads JSON and inserts it programmatically.

### 5. Run app (development)
- Start backend (`npm run dev` in `backend/`)
- Start frontend (Vite: `npm run dev` in `frontend/`)
- Open your browser at the frontend URL (e.g., `http://localhost:5173` or `http://localhost:3000`)

### 6. Build & deploy (production)
Build frontend:
```bash
cd frontend
npm run build
# copy build output to backend public folder or deploy separately (Netlify/Vercel)
```
Serve static build from Express (example):
```js
app.use(express.static(path.join(__dirname, '..', 'frontend', 'dist')));
app.get('*', (req, res) => {
  res.sendFile(path.join(__dirname, '..', 'frontend', 'dist', 'index.html'));
});
```

---

## Environment Variables
Add a `.env` file in `backend/` and `frontend/` (if needed). Example `backend/.env`:
```
PORT=5000
MONGO_URI=mongodb+srv://<user>:<pass>@cluster0.mongodb.net/bookstore?retryWrites=true&w=majority
JWT_SECRET=your_jwt_secret_here
SALT_ROUNDS=10
```

Example `frontend/.env` (Vite uses `VITE_` prefix; CRA uses `REACT_APP_`):
```
VITE_API_URL=http://localhost:5000/api
# or for CRA
REACT_APP_API_URL=http://localhost:5000/api
```

---

## Common Commands
From `backend/`:
- `npm install` — install backend deps
- `npm run dev` — start backend with nodemon
- `npm start` — start backend with node

From `frontend/`:
- `npm install` — install frontend deps
- `npm run dev` or `npm start` — start dev server
- `npm run build` — create production build

From repo root (if configured):
- `npm run dev` — run both servers concurrently

---

## Testing
- Add unit tests with Jest / Supertest for backend
- Add React Testing Library for frontend
- Example: `npm run test` (configure scripts accordingly)

---

## Deployment Suggestions
- **Frontend:** Vercel, Netlify, GitHub Pages (static)
- **Backend:** Render, Heroku (legacy), DigitalOcean App Platform, Railway
- **Database:** MongoDB Atlas (recommended for production)

If deploying both together, build frontend and serve static files from Express or use separate hosts with CORS configured.

---

## Contributing
1. Fork the repository
2. Create a feature branch: `git checkout -b feat/your-feature`
3. Commit your changes: `git commit -m "feat: add your feature"`
4. Push to branch: `git push origin feat/your-feature`
5. Open a Pull Request and describe changes

Please follow conventional commits and add tests where possible.

---

## License
This project is open-sourced under the MIT License. See the [LICENSE](LICENSE) file for details.

---

## Contact
Rohit Lakha — rohitlakha@example.com
Project Link: https://github.com/Rohitlakha/mern-bookstore-app

---

> _Made with ❤️ by Rohit — feel free to customize this README with screenshots, demo link, and additional setup notes specific to your project._

