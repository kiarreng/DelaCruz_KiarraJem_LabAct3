# 3ISB - Laboratory Activity 3: API Authentication using JWT

# 📌 **Overview**  
This activity will help you build a Authentication API using Express.js and MySQL. We will implement **Signup**, **Login**, **Logout** (token revocation), and a **Protected** /profile endpoint using JWT. Passwords are stored as bcrypt hashes, never in plain text.

_(Note: Make sure to download XAMPP, Visual Studio Code, and Postman as these will be needed for this project)_

# 🚀 **Run Project**  
  
# **Step 1: Create Database**  
Run Apache and MySQL at XAMPP Control Panel. Create a database in MySQL or phpMyAdmin named _lab_auth_. Then, create the table for _users_ & _revoked_tokens_:
- **users table**
  - id (int, primary key, auto-increment)
  - email (varchar, unique)
  - password_hash (varchar) 
  - full_name (varchar)
  - role (varchar, default: student)
  - created_at (timestamp)
- **revoked_tokens table**
  - id (int, primary key, auto-increment)
  - jti (varchar, unique)
  - expires_at (datetime)
  - revoked_at (timestamp)

# **Step 2: Express Project Setup**  
- Create a folder: lab-auth-api
- Open a terminal in that folder, then run:
-       npm init -y
        npm install express mysql2 dotenv cors bcryptjs jsonwebtoken uuid
        npm install -D nodemon
- Update scripts to package.json (open and edit):
-       {  
          "scripts": {
          "start": "node server.js",
          "dev": "nodemon server.js"
          }
        }
- Download all the files included in this repository.
- Check .env credentials and database name (lab_auth).
- In your terminal (project root), run:
-       npm run dev
-  If successful, the terminal should display:
-     🚀 Server running… and ✅ MySQL connected

# **Step 3: Testing Authentication API in Postman**  
Perform signup, login, protected, and logout:
- POST /api/auth/signup → Stores new user data
- POST /api/auth/login → Verify if user exists through correct email and password
- GET /api/profile → To access a token-protected file
- POST /api/auth/logout → Logging a user out

_Note: Use Postman environment with {{baseUrl}}._
