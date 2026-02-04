# TitanTrust Bank Management System

TitanTrust Bank is a robust, console-based Java application designed to simulate core banking operations. It utilizes a modular architecture to manage user accounts, financial transactions, and persistent data storage through a local file-based database.

## 🏗️ Architecture & Component Breakdown

The project follows a modular design to ensure clear separation of concerns:

* **BankSystem.java**: The main entry point and Controller. It provides the CLI for user registration, secure login, and session state management.
* **BankAccount.java**: The Data Model. Defines account structures (numbers, balances, PINs) and implements core logic for deposits and withdrawals.
* **FileManager.java**: The Data Access Layer. Manages all I/O operations with the flat-file database to ensure data persistence.
* **TransactionManager.java**: The Business Logic Layer. Handles complex tasks like inter-account transfers and enforces security via PIN verification.

## 🚀 Key Features

| Feature | Technical Implementation |
| :--- | :--- |
| **Secure Authentication** | Validates credentials against persistent records in `accounts.txt`. |
| **Account Creation** | Automatically generates a unique 6-character UUID for every new user. |
| **Inter-Account Transfer** | Simultaneous sender deduction and recipient addition with double-entry logging. |
| **Persistent Storage** | Utilizes `BufferedWriter` and `BufferedReader` to ensure data survives application restarts. |
| **Transaction Auditing** | Appends financial activities to `transactions.txt` with timestamps and descriptions. |
| **Security Management** | Allows users to securely update credentials (PIN) or permanently close accounts. |

## 📂 Project Structure
All files are located in the root directory for direct access and compilation:

```text
.
├── BankAccount.java         # Data Model & Core Logic
├── BankSystem.java          # Main Controller & CLI
├── FileManager.java         # File I/O & Database Layer
├── TransactionManager.java  # Business Logic & Security
├── BankSystem.jar           # Executable Build Artifact
├── manifest.txt             # JAR Metadata
├── accounts.txt             # Persistent Account Database
├── transactions.txt         # Transaction Audit Logs
└── README.md                # Project Documentation
