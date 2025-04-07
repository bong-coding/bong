---
title: Saramin Crawling
date: 2024-11-30
---

## 🔗 https://github.com/bong-coding/server.git

**A RESTful API job platform built with Node.js and Express.js, featuring web crawling, JWT-based authentication, MongoDB integration, and Swagger documentation.  
Deployed on Jeonbuk National University's cloud server.**

---

# 📄 Saramin API

A Node.js-based REST API server that crawls job postings from the Saramin website and provides core functionalities like authentication, job management, application tracking, and bookmark support.

> Built using Express.js, MongoDB, JWT, Swagger, and HTTPS for a secure and testable API experience.

---

## ✔️ Project Highlights

- Backend server built with **Node.js + Express.js**
- Data storage using **MongoDB Compass**
- User authentication with **JWT**
- Web crawling with **Cheerio + Axios**
- API documentation and testing via **Swagger UI**
- Secure server deployment with **HTTPS (SSL certificate)**

---

## 🚀 Core Features

### 👤 Auth API (`/auth`)
- `POST /auth/register`: Register a user (email format check, password encryption, duplicate prevention)
- `POST /auth/login`: Login and receive JWT tokens
- `GET /auth/profile`: Retrieve authenticated user info
- `PUT /auth/profile`: Update user info (including password)
- `DELETE /auth/profile`: Delete user account

---

### 📄 Job API (`/jobs`)
- `GET /jobs`: List jobs with search, filtering, and pagination
- `GET /jobs/:id`: Retrieve detailed job info and increase view count

---

### 📝 Application API (`/applications`)
- `POST /applications`: Submit a job application (with duplicate check)
- `GET /applications`: View application history (with filter/sort)
- `DELETE /applications/:id`: Cancel an application (with status validation)

---

### 🌟 Bookmark API (`/bookmarks`)
- `POST /bookmarks`: Toggle bookmark on/off for a job
- `GET /bookmarks`: Get user's bookmarked jobs (sorted and paginated)

---

## 🔐 Authentication & Security

- **JWT Auth**
  - Access & Refresh token generation
  - Route protection for authorized access
- **Security Middleware**
  - `helmet`: Sets HTTP headers for security
  - `cors`: Controls CORS policy
  - `express-validator`: Validates input data
  - `express-rate-limit`: Throttles excessive requests

---

## 🛠 Setup & Execution

### 1. Install dependencies
```bash
npm install
```
###2. Execution
- Run the crawler
```bash
npm run crawl
```
### 3. Start the HTTPS server
```bash
sudo node app.js
```
### Generate a test SSL certificate
```bash
openssl req -nodes -new -x509 -keyout server.key -out server.crt -days 365
```
Set file paths in app.js:
```javascript
const key = fs.readFileSync('/home/ubuntu/key.pem');
const cert = fs.readFileSync('/home/ubuntu/cert.pem');
```
---
## 🧾 Core Libraries

| Purpose             | Libraries                                |
|---------------------|-------------------------------------------|
| Server Framework    | `express`                                 |
| Web Crawling        | `axios`, `cheerio`                        |
| Authentication      | `jsonwebtoken`, `bcryptjs`               |
| Security            | `helmet`, `cors`, `express-rate-limit`   |
| Database            | `mongoose`                                |
| API Documentation   | `swagger-ui-express`                      |
| Env Configuration   | `dotenv`                                  |
| Logging             | `winston`                                 |


---
### Project Structure
```bash
├── app.js              # Main server entry (includes HTTPS setup)
├── routes/             # Route modules
├── controllers/        # Request handlers
├── models/             # Mongoose schemas
├── middlewares/        # Auth & security middlewares
├── utils/              # Utility functions
├── crawlers/           # Saramin crawler implementation
├── config/             # Swagger & environment config
├── .env                # Environment variable file


```