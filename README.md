# 📈 Bluestock IPO Information Web Application

A **full-stack web application & REST API** developed during my internship at **Bluestock Fintech**.
The application provides **real-time IPO (Initial Public Offering) information** with secure backend APIs and a responsive frontend.

---

## 🚀 Project Overview

* **Company:** Bluestock Fintech
* **Website:** [Bluestock Website](http://www.bluestock.in/)
* **Project Type:** Web Application & REST API
* **Tech Stack:** Node.js (Express.js), PostgreSQL, Bootstrap 5, JavaScript

📅 **Start Date:** 02/02/2025
📅 **Deadline:** Flexible (as per team lead)

---

## 📢 Objective

Develop a scalable application to share IPO-related data with the public, including:

* ✅ Company Name & Logo
* ✅ IPO Price, Listing Date, Market Price
* ✅ Issue Size, Type, Status
* ✅ Downloadable RHP & DRHP PDFs

---

## 🛠️ Tech Stack

**Backend:** Node.js with Express.js (RESTful APIs)
**Database:** PostgreSQL (pgAdmin for management)
**Frontend:** HTML, CSS, Bootstrap 5, JavaScript
**Tools:** GitHub, Postman, Notion, Google Workspace

---

## 👨‍💻 Team Members

| **SR. No** | **Name**                                 | **Role**     | **Assigned Task**                                                                  |
| ---------- | ---------------------------------------- | ------------ | ---------------------------------------------------------------------------------- |
| 1          | Vishwajeet Shrikrishna Deshmane          | Team Lead    | GitHub setup, JWT Authentication, PostgreSQL schema design, CRUD APIs, Integration |
| 2          | Venkata Akash Kumar Yeginati             | Co-Team Lead | Backend logic, Core API routes, Node.js + PostgreSQL integration, Authentication   |
| 3          | Prerna Rahul Waghmare                    | Developer    | Frontend UI (Bootstrap 5), IPO listings, Company fetch & integration               |
| 4          | Priyadarshini S                          | Developer    | Database models, CRUD operations, PostgreSQL testing                               |
| 5          | Kota Veera Venkata Satya Sai Tarun Kumar | Developer    | To be assigned                                                                     |
| 6          | Aayush Barik                             | Developer    | Frontend components, Responsive design, API integration                            |
| 7          | Dasari Vishal                            | Developer    | Backend logic, API integration with frontend                                       |
| 8          | Adarsh Rai                               | Developer    | REST APIs, Validation, Error handling, Postman testing                             |
| 9          | Vikas Das                                | Developer    | Backend API integration, Data handling between frontend & backend                  |
| 10         | Aryan Gotiwale                           | Developer    | Frontend responsiveness & UI consistency                                           |

---

## 📌 Project Setup

### 1. Prerequisites

* Node.js (LTS recommended) → [Download](https://nodejs.org/)
* PostgreSQL → [Download](https://www.postgresql.org/download/)
* npm or yarn

### 2. Initialize Project

```bash
mkdir bluestock-ipo
cd bluestock-ipo
npm init -y
npm install express sequelize pg pg-hstore dotenv nodemon
```

### 3. Environment Variables (`.env`)

```ini
DB_NAME=bluestock_ipo
DB_USER=your_username
DB_PASSWORD=your_password
DB_HOST=localhost
DB_PORT=5432
JWT_SECRET=your_secret_key
```

Add `.env` to `.gitignore`:

```gitignore
node_modules/
.env
```

### 4. Project Structure

```
bluestock-ipo/
│── backend/
│   ├── config/            # Database config
│   ├── models/            # Sequelize models
│   ├── routes/            # API routes
│   ├── controllers/       # Business logic
│   ├── index.js
│
│── database/
│   ├── schema.sql
│   ├── seed.sql
│
│── frontend/              # Bootstrap UI
│── README.md
```

---

## 🌐 REST API Endpoints

* `GET /api/ipos` → Fetch all IPOs
* `GET /api/ipos/:id` → Fetch IPO by ID
* `POST /api/ipos` → Add new IPO
* `PUT /api/ipos/:id` → Update IPO
* `DELETE /api/ipos/:id` → Delete IPO

---

## 🎨 Frontend

* Responsive IPO listings (Bootstrap 5 grid)
* IPO details page with company info & PDFs
* Fetch API for backend integration

---

## 🔗 Resources

* [Bluestock Website](http://www.bluestock.in/)
* [Express.js Docs](https://expressjs.com/)
* [Sequelize Docs](https://sequelize.org/)
* [PostgreSQL Docs](https://www.postgresql.org/docs/)
* [Figma UI/UX Design](https://www.figma.com/design/IyF5MKCS7GP2ChFBOiWXAK/bluestock-fintech-ui-ux-team?node-id=0-1)
* [System Design Board](https://www.figma.com/board/g9bjreevYNJkfMuwRacyaP/System-Design?t=rhom7O3DRl5pdHkG-1)

---

## 📌 Work Guidelines

* ✅ Use Notion & Google Workspace for task tracking
* ✅ Push code daily to GitHub (tested & clean)
* ✅ Join daily team meet at **6:00 PM** → [Google Meet Link](https://meet.google.com/zih-fsxx-spc)
* ✅ Communicate blockers early

---

## ✅ Daily Standup Format

* What was completed yesterday?
* What will be worked on today?
* Any blockers/issues faced?
* Estimated completion time?

---

## 📖 Final Notes

This is a **production-level project**. Maintain clean code, test thoroughly, respect deadlines, and collaborate effectively.

🚀 Let’s build something impactful together!
