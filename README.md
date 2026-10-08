# 🏦 OM Bank Of India - Bank Management System

A feature-rich, console-based Banking Management System implemented in **C++**. This application provides file-persisted account management, transactional logging, secure user login, colored CLI menus, and auto-generated unique account numbers.

---

## 🚀 Features

- 👤 **Account Creation**: Register new bank accounts with personal details (Name, Aadhaar, Phone, Email, Password) and an initial minimum balance of ₹500.
- 🔢 **Auto-Generated Account Numbers**: Automatically assigns structured account numbers (e.g., `OMBOI101`, `OMBOI102`) using sequence tracking in `OM-Bank-Of-India.txt`.
- 🔐 **User Authentication**: Secure login system matching account numbers with account passwords.
- 💰 **Deposit & Withdrawal**: Real-time balance management with input validation.
- 📜 **Transaction History**: Keeps a complete log of all deposits and withdrawals per user account.
- 💾 **File Persistence**: Automatically saves and loads account data and transaction histories from individual `<accountNumber>.txt` files.
- 🎨 **ANSI Terminal Colors**: Color-coded menu interface (Green for creation, Blue for login, Yellow for transactions, Magenta for account details).

---

## 📁 Project Structure

```
Banking Management System/
├── BankManagement.c++       # Primary C++ source file
├── main.cpp                 # Secondary source file entry point
├── OM-Bank-Of-India.txt     # Auto-incrementing account code sequence file
├── .gitignore               # Specifies ignored build artifacts (*.exe, *.o)
└── README.md                # Detailed project documentation
```

---

## 📐 Architecture & Class Structure

### `class bankAccount`

| Access | Member Name | Description / Details |
| :--- | :--- | :--- |
| `private` | `string bankName` | Bank prefix code (`OMBOI`) |
| `private` | `int bankCode` | Unique sequential code number |
| `private` | `string accountHolderName` | Name of the account holder |
| `private` | `string accountNumber` | Combined account identifier (`bankName + bankCode`) |
| `private` | `string accountPassword` | Account security password |
| `private` | `string addharNumber` | Government ID (Aadhaar number) |
| `private` | `string email` | Registered email address |
| `private` | `string phoneNumber` | Contact phone number |
| `private` | `double balance` | Account current balance |
| `private` | `vector<string> transactionHistory` | List of recorded transaction records |
| `public` | `void savetoFile()` | Writes account state and transaction logs to file |
| `public` | `void loadFromFile()` | Reads account details and history from file |
| `public` | `void mainMenu()` | Displays main logged-in dashboard menu |
| `public` | `void createAccount()` | Interactively collects user info and registers account |
| `public` | `void loginBankAccount()` | Authenticates user credentials |
| `public` | `void depositMoney()` | Adds funds to balance and updates history |
| `public` | `void withdrawMoney()` | Deducts funds from balance with validation |
| `public` | `void checkBalance()` | Displays current account balance |
| `public` | `void accountDetails()` | Displays complete profile information |
| `public` | `void allTransactionHistory()` | Outputs formatted transaction log |

---

## 🛠️ How to Compile & Run

### Prerequisites
- C++ Compiler (`g++`, `clang++`, or MSVC supporting C++11 or higher)

### Compilation Commands

Using `g++`:
```bash
# Compile BankManagement.c++
g++ BankManagement.c++ -o bank_system

# Run on Linux / macOS / Git Bash
./bank_system

# Run on Windows PowerShell / Command Prompt
.\bank_system.exe
```

---

## 🎮 Menu Operations

```
 Welcome to OM Bank Of India
--------------------------------------
1. Create Account
2. Login
3. Exit
```

Upon logging in, users access the interactive dashboard:
```
----------------------------------
 Enter 1 for Deposit Money 
 Enter 2 for Withdraw Money 
 Enter 3 for Check Balance 
 Enter 4 for Account Details 
 Enter 5 for All Transaction History 
 Enter 6 for Logout 
----------------------------------
```

---

## 📜 License

Distributed under the MIT License. See `LICENSE` for more information.
