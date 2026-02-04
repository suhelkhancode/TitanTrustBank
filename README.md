# TitanTrust Bank Management System

TitanTrust Bank is a robust, console-based Java application designed to simulate core banking operations. It utilizes a modular architecture to manage user accounts, financial transactions, and persistent data storage through a local file-based database.

## 🏗️ Architecture & Component Breakdown

The project follows a modular design to ensure clear separation of concerns:

* **Controller & UI (`BankSystem.java`)**: Acts as the main entry point, providing a CLI for user registration, secure login, and session state management.
* **Data Model (`BankAccount.java`)**: Defines account structures including account numbers, balances, and PINs, while implementing core logic for deposits and withdrawals.
* **Data Access Layer (`FileManager.java`)**: Manages all I/O operations with the flat-file database using CSV formatting to ensure data persistence.
* **Business Logic Layer (`TransactionManager.java`)**: Contains procedural logic for complex tasks like inter-account transfers and enforces security protocols through PIN verification.

## 🚀 Key Features

| Feature | Technical Implementation |
| :--- | :--- |
| **Secure Authentication** | Validates account numbers and PINs against persistent records in `accounts.txt`. |
| **Account Creation** | Automatically generates a unique 6-character UUID for every new user. |
| **Inter-Account Transfer** | Simultaneous sender deduction and recipient addition with double-entry transaction logging. |
| **Persistent Storage** | Utilizes `BufferedWriter` and `BufferedReader` to ensure data survives application restarts. |
| **Transaction Auditing** | Appends all financial activities to a dedicated history file with timestamps and descriptions. |
| **Security Management** | Allows users to securely update credentials (PIN) or permanently close accounts. |

## 🛠️ Technical Specifications

* **Language:** Java
* **Data Format:** Plain-text CSV (Comma Separated Values)
* **Build Artifact:** `BankSystem.jar`
* **Dependencies:** Standard Java SE libraries (`java.util.*`, `java.io.*`)
* **Business Rules:** Includes a hard-coded daily withdrawal limit of 100,000.

## 📂 Project Structure
```text
titan-trust-bank/
│
├── src/
│   ├── BankSystem.java          # Main Controller & CLI
│   ├── BankAccount.java         # Data Model & Core Logic
│   ├── FileManager.java         # File I/O & Database Layer
│   └── TransactionManager.java  # Business Logic & Security
│
├── data/
│   ├── accounts.txt             # Persistent Account Database
│   └── transactions.txt         # Transaction Audit Logs
│
└── README.md
