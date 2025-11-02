# 📚 MERN Bookstore App

[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
![Node](https://img.shields.io/badge/Node.js-%3E%3D14-brightgreen?logo=node.js)
[![Last Commit](https://img.shields.io/github/last-commit/Rohitlakha/mern-bookstore-app?color=blue)](https://github.com/Rohitlakha/mern-bookstore-app/commits/main)
![Repo Size](https://img.shields.io/github/repo-size/Rohitlakha/mern-bookstore-app?color=orange)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Rohit%20Lakha-blue?logo=linkedin)](https://www.linkedin.com/in/rohit-lakha)
[![GitHub](https://img.shields.io/badge/GitHub-Rohitlakha-black?logo=github)](https://github.com/Rohitlakha)

---

> **A Full-stack Bookstore Web Application built using the MERN Stack (MongoDB, Express, React, Node.js)** — featuring **JWT authentication**, **role-based access**, **categorized books (Free, Paid, Prime)**, and a **modern Tailwind CSS responsive UI**.

---

## 🧭 Table of Contents
- [📸 Demo & Screenshots](#-demo--screenshots)
- [✨ Features](#-features)
- [🧠 Tech Stack](#-tech-stack)
- [📂 Repository Structure](#-repository-structure)
- [⚙️ Requirements](#️-requirements)
- [🚀 Quick Start (A → Z)](#-quick-start-a--z)
- [🔐 Environment Variables](#-environment-variables)
- [🧩 Common Commands](#-common-commands)
- [🧪 Testing](#-testing)
- [🌍 Deployment Suggestions](#-deployment-suggestions)
- [🤝 Contributing](#-contributing)
- [📄 License](#-license)
- [📬 Contact](#-contact)

---

## 📸 Demo & Screenshots

![App Screenshot](https://github.com/Rohitlakha/mern-bookstore-app/blob/e5e4c74f18f444f073846a2c51f4e588d3f80e49/Frontend/public/Screenshot.png)

---

## ✨ Features
- 🔑 User registration & login (JWT authentication)
- 🧍 Role-based access (User / Admin)
- 📚 Book categories — Free, Paid, Prime
- 📝 Admin CRUD operations (Add / Edit / Delete books)
- 🌐 Responsive UI with **Tailwind CSS**
- 🧩 Local seeding support for development
- 🔒 Secure password hashing with **bcrypt**

---

## 🧠 Tech Stack

| Layer | Technology |
|-------|-------------|
| **Frontend** | React (Vite / CRA), React Router, Tailwind CSS |
| **Backend** | Node.js, Express.js, Mongoose |
| **Database** | MongoDB (Atlas / Local) |
| **Authentication** | JSON Web Token (JWT) |
| **Dev Tools** | Nodemon, Concurrently |

---

## 📂 Repository Structure


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

## 🚀 Run the Project (Simple Steps)

**Step 1:** Copy the GitHub repository URL  
**Step 2:** Open Command Prompt (CMD) or Terminal  
**Step 3:** Run → `git clone repo_url`  
**Step 4:** Open the project folder  
**Step 5:** Unzip `frontend` and `backend` folders (if zipped)  
**Step 6:** Go back to the main folder  
**Step 7:** Right-click → “Open in Terminal”  
**Step 8:** Run → `code .` (to open in VS Code)  
**Step 9:** Move to `frontend` →  
```bash
cd frontend
npm install
npm run dev
```
**Step 10:** Move to backend →
```cd backend
npm install
npm start
```


