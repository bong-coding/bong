---
title: C++ Contact Book
date: 2021-12-10
---

### https://github.com/bong-coding/cpp_contact.git

# Contact Book Management Program

This is an example program for managing contact information such as **name, phone number, email, and address** using **C++ console**.  
It provides essential contact management features such as **add, search, edit, delete, and view all contacts**.

---

## Key Features

1. **Add Contact**
   - Accepts input for name, phone number, email, and address
   - Stores the information in a dynamic array (`std::vector<Contact>`)

2. **Search Contact**
   - Searches for contacts based on partial name matches
   - Displays all matching contacts if multiple matches are found

3. **Edit Contact**
   - Edits contact details (phone number, email, address) by entering the exact name
   - Allows skipping fields by pressing Enter to retain current values

4. **Delete Contact**
   - Deletes contacts by exact name match
   - Deletes all contacts with the same name if duplicates exist

5. **View All Contacts**
   - Displays all stored contacts in the address book

6. **Exit Program**
   - Selecting option 6 exits the program

---

## Compilation and Execution

**Compilation**
   ```bash
   g++ -o address_book main.cpp
