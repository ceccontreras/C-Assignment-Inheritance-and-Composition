# C++ Assignment: Inheritance and Composition in a Banking System

This repository contains a C++ console application that demonstrates object-oriented programming principles, specifically inheritance and polymorphism, through a simple banking system. The program manages a checking and a savings account, allowing a user to perform various transactions via a menu-driven interface.

## Overview

The application is built around a base `bankAccount` class with two derived classes: `checkingAccount` and `savingsAccount`. Each class has its own specific attributes and business logic. The user interacts with pre-initialized accounts, performing actions like deposits, withdrawals, and interest posting. Upon exiting, the final state of both accounts is saved to a text file.

## Features

*   **Object-Oriented Design**: Utilizes a clear inheritance structure (`bankAccount` -> `checkingAccount`, `savingsAccount`) to model different account types.
*   **Polymorphism**: Employs virtual functions (`withdraw`, `printAccountInfo`, `saveToFile`) to provide type-specific behavior for each account.
*   **Menu-Driven Interface**: A 9-option console menu provides a user-friendly way to interact with the system.
*   **Account Operations**: Supports deposits, withdrawals, and interest posting for both account types.
*   **Custom Business Logic**:
    *   The `checkingAccount` includes features like a minimum balance, service charges for falling below it, and the ability to "write a check".
    *   The `savingsAccount` enforces rules to prevent overdrafts.
*   **Input Validation**: Ensures that user input for menu choices and monetary amounts is valid, preventing crashes and incorrect data.
*   **File I/O**: Generates a formatted `AccountSummary.txt` report upon exiting the program, detailing the final status of both accounts.

## Class Structure

The program's logic is organized into three main classes:

*   **`bankAccount` (Base Class)**
    *   **Attributes**: `accountNumber`, `balance`
    *   **Methods**: `deposit()`, `getAccountNumber()`, `getBalance()`, and virtual methods for `withdraw()`, `printAccountInfo()`, and `saveToFile()`.

*   **`checkingAccount` (Derived from `bankAccount`)**
    *   **Attributes**: `interestRate`, `minimumBalance`, `serviceCharges`
    *   **Methods**: Overrides `withdraw()` to check the minimum balance and apply service charges. Overrides `printAccountInfo()` to display all checking-specific details. Includes a `writeCheck()` method.

*   **`savingsAccount` (Derived from `bankAccount`)**
    *   **Attributes**: `interestRate`
    *   **Methods**: Overrides `withdraw()` to prevent the balance from going below zero. Overrides `printAccountInfo()` for a savings-specific display format.

## How to Compile and Run

1.  **Clone the repository:**
    ```sh
    git clone https://github.com/ceccontreras/C-Assignment-Inheritance-and-Composition.git
    cd C-Assignment-Inheritance-and-Composition/UNIT11_PROGRAM_ASSIGNMENT
    ```

2.  **Compile the source code using a C++ compiler (like g++):**
    ```sh
    g++ UNIT11_PROGRAM.CPP -o BankingSystem
    ```

3.  **Run the executable:**
    ```sh
    ./BankingSystem
    ```

## Usage

Upon running the program, you will be greeted with a welcome message and the main menu.

```
============================================
          BANKING SYSTEM MAIN MENU
============================================
  1. View Checking Account Info
  2. Deposit to Checking Account
  3. Withdraw / Write Check (Checking)
  4. Post Interest (Checking)
  5. View Savings Account Info
  6. Deposit to Savings Account
  7. Withdraw from Savings Account
  8. Post Interest (Savings)
  9. Exit and Save Account Summary
============================================
```

Enter a number from 1 to 9 to perform the corresponding action. The program provides feedback for each operation. Choosing option 9 will save the account details to `AccountSummary.txt` and terminate the program.

## Output Example

When the program exits, it generates the `AccountSummary.txt` file with content similar to the following:

```
============================================
          ACCOUNT SUMMARY REPORT
============================================

--- Checking Account ---
Account Number  : 1001
Balance         : $500.00
Interest Rate   : 2.00%
Minimum Balance : $300.00
Service Charges : $25.00

--- Savings Account ---
Account Number  : 2001
Balance         : $1000.00
Interest Rate   : 3.00%

============================================
  Report generated on exit.
============================================
