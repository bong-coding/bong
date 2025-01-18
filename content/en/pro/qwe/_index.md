---
title: Locker Management Using Sockets
date: 2021-12-10
---

### https://github.com/bong-coding/socketlocker_manage.git

# Locker Management Socket Program
This is an example of a **server/client architecture** for managing multiple lockers using **socket communication**.  
The client operates like a kiosk interface, selecting menu options to send requests to the server. The server uses files (lock files) to store, update, and retrieve locker statuses (passwords, items, etc.).

---

## File Structure

### `client.c`
- Connects to the server using a Unix domain socket (`AF_UNIX`).
- Provides menu options (1–6) to request **locker status**, **registration**, **item storage**, **item retrieval**, and **password reset (admin call)**.
- Receives and displays the server's responses.

### `server.c`
- Implements the **Unix domain socket server**.
- On execution, it prompts the user for the number of lockers, initializes a structure array (`loc* locker_array`), and saves the data to a file.
- When a client connects, the server forks a new process to handle requests.
- Reads and writes locker data (number/password/status/items) to the `lock_information` file.

---

## Operational Flow

### 1. Server Execution (`server.c`)
1. The server enters a listening state via `socket(AF_UNIX, SOCK_STREAM, 0)` → `bind()` → `listen()`.
2. Prompts the user to input the **number of lockers**, initializes the `locker_array` via `reset()`, and saves everything to the `lock_information` file using `save_all()`.
3. Enters an **infinite loop** and waits for client connections using `accept()`.
4. On connection, forks a child process to communicate with the client:
   - Handles tasks such as password verification, locker registration, item storage/retrieval, and admin calls (password reset).
   - Updates the locker information in the file (`loc_updatefile()` or `save_all()`).
   - Terminates the child process when the client disconnects.

### 2. Client Execution (`client.c`)
1. Creates a Unix domain socket with `socket(AF_UNIX, SOCK_STREAM, 0)` and connects to the server using `connect()`.
2. Receives the **number of lockers** (`count`) from the server and stores it.
3. Displays the following menu:  
   **1.** View locker usage status (`show()`)  
   **2.** Register a locker (locker number and password setup)  
   **3.** Store an item (possible if the locker is registered and the password matches)  
   **4.** Retrieve an item (retrievable if the password matches; sets the locker to “available” again)  
   **5.** Admin call (e.g., password reset)  
   **6.** Exit the program  
4. Sends the selected menu option to the server and inputs any additional required data (locker number, password, item name, etc.).
5. Receives and displays the server's processing results (success/failure, usage status, etc.).

---