# Bluestock IPO Setup

```bash
node -v
npm -v
psql --version
```

```bash
mkdir bluestock-ipo
cd bluestock-ipo
npm init -y
```

## Installed Required Packages

- **express**: Web framework for Node.js
- **pg**: PostgreSQL client for Node.js
- **pg-hstore**: Helps store JSON data in PostgreSQL
- **sequelize**: ORM for PostgreSQL
- **dotenv**: Loads environment variables
- **cors**: Enables cross-origin requests
- **nodemon**: Auto-restarts the server during development

```bash
mkdir config models routes controllers
touch app.js config/database.js models/index.js
```

## 1️⃣ Install PostgreSQL

Download & Install PostgreSQL from PostgreSQL Official Website. During installation:

- Enable pgAdmin (Graphical UI for PostgreSQL)
- Set a password for the default "postgres" user (Remember this)
- Install psql (CLI tool for running queries)

## 2️⃣ Install PostgreSQL Extension in VS Code

1. Open VS Code
2. Go to Extensions (Ctrl + Shift + X)
3. Search for "PostgreSQL" and install PostgreSQL extension by Microsoft
4. Click on "Add New Connection" → Enter:

```json
{
    "previewLimit": 50,
    "server": "localhost",
    "port": 5432,
    "askForPassword": true,
    "driver": "PostgreSQL",
    "database": "postgres",
    "username": "sai",
    "name": "bluestock_db"
}
```

✅ Now you are connected to PostgreSQL in VS Code.

---

# **🔹 Bluestock IPO – Optimized PostgreSQL Database Schema**

This schema efficiently manages **users, companies, IPOs, transactions, subscriptions, watchlists, and notifications**, ensuring **data integrity, performance, and seamless expansion**.

---

## **📌 Schema Overview**

| **Table Name**     | **Purpose** |
|--------------------|-------------|
| `users`            | Stores user details (admin, investor) |
| `companies`        | Stores company details |
| `ipos`             | Stores IPO-related data |
| `subscriptions`    | Tracks user IPO applications |
| `transactions`     | Logs payments for IPOs |
| `watchlists`       | Allows users to track IPOs |
| `notifications`    | Manages system/user notifications |

---

## **1️⃣ Users Table**

Stores **investor/admin** details securely.

