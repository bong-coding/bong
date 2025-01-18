---
title: Movie Demo Site Development
date: 2024-09-20
---

### https://bong-coding.github.io/vue/
**"Jjapflix"** is a web application for movie information developed with **Vue.js**.  
Users can explore a variety of movies through popular movie listings, genre-based filtering, and search functionality. Additionally, they can manage personalized wishlists by signing up and logging in.

---

## Ⅰ) Tech Stack

- **Frontend Framework**: Vue.js  
- **State Management**: Vuex  
- **Routing**: Vue Router  
- **HTTP Communication**: Axios  
- **Styling**: CSS  
- **Icons**: Font Awesome  
- **API**: The Movie Database (TMDB) API  
- **Package Manager**: npm  
- **Build Tool**: Vue CLI  
- 📦 **Additional Libraries**:
  - **Vue Toastification**: Provides user notifications
  - **Vuex Persisted State**: Stores the state in local storage to persist data even after a page refresh

---

## Ⅱ) Key Features

1. **User Authentication and Login**
   - Maintains authentication state
   - Implements access control for specific routes

2. **Local Storage and State Management**
   - Integrates TMDB API for fetching movie data
   - Handles API communication and error management

3. **Movie Search and Filtering**
   - Supports filtering by genre, rating, and language
   - Provides real-time search results and updates

4. **Popular Movies**
   - Displays currently trending movies fetched via TMDB API

5. **Wishlist Feature**
   - Allows users to save and manage their favorite movies

6. **Multilingual Support**
   - Provides an interface that supports multiple languages

7. **Responsive Design**
   - Ensures seamless functionality across various devices
   - Improves user experience with intuitive navigation and design

8. **Notifications**
   - Provides user feedback through an alert system

9. **Navigation and Routing**
   - Implements Vue Router for dynamic page navigation

10. **Kakao API OAuth Integration**
    - Enables third-party authentication via Kakao API

---

## Ⅲ) Development Strategy

### Git Flow Branching Strategy

- **Branch Structure**:
  - **main**: Always maintains a deployable state
  - **develop**: Integrates ongoing development work
  - **feature**: Created for developing new features

- **Pull Requests**:
  - Ensures code quality and proper review before merging.

---

### CI/CD Pipeline and Automation

1. **Build and Test Workflow**
   - Automatically performs builds and tests when changes are merged into the `develop` branch.

2. **Deployment Workflow**
   - Automatically deploys changes to the production environment when updates are made to the `main` branch.

3. **Slack Notifications**
   - Workflow results are sent to a Slack channel, enabling team members to monitor real-time updates.

---
