
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

* **Backend:** Node.js with Express.js (RESTful APIs)  
* **Database:** PostgreSQL (pgAdmin for management)  
* **Frontend:** HTML, CSS, Bootstrap 5, JavaScript  
* **Tools:** GitHub, Postman, Notion, Google Workspace

---

## 👨‍💻 Team Members & Contributions

| **SR. No** | **Name**                                 | **Role**     | **Contributions**                                                          |
| ---------- | ---------------------------------------- | ------------ | -------------------------------------------------------------------------- |
| 1          | **Vishwajeet Shrikrishna Deshmane**      | Team Lead    | Backend, API routes/endpoints, Database, some frontend & remaining tasks   |
| 2          | Venkata Akash Kumar Yeginati             | Co-Team Lead | Contributed nothing to project                                             |
| 3          | Prerna Rahul Waghmare                    | Developer    | 4–5 pages of frontend, left project on March 22nd                          |
| 4          | Priyadarshini S                          | Developer    | Database schema & models                                                   |
| 5          | Kota Veera Venkata Satya Sai Tarun Kumar | Developer    | Contributed nothing to project                                             |
| 6          | **Aayush Barik**                         | Developer    | Managed frontend, implemented multiple pages and responsive design         |
| 7          | Dasari Vishal                            | Developer    | Contributed nothing to project                                             |
| 8          | Adarsh Rai                               | Developer    | Contributed nothing to project                                             |
| 9          | Vikas Das                                | Developer    | Contributed nothing to project                                             |
| 10         | Aryan Gotiwale                           | Developer    | Contributed nothing to project                                             |

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
````

### 3. Environment Variables (`.env`)

```init
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
│── backend/                     # Node.js Backend
│   ├── config/
│   │   └── database.js          # PostgreSQL Connection
│   ├── models/
│   │   ├── User.js
│   │   ├── Company.js
│   │   ├── IPO.js
│   │   └── Subscription.js
│   ├── routes/
│   │   ├── userRoutes.js
│   │   ├── companyRoutes.js
│   │   ├── ipoRoutes.js
│   │   └── subscriptionRoutes.js
│   ├── controllers/
│   │   ├── userController.js
│   │   ├── companyController.js
│   │   ├── ipoController.js
│   │   └── subscriptionController.js
│   └── index.js
│
│── database/
│   ├── schema.sql               # Database Schema
│
│── frontend/                    
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



