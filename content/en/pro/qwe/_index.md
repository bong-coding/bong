---
title: Bank databases
date: 2021-12-10
---

### I lost the code, so I'll replace it with a photo and text.

<!--more-->
 델파이와 sql developer를 연동시켜 실행

Running Delphi and SQL developer in conjunction with each other

Ⅰ) Technology Stack
Language used
- sqldeveloper
- Delphi

Ⅱ) Main functions
- Account opening
- Account locked after 3 password errors between customer transfers
- No fee for account transfer between the same bank
- Low interest rate per amount when creating an account type as savings

Establish a database to perform basic banking operations

- A deposit account is an object for managing a customer's bankbook.
- Deposit account transaction is an object to manage the deposit and withdrawal history for each deposit account.
- A single deposit or withdrawal history is dated and printed for each transaction.

------------------ER다이어 그램----------------------------- 
- Banks provide deposit and card services to customers
- Customers are identified by assigning them a social security number and have information such as customer name, customer address, date of birth, email, phone number, and occupation.
- Cards (business) are identified by assigning a unique card ID (number) and have information such as card application date, limit amount, payment date, card type, social security number, and account ID.

------------------테이블 구조------------------------------- 


Customer (security_number, name, address, birthday, email, phone, job) : Primary key(security_number)
Card (card_id, request_date, max_out, pay_date, card_type, security_number, account_id) : Primary key (card_id), foreign key (account_id)
Account (account_id, account_type, balance, request_card, open_date, name, phone, email, security_number) : Primary key(account_id), foreign key(security_number)
Transaction (transaction_id, account_id, transaction_date, transaction_type, information, amount, balance) : Primary key(transaction_id), foreign key(account_id)

Banking management database tables
- Customer (Social Security number, name, address, birthday, email, phone number, occupation)
- Card (card number, application date, card limit, payment date, card type, social security number, account number)
- Account (account number, account type, deposit balance, card application status, deposit opening date, depositor name, phone number, email, social security number)
- Transaction (transaction number, account number, date of deposit and withdrawal, deposit category, deposit details, transaction amount, deposit balance)


