# 📒 KhataDekho

> A lightweight **digital ledger ("khata") web app** built with **Node.js, Express and EJS** — a simple, server-rendered Khatabook-style project for recording and viewing entries.

![Node.js](https://img.shields.io/badge/Node.js-18+-339933?logo=nodedotjs&logoColor=white)
![Express](https://img.shields.io/badge/Express-4.19-000000?logo=express&logoColor=white)
![EJS](https://img.shields.io/badge/EJS-3.1-B4CA65)
![License](https://img.shields.io/badge/License-ISC-blue)

---

## 📑 Table of Contents

- [Overview](#-overview)
- [Features](#-features)
- [Tech Stack](#️-tech-stack)
- [Project Structure](#-project-structure)
- [How It Works](#-how-it-works)
- [Getting Started](#️-getting-started)
- [Scripts](#-scripts)
- [Future Improvements](#-future-improvements)
- [Author](#-author)

---

## 🎯 Overview

**KhataDekho** ("see your ledger") is a small full-stack web application that lets a user keep track of ledger entries from the browser. The server is built with **Express**, pages are rendered on the server with **EJS** templates, and entry data is stored in the project's `files/` directory.

It is a learning project focused on core backend fundamentals: routing, templating, request handling and file-based persistence.

---

## 🚀 Features

- 📝 Create ledger entries from a web form
- 📋 View saved entries in a server-rendered page
- 🖥️ Server-side rendering with reusable **EJS** views
- 💾 Simple file-based storage — no database setup required
- ⚡ Minimal dependencies (Express + EJS only)

<!-- TODO: confirm/adjust this list against app.js and the views (e.g. edit, delete, search, date-wise listing). -->

---

## 🛠️ Tech Stack

| Category | Technology |
| -------- | ---------- |
| Runtime | Node.js |
| Web Framework | Express `^4.19.2` |
| Templating | EJS `^3.1.10` |
| Storage | Local files (`files/` directory) |
| Package Manager | npm |

---

## 📁 Project Structure

```text
khatadekho/
│
├── app.js              # Express server, routes and app configuration
├── package.json        # Project metadata and dependencies
├── package-lock.json   # Locked dependency versions
├── .gitignore
│
├── views/              # EJS templates rendered by the server
├── files/              # Stored ledger data
└── node_modules/       # Installed dependencies (not committed)
```

---

## 🔄 How It Works

```text
   Browser
      │   HTTP request
      ▼
┌──────────────┐
│   Express    │  routes defined in app.js
│   (app.js)   │
└──────┬───────┘
       │
       ├──────────► reads / writes entries in  files/
       │
       ▼
┌──────────────┐
│  EJS views   │  views/*.ejs rendered with data
└──────┬───────┘
       │   HTML response
       ▼
   Browser
```

1. The browser sends a request to an Express route.
2. The route reads or writes ledger data in the `files/` directory.
3. The data is passed into an **EJS** template from `views/`.
4. The rendered HTML page is sent back to the browser.

---

## ⚙️ Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) 18 or newer
- npm (bundled with Node.js)

### 1. Clone the repository

```bash
git clone https://github.com/shubhamk23b/khatadekho.git
cd khatadekho
```

### 2. Install dependencies

```bash
npm install
```

### 3. Run the app

```bash
node app.js
```

Then open the address printed in the terminal (check the `listen` port in `app.js`), for example:

```text
http://localhost:3000
```

> 💡 For auto-restart during development, run it with [nodemon](https://www.npmjs.com/package/nodemon): `npx nodemon app.js`

---

## 📜 Scripts

`package.json` currently defines only a placeholder `test` script. Adding a `start` script is recommended:

```json
"scripts": {
  "start": "node app.js"
}
```

After that you can run the app with `npm start`.

---

## 🚀 Future Improvements

- [ ] Move storage from files to a database (SQLite / MongoDB)
- [ ] User authentication and per-user ledgers
- [ ] Edit and delete entries
- [ ] Search and filter by name or date
- [ ] Total balance summary (credit / debit)
- [ ] Input validation and error pages
- [ ] Environment-based configuration (`.env` for the port)
- [ ] Deployment (Render / Railway)

---

## 👨‍💻 Author

**Shubham Kanojiya**
AI/ML & Backend Developer

GitHub: [@shubhamk23b](https://github.com/shubhamk23b)

---

⭐ If you find this project useful, consider giving it a star on GitHub!