```sql
CREATE TABLE users (
        id SERIAL PRIMARY KEY,
        full_name VARCHAR(100) NOT NULL,
        email VARCHAR(150) UNIQUE NOT NULL,
        password TEXT NOT NULL,
        phone_number VARCHAR(15) UNIQUE,
        profile_image TEXT,
        role VARCHAR(20) CHECK (role IN ('admin', 'user')) DEFAULT 'user',
        created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

### **✅ Improvements:**

- **Ensured `email` uniqueness** to prevent duplicate accounts.
- **Added `role` constraint** to limit values to 'admin' or 'user'.
- **Used `VARCHAR(15)` for `phone_number`**, as mobile numbers have a fixed format.

---

## **2️⃣ Companies Table**

Stores **company IPO details**.

```sql
CREATE TABLE companies (
        id SERIAL PRIMARY KEY,
        name VARCHAR(255) UNIQUE NOT NULL,
        logo_url TEXT,
        industry VARCHAR(100) NOT NULL,
        market_cap BIGINT CHECK (market_cap > 0),
        description TEXT,
        created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

### **✅ Improvements:**

- **Made `industry` mandatory** for classification.
- **Added `market_cap` constraint** to ensure positive values.

---

## **3️⃣ IPOs Table**

Handles **IPO pricing, status, and schedule**.

```sql
CREATE TABLE ipos (
        id SERIAL PRIMARY KEY,
        company_id INT NOT NULL,
        price_per_share DECIMAL(10,2) CHECK (price_per_share > 0) NOT NULL,
        total_shares INT CHECK (total_shares > 0) NOT NULL,
        opening_date DATE NOT NULL,
        closing_date DATE NOT NULL,
        status VARCHAR(20) CHECK (status IN ('Upcoming', 'Open', 'Closed')) NOT NULL DEFAULT 'Upcoming',
        created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
        CONSTRAINT fk_company FOREIGN KEY (company_id) REFERENCES companies(id) ON DELETE CASCADE
);
```

### **✅ Improvements:**

- **Foreign key added (`company_id`)** with `ON DELETE CASCADE` to remove IPOs when a company is deleted.
- **Added constraints for `price_per_share`, `total_shares`**, and **status values**.

---

## **4️⃣ Subscriptions Table**

Tracks **investor IPO applications**.

```sql
CREATE TABLE subscriptions (
        id SERIAL PRIMARY KEY,
        user_id INT NOT NULL,
        ipo_id INT NOT NULL,
        shares_applied INT CHECK (shares_applied > 0) NOT NULL,
        created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
        CONSTRAINT fk_user FOREIGN KEY (user_id) REFERENCES users(id) ON DELETE CASCADE,
        CONSTRAINT fk_ipo FOREIGN KEY (ipo_id) REFERENCES ipos(id) ON DELETE CASCADE
);
```

### **✅ Improvements:**

- **Enforced `user_id` and `ipo_id` foreign keys**.
- **Used `ON DELETE CASCADE`** to prevent orphan records.
- **Ensured users apply for at least `1 share`**.

---

## **5️⃣ Transactions Table**

Logs **payment details for IPOs**.

```sql
CREATE TABLE transactions (
        id SERIAL PRIMARY KEY,
        user_id INT NOT NULL,
        ipo_id INT NOT NULL,
        amount DECIMAL(15,2) CHECK (amount > 0) NOT NULL,
        payment_status VARCHAR(20) CHECK (payment_status IN ('Pending', 'Completed', 'Failed')) NOT NULL DEFAULT 'Pending',
        transaction_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
        CONSTRAINT fk_user_transaction FOREIGN KEY (user_id) REFERENCES users(id) ON DELETE CASCADE,
        CONSTRAINT fk_ipo_transaction FOREIGN KEY (ipo_id) REFERENCES ipos(id) ON DELETE CASCADE
);
```

### **✅ Improvements:**

- **Added `payment_status` constraint** to ensure only valid values.
- **Set `DEFAULT 'Pending'` for payment tracking**.

---

## **6️⃣ Watchlists Table**

Allows users to **track IPOs**.

```sql
CREATE TABLE watchlists (
        id SERIAL PRIMARY KEY,
        user_id INT NOT NULL,
        ipo_id INT NOT NULL,
        created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
        CONSTRAINT fk_user_watchlist FOREIGN KEY (user_id) REFERENCES users(id) ON DELETE CASCADE,
        CONSTRAINT fk_ipo_watchlist FOREIGN KEY (ipo_id) REFERENCES ipos(id) ON DELETE CASCADE
);
```

### **✅ Improvements:**

- **Foreign key constraints added for user-IPO relationships**.
- **Users can only track IPOs that exist**.

---

## **7️⃣ Notifications Table**

Handles **system/user notifications**.

```sql
CREATE TABLE notifications (
        id SERIAL PRIMARY KEY,
        user_id INT NOT NULL,
        message TEXT NOT NULL,
        is_read BOOLEAN DEFAULT FALSE,
        created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
        CONSTRAINT fk_user_notification FOREIGN KEY (user_id) REFERENCES users(id) ON DELETE CASCADE
);
```

### **✅ Improvements:**

- **Ensured messages cannot be `NULL`**.
- **Added `is_read BOOLEAN DEFAULT FALSE`** for tracking unread messages.

---

## **📌 Foreign Key Relationships (ERD)**

```
Users → Subscriptions → IPOs → Companies
             → Transactions
             → Watchlists
             → Notifications
```

---

## **📌 Indexing for Faster Queries**

To improve **query performance**, add indexes:

```sql
CREATE INDEX idx_users_email ON users(email);
CREATE INDEX idx_companies_name ON companies(name);
CREATE INDEX idx_ipos_company_id ON ipos(company_id);
CREATE INDEX idx_subscriptions_user_id ON subscriptions(user_id);
CREATE INDEX idx_transactions_user_id ON transactions(user_id);
```

### **✅ Benefits of Indexing:**

- **Speeds up lookups by email and company name.**
- **Optimizes JOIN operations between IPOs, subscriptions, and transactions.**

---

## **📌 Testing Database in PostgreSQL**

Test data **without backend/frontend** using queries:

```sql
-- Check registered users
SELECT * FROM users;

-- Get all IPOs that are currently Open
SELECT * FROM ipos WHERE status = 'Open';

-- List IPO applications of a specific user
SELECT * FROM subscriptions WHERE user_id = 1;

-- Check pending transactions
SELECT * FROM transactions WHERE payment_status = 'Pending';
```

---

## **🚨 Mistakes to Avoid**

- ❌ **Skipping constraints** → Leads to bad data.
- ❌ **Not using indexes** → Slows down performance.
- ❌ **Using broad text fields** → Reduces efficiency.
- ❌ **Forgetting `ON DELETE CASCADE`** → Leaves orphan records.

---

## **✅ Next Steps**

- ✅ **1. Set up PostgreSQL on VS Code**
- ✅ **2. Create & Test Database Schema**
- ⬜ **3. Connect Node.js Backend to PostgreSQL**
- ⬜ **4. Develop REST API for IPOs**

---

### **💡 Ready to Set Up PostgreSQL & Connect with Node.js? 🚀**

Would you like **step-by-step guidance** on setting up **PostgreSQL on VS Code, connecting it with Node.js, and migrating it to AWS?**