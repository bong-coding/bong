---
title: Movie Demo Website
date: 2024-09-20
---

### 🔗 https://bong-coding.github.io/vue/

**A responsive Vue.js-based SPA where users can browse popular movies, search by genre, and manage their personalized wishlist after signing up or logging in.**

---

# 🎬 Jjapflix – Vue Movie Info SPA

> A Single Page Application (SPA) built with Vue.js, powered by The Movie Database (TMDb) API and Kakao Developers API.  
> Features include dynamic movie search, personalized wishlist, social login, and multi-language support.

---

## ✔️ Project Overview

| Category       | Details                                      |
|----------------|----------------------------------------------|
| Framework      | Vue.js (SPA)                                 |
| State Management | Vuex + vuex-persistedstate                  |
| Routing        | Vue Router                                   |
| API Integration| TMDB API, Kakao API                          |
| Deployment     | GitHub Pages, GitHub Actions                 |
| Authentication | Email/Password, Kakao OAuth                  |
| Storage        | localStorage / sessionStorage                |
| Responsive     | Supports desktop, tablet, and mobile devices |
| UI Effects     | CSS transitions and animations               |
| AI Tools       | ChatGPT used for prompting and code refinement |

---

## 🚀 Key Features Summary

### 🔐 User Authentication
- Email/password registration & login
- Kakao social login integration
- “Remember Me” toggle with session/local storage
- Auto redirect to `/` after login
- UI conditional rendering based on login state
- Auth guard for protected routes

---

### 🎁 Wishlist Management
- Add/remove movie recommendations
- Persisted in Vuex + localStorage
- Wishlisted movies visually marked with 👍

---

### 🔍 Movie Search & Filtering
- Combined filters: genre, rating, language, sort
- Real-time filtering and reset option
- Search results shown in card layout

---

### 🔥 Popular Content
- `/popular` route
- Choose between Table View and Infinite Scroll
- Includes pagination and scroll-to-top button

---

### 🎬 Homepage
- Displays movie info from multiple TMDB endpoints
- Movie details: title, overview, genres, rating
- Hover effects and "recommend" button on posters

---

### 💬 Notification System
- Toast messages using Vue Toastification
- Context-aware feedback for login/signup/errors

---

### 🌐 Multilingual Support
- Language selection: Korean, English
- Language stored in localStorage
- API responses adapted to selected language

---

### 🔌 API Handling
- Axios interceptor for token/lang injection
- Centralized API error handling
- Optimized request flow and response caching
- Visual loading indicators via spinner or loader

---

### 📱 Responsive UI & UX
- Fully responsive across all devices
- Media queries and flexible layout handling
- Animated transitions for cards, menus, and modals

---

## ⚙️ GitHub Actions – CI/CD Pipeline

This project uses **GitHub Actions** for automated builds, tests, and deployment.

### ✔️ Workflow

| Branch      | Action                         |
|-------------|--------------------------------|
| `develop`   | Auto build and test on push/PR |
| `main`      | Deploy to GitHub Pages         |
| All Branches| CI checks triggered on PRs     |

### 🔔 Slack Integration
- Workflow results delivered to Slack in real-time

### 🔐 Security & Optimization
- `.env-dev` and `.env-prod` for environment separation
- API keys stored securely via GitHub Secrets
- Branch protection: no direct push to `main`, PR approval required

---

## ✨ Feature Details

### 🔐 Authentication
- Email/Password registration with validation
- Session vs. persistent login modes
- Secure logout and route protection

---

### 🧠 State Management & Persistence
- Vuex for centralized store
- vuex-persistedstate to survive refresh
- Language/theme/user preferences stored locally

---

### 🔌 API Integration & Error Handling
- TMDB via Axios with automatic key/lang injection
- Graceful handling of 404/500 and network errors
- User-friendly feedback with toasts
- Cached or optimized repeated calls

---

### 📈 Popular Movies View
- TMDB-based trending movies
- Selectable layout:
  - **Table View** with pagination
  - **Infinite Scroll** with auto-load
- Scroll-to-top button included

---

### ❤️ Wishlist
- Toggle wishlist items easily
- Dedicated wishlist page
- Persistent and reactive UI updates

---

### 🌐 Language Support
- Multi-language: Korean / English 
- Language stored in localStorage
- Applied to API responses dynamically

---

### 📱 Responsive Design
- Mobile-first layout with media queries
- Smooth CSS transitions:
  - Card hover zoom
  - Page transitions
  - Button/menu animations

---

### 💬 User Notification
- Vue Toastification for real-time feedback
- Unified styling for success, error, warning messages

---

### 🧭 Navigation & Routing
- SPA with Vue Router
- Guard protected pages (redirect to login if unauthorized)
- 404 fallback routes
- Route-level transition effects

---

## 🌿 Git Strategy

This project adopts the **Git Flow strategy** for clean version control and collaborative development.

### ✔️ Branching Structure

| Branch       | Purpose                        |
|--------------|--------------------------------|
| `main`       | Production / release branch    |
| `develop`    | Active development branch      |
| `feature/*`  | Feature-specific implementation|

---

## 🧪 Dev & Deployment Environment

### ⛅ Environment Separation
- `.env-dev`, `.env-prod` for different stages
- Handled via `dotenv`
- Separate NPM scripts:

```bash
npm run serve:dev     # Development mode
npm run serve:prod    # Production mode
```