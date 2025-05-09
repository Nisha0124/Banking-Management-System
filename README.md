# Banking-Management-System

This Bank Management System is a GUI-based application developed using Python's tkinter module for the frontend and pymysql for database interaction. The system allows users to create accounts, log in, deposit, withdraw, and manage accounts. It interacts with a MySQL database to store user information and transaction data.


Key Features
1.Account Creation: Allows users to create new accounts by entering necessary information such as username, password, contact number, and email.
2.Login: Enables users to log into their account using a contact number and password.
3.Deposit & Withdrawal: Users can deposit money into their accounts or withdraw funds.
4.Account Deletion: Users can delete their account if desired.
5.Account Balance: Users can check their current balance.

Classes and Methods
1.Bank Class
oThe bank class defines the main structure of the application and handles the user interface and database interaction.

Constructor: __init__(self, win)
Parameters:
owin: The main window of the application.
Functionality:
oSets up the main window and the overall layout of the application.
oAdds buttons like "CREATE ACCOUNT" and "LOGIN" that allow the user to navigate between the account creation and login screens.

Account Creation
openAC(self): Displays the account creation screen.
oIncludes fields to input username, password, confirm password, contact number, and email.
oIncludes buttons to submit or close the account creation screen.
insert(self): Handles the insertion of account details into the MySQL database after validation.
oEnsures all fields are filled out and that the password matches the confirmation.
oValidates the contact number and email format using regular expressions.
clear_fields(self): Clears the input fields after account creation.

Login Process
loginAC(self): Displays the login screen with fields for contact number and password.
oIncludes buttons to log in or close the screen.
authenticate(self): Authenticates the login by checking the provided credentials against the MySQL database.
oDisplays a success or error message based on the login attempt.
clear_fieldsLogIn(self): Clears the login input fields.

Home Screen after Login
show_home_frame(self): Displays the home screen after a successful login.
oIncludes options to Deposit, Withdraw, Log out, and Delete Account.
logout(self): Destroys the home screen and allows the user to log out and return to the login screen.

Deposit & Withdraw
deposit(self): Displays the deposit screen where users can input the deposit amount.
oIncludes an "OK" button to process the deposit.
process_deposit(self): Validates the deposit amount and updates the user's balance in the database.
oThe deposit is only processed if the user is logged in.
withdraw(self): Similar to the deposit method but handles the withdrawal of funds.

Error Handling
Throughout the application, messagebox.showerror() and messagebox.showinfo() are used to display error or success messages, ensuring the user receives immediate feedback regarding their actions.

Database Interaction
The system connects to a MySQL database (bankdb) where user data (including username, password, email, and contact number) and account balance are stored. Here's a summary of the database operations:
1.Account Creation:
oInserts data into the account table.
oEnsures the user's contact information is unique.
2.Login:
oAuthenticates the user by checking if the contact number and password exist in the database.
3.Deposit and Withdrawal:
oRetrieves the user's current balance and updates it after a deposit or withdrawal.
oEnsures that the user has sufficient funds for withdrawal.


