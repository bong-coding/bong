---
title: Socket-Based Locker Management System
date: 2021-12-10
---

### 🔗 https://github.com/bong-coding/socketlocker_manage.git

# Socket Locker Management Program
A client-server application using **Unix domain sockets** to manage multiple lockers.  
The client acts like a kiosk, allowing users to select menu options and send requests to the server.  
The server handles each locker’s status (password, stored item, availability) through a file-based system.

---

## 📁 File Descriptions

### `client.c`
- Connects to the server via **Unix Domain Socket (`AF_UNIX`)**
- Presents a menu (1 to 6) for actions such as:
  - **Check locker status**
  - **Register a locker**
  - **Store an item**
  - **Retrieve an item**
  - **Reset password (admin action)**
- Displays server responses in the terminal

### `server.c`
- Implements a **Unix domain socket server**
- On startup:
  - Prompts the admin for the number of lockers
  - Initializes a structure array (`loc* locker_array`) for lockers
  - Saves the state to a file (`lock_information`)
- On client connection:
  - Uses `fork()` to create a separate process per client
  - Processes requests: validate password, register lockers, store/retrieve items, admin reset
  - Updates the locker file with changes (`loc_updatefile()` or `save_all()`)

---

## 🔁 Workflow

### 1. Running the Server (`server.c`)
1. Initializes socket: `socket(AF_UNIX, SOCK_STREAM, 0)` → `bind()` → `listen()`
2. Admin is prompted to enter the **number of lockers**
3. Locker data is initialized (`reset()`) and saved to `lock_information` (`save_all()`)
4. Enters a **loop** waiting for client connections (`accept()`)
5. On client connection:
   - Creates a child process using `fork()`
   - Handles the client's request:
     - Locker registration
     - Password check
     - Store or retrieve items
     - Admin reset (password reset)
   - Updates locker file accordingly
   - Ends child process when client disconnects

### 2. Running the Client (`client.c`)
1. Connects to the server with `socket()` + `connect()`
2. Receives the **number of lockers** from the server
3. Displays a menu:
  **1.View locker status**
   **2.Register locker (choose number & set password)**
   **3.Store item (requires correct password)**
   **4.Retrieve item (correct password resets locker to "available")**
   **5.Admin call (reset password)**
   **6.Exit program**