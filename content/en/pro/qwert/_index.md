---
title: Saramin Crawling
date: 2024-11-30
---

## https://github.com/bong-coding/server.git

### This project is a RESTful API for a job information platform developed using **Node.js** and **Express.js**, which crawls job information. It uses **MongoDB** as the database, provides authentication with **JWT**, and documents the API using **Swagger**. The project is deployed on a Jeonbuk National University cloud server.

---

## Ⅰ) Tech Stack

- **Javascript**
- **Express.js**
- **Node.js**
- **MongoDB**

---

## Ⅱ) Key Features

### REST API Development
- **Basic CRUD Features**: Provides Create, Read, Update, and Delete operations for all resources.

### User Management API (`/auth`):
1. **User Registration (POST /auth/register)**:
   - Email format validation.
   - Password encryption.
   - Duplicate user check.
   - Saves user information.
2. **Login (POST /auth/login)**:
   - User authentication.
   - Issues JWT tokens.
   - Saves login history.
   - Handles errors on login failure.
3. **Edit User Profile (PUT /auth/profile)**:
   - Applies authentication middleware.
   - Enables password change and profile updates.
4. **View User Profile (GET /auth/profile)**:
   - Provides authenticated user's profile information.
5. **Delete Account (DELETE /auth/profile)**:
   - Deletes the authenticated user's account.

---

### Job Posting API (`/jobs`):
1. **List Job Postings (GET /jobs)**:
   - Implements pagination (default page size: 20).
   - Supports search and filtering features.
2. **View Job Details (GET /jobs/:id)**:
   - Provides detailed job information.
   - Includes a feature to increase the view count.

---

### Application Management API (`/applications`):
1. **Apply for a Job (POST /applications)**:
   - Verifies authentication.
   - Checks for duplicate applications.
   - Saves application information.
2. **View Application History (GET /applications)**:
   - Displays application history for the user.
   - Supports filtering by status and sorting by date.
3. **Cancel Application (DELETE /applications/:id)**:
   - Verifies authentication.
   - Checks if cancellation is allowed.
   - Updates the application status.

---

### Bookmark API (`/bookmarks`):
1. **Add/Remove Bookmarks (POST /bookmarks)**:
   - Verifies authentication.
   - Toggles bookmark addition or removal.
2. **List Bookmarks (GET /bookmarks)**:
   - Displays the user's bookmarked job postings.
   - Includes pagination and sorting by the latest entries.

---

## Ⅲ) Authentication and Security Implementation

### JWT-Based Authentication:
- **Access Token**:
  - Issues an access token during login.
  - Validates tokens using middleware.
- **Refresh Token**:
  - Issues a refresh token during login.
  - Implements token renewal through a dedicated endpoint.

### Security Middleware:
1. **Authentication Middleware**:
   - Controls access to protected routes.
2. **Input Validation**:
   - Validates input data using `express-validator`.
3. **Rate Limiting**:
   - Limits API request rates using `express-rate-limit`.

### Additional Security Enhancements:
1. **Helmet**:
   - Configures HTTP headers for enhanced security.
2. **CORS Settings**:
   - Controls cross-origin resource sharing.

---

## Ⅳ) Key Endpoints

### a. User Management API (`/auth`)
- **User Registration (POST /auth/register)**:
  - Validates email format.
  - Encrypts passwords.
  - Checks for duplicate users.
  - Saves user information.
- **Login (POST /auth/login)**:
  - Authenticates users and issues JWT tokens.
  - Handles errors for failed login attempts.
- **Edit Profile (PUT /auth/profile)**:
  - Updates passwords and profile information after authentication.
- **View Profile (GET /auth/profile)**:
  - Retrieves authenticated user information.
- **Delete Account (DELETE /auth/profile)**:
  - Deletes the authenticated user's account.

---

### b. Job Posting API (`/jobs`)
- **List Job Postings (GET /jobs)**:
  - Implements pagination (default page size: 20).
  - Provides search and filtering functionality.
- **View Job Details (GET /jobs/:id)**:
  - Displays detailed job posting information.
  - Increments the view count.

---

### c. Application Management API (`/applications`)
- **Apply for a Job (POST /applications)**:
  - Verifies authentication and prevents duplicate applications.
  - Saves application details.
- **View Application History (GET /applications)**:
  - Displays application history for the user.
  - Includes filtering by status and sorting by date.
- **Cancel Application (DELETE /applications/:id)**:
  - Verifies authentication and checks cancellation eligibility.
  - Updates the application status.

---

### d. Bookmark API (`/bookmarks`)
- **Add/Remove Bookmarks (POST /bookmarks)**:
  - Toggles between adding or removing bookmarks.
- **List Bookmarks (GET /bookmarks)**:
  - Displays the user's bookmarks with pagination and sorting.

--- 