Here is a **clean, professional, polished README** you can copy directly into your `README.md`:

---

````md
# Laravel JWT Authentication API

A clean and secure RESTful authentication API built with **Laravel 11** and **tymon/jwt-auth**.  
This API provides user registration, login, profile retrieval, and logout using JWT (JSON Web Tokens).

---

## 🚀 Features

- **User Registration** – Validates input and creates new users.
- **JWT Authentication** – Secure login issuing a signed access token.
- **Protected Routes** – `profile` and `logout` require a valid Bearer token.
- **Token Blacklisting** – Logout invalidates the token for security.

---

## 🛠 Tech Stack

- **PHP 8.2+**
- **Laravel 11**
- **Tymon JWT Auth**
- **SQLite / MySQL / PostgreSQL**

---

## ⚙️ Installation & Setup

Follow the steps below to run the project locally.

### **1. Clone the Repository**
```bash
git clone https://github.com/ayomijpeg/auth-api.git
cd auth-api
````

### **2. Install Dependencies**

```bash
composer install
```

### **3. Environment Setup**

Copy the example environment file and generate your app key:

```bash
cp .env.example .env
php artisan key:generate
```

### **4. Configure Database**

Open your `.env` file and update your database credentials.

For SQLite (default), create the database file:

```bash
touch database/database.sqlite
```

### **5. Generate JWT Secret**

This secret key signs all tokens.

```bash
php artisan jwt:secret
```

### **6. Run Database Migrations**

```bash
php artisan migrate
```

### **7. Start the Application**

```bash
php artisan serve
```

API will run at:

```
http://127.0.0.1:8000
```

---

## 📡 API Endpoints

> **Important:** Every request should include the header:
> `Accept: application/json`

---

### **1. Register User**

**POST** `/api/auth/register`

**Body**

```json
{
  "name": "John Doe",
  "email": "john@example.com",
  "password": "password123"
}
```

---

### **2. Login**

**POST** `/api/auth/login`

**Body**

```json
{
  "email": "john@example.com",
  "password": "password123"
}
```

**Response:** Returns a Bearer JWT token.

---

### **3. User Profile (Protected)**

**GET** `/api/user/profile`

**Headers**

```
Accept: application/json
Authorization: Bearer <your_token_here>
```

---

### **4. Logout (Protected)**

Invalidates the current JWT token.

**POST** `/api/auth/logout`

**Headers**

```
Accept: application/json
Authorization: Bearer <your_token_here>
```

---

## 🧪 Testing

Use Postman, Thunder Client, or any API testing tool.

✔ Ensure `Accept: application/json` is set
✔ Login to receive your Bearer token
✔ Use the token for all protected routes






