# Background
In today’s fast-paced world, financial management is crucial for individuals seeking to maintain control over their income and expenses. However, many current personal finance tracking tools are either too complicated, missing key functionalities, or inaccessible to users. To address this gap, we proposed developing a robust, user-friendly personal finance tracker ‘FIRE’ using Rust, tailored for users looking for a simplified yet powerful tool to handle their financial management effectively.

This project aims to deliver a versatile command-line solution designed to empower users with seamless tracking of income and expenses across customizable categories, while managing multiple account types upon users’ needs. The tool ensures accurate financial data logging and automated reconciliation, delivering a streamlined experience for users seeking clear insights into their spending, saving, and investment behavior. Featuring an intuitive, no-frills interface, this utility enables users to optimize their financial strategies and decision-making, to reach long-term financial goals and, eventually, achieve FIRE (Financial Independence, Retire Early).

# Scope Definition
This section entails the scope of our project, which includes the details for basic functionalities for our personal finance tracker tool and objectives for our tool. Please note that, because of the time constraint and limited resources, our tool would only support text user interface.

## Objectives
The goal of FIRE(personal finance tracker) is to provide users with a streamlined, command-line-based tool that empower users to take full control of their personal finances with ease and precision. Built with Rust, this tool will simplify financial management by enabling users to log transactions, set and monitor budgets, and generate insightful financial reports. Key objectives include:

### Intuitive Budgeting Tools
Users can access easy-to-use tools to set spending limits in categories like housing, utilities, and entertainment, as well as income expectations, such as salary or bonuses. By allowing budgets to be managed daily, weekly, monthly, or yearly, the tool lets users adjust tracking to fit their personal needs. With real-time updates on spending, users can continuously monitor their progress and stay aligned with their financial goals.

### Comprehensive Financial Reports
Users can access customizable reports that provide clear insights into their spending and saving habits. These reports are available in different views—such as account-based, income-focused, or expense-oriented—and can be adjusted by time frame, ranging from daily to yearly. Additionally, the tool offers budget status summaries (below target, on target, or exceeded) to show users how well they’re meeting their financial goals.

## Functions
In this section, we identify the functions for our personal finance tracker. The functionalities are categorized with detailed descriptions and sample commands. The commands are for illustration purposes and are subject to change.

### User Authentication
The tool must support user authentication for access control and account interactions. Specifically:
* When the user uses the tool for the first time, he/she would be prompted to enter a username and a password.
  * Usernames must be unique. The tool would provide error messages in case of a collision in usernames.
  * On subsequent tool usage, the tool would authenticate the user through the username and password.

### Account Management
There are two types of functionalities relevant to account management:
* The tool must support users to add, delete, and rename different accounts. 
   * The account names should be unique for the same user. The tool would provide error messages in case of a collision in names when adding or renaming accounts.
* The tool must support multiple types of accounts for each user. The types are defined in two levels:
  * On the basic level, the accounts are divided into debit and credit accounts.
  * On the finer-grind level, the user could customize the account names based on their own needs.

### Transaction Management
Before we dive into detailed functionalities, we would like to make a distinction between **internal** and **external** transactions for a user:
* An internal transaction is one that happens among multiple accounts of the same user. In this case, the user should use the “transfer” function. 
* All other transactions are considered external. In this case, the user should use the “log” function.
For each logged transaction, the tool would provide a transaction_id to the user.

In terms of functionalities, the tool must support users to log their transactions and categorize them. More specifically:
* The user should define a transaction as either income or expense.
* The user should be able to classify a transaction with one or more categories.
  * The tool provides default lists of categories for both income and expenses, listed below:
  * Income default categories: wage/bonus/interest/investment
  * Expense default categories: utility/housing/shopping/food/grocery/car
* The user should be able to add customized categories.
* Optionally, the user could specify notes with each transaction.
* The user should be able to modify a logged transaction’s amount, involved accounts, categories, and notes if applicable.

### Budget Management
The tool must support users to manage budgets. Specifically, the user should be able to:
* Set numerical limits for expense categories.
* Set numerical expectations for income categories.
* Set frequency for budgets: daily/weekly/monthly/yearly.
* Modify previously set budgets.
The specified categories and frequencies would be validated by the tool.

### Analysis and Reporting
On the basic level, the tool must offer reports on the logged transactions:
* The user could choose between two views: account centric, income centric, or expense.
* The user could adjust the time span of the reports: daily/weekly/monthly/yearly.
* The user could get budget status: below_expectation/on_target/exceeded.

