<img width="831" height="468" alt="image" src="https://github.com/user-attachments/assets/82c3d3aa-5f9e-4795-90ee-1269b3163760" />
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

![3316b44b-0b7d-4910-83a5-ac2d960da240](https://github.com/user-attachments/assets/491f5c1e-b15a-4224-ab09-f901df5a21ce)

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
│── .vscode/                  # VSCode settings
│── Frontend/                 # Bootstrap UI
│── config/                   # Database and app configurations
│── controllers/              # Business logic for API endpoints
│── middleware/               # Middleware (auth, error handling)
│── models/                   # Sequelize models
│── node_modules/             # Node dependencies
│── routes/                   # API routes
│── server/                   # Server-related utilities (if needed)
│── src/                      # Optional source code folder
│── Internship_Report_final.docx
│── LICENSE
│── README.md
│── db_schema.txt
│── img-urls.txt
│── info.md
│── info.txt
│── ipo.js
│── ipoRoutes.js
│── package-lock.json
│── package.json
│── server.js

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


## 🖼️ Screenshots of some important webpages 
1. Landing Page
<img width="831" height="467" alt="image" src="https://github.com/user-attachments/assets/6d62d10a-7032-4b76-8fdf-317901f87ec1" />


2.Homepage
<img width="831" height="468" alt="image" src="https://github.com/user-attachments/assets/96a86a49-1890-4080-91a3-170d078604be" />


3. Upcoming IPO Page
<img width="831" height="468" alt="image" src="https://github.com/user-attachments/assets/ddf796ef-44c5-481b-9f10-588f9025caff" />


3. IPO Details Page
<img width="831" height="468" alt="image" src="https://github.com/user-attachments/assets/a2210eff-75e7-4936-931f-df491f249959" />


4. IPO Dashboard page 
<img width="831" height="468" alt="image" src="https://github.com/user-attachments/assets/e44fc7fa-bc61-471e-b34e-0453a82774ee" />


5. IPO Report page 
<img width="831" height="468" alt="image" src="https://github.com/user-attachments/assets/79223f18-11b9-4678-b554-f547eabff81f" />


6. Upcoming IPO Dashboard page 
<img width="831" height="468" alt="image" src="https://github.com/user-attachments/assets/59d7391a-9ad8-49fa-b402-96088f0483ed" />


7. Register IPO page 
<img width="831" height="468" alt="image" src="https://github.com/user-attachments/assets/da4d7850-5624-4c63-81aa-d4994fb69ca9" />


8. IPO Subscription Page
<img width="831" height="468" alt="image" src="https://github.com/user-attachments/assets/2e8c8609-d58b-478f-97cd-d0cff858c714" />


9. Settings Page
<img width="831" height="468" alt="image" src="https://github.com/user-attachments/assets/b63fb226-1804-44bd-a6df-f77c00e89290" />


10. Help and Support Page
<img width="831" height="468" alt="image" src="https://github.com/user-attachments/assets/1da236ee-8548-4733-ab19-315955db25f4" />


11. Bluestock Community Page
<img width="831" height="468" alt="image" src="https://github.com/user-attachments/assets/41636081-b587-40e9-9033-3e188959db2f" />


12. Bluestock Shark Investor Page
<img width="831" height="468" alt="image" src="https://github.com/user-attachments/assets/15dc1123-360b-47f6-9a77-4bd557c010ec" />


## Internship certificate
<img width="1037" height="691" alt="image" src="https://github.com/user-attachments/assets/acf1da02-5a2a-4edd-84e7-86c78734c7ec" />


## References 
	References and Appendices

(Books, Articles, Websites, and Tools Referenced)

During the development of the Bluestock Fintech IPO Information Web Application, the following resources were consulted and utilized extensively for learning, implementation, and troubleshooting:

	Official Documentation
•	Node.js Documentation
•	Express.js Documentation
•	PostgreSQL Official Docs
•	Render Deployment Guide
•	Bootstrap 5 Documentation
•	JavaScript MDN Web Docs

	📚 Online Articles and Blogs
•	“Building a RESTful API with Node.js and PostgreSQL” – DigitalOcean Community
•	“Deploying Node.js on Render” – Medium Blog by CodeSweetly
•	“Best Practices for PostgreSQL Database Schema Design” – Hackernoon
•	“Handling Date Filters in JavaScript and SQL” – Stack Overflow Threads

## Tools & Platforms Used
•	VS Code – Primary Code Editor
•	Postman – API Testing
•	Render – Cloud Deployment
•	GitHub – Version Control & Collaboration
•	pgAdmin – PostgreSQL GUI
•	Google Search – For Stack Overflow and community solutions
