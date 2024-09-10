Social Media Website
Welcome to the Social Media Website project! This repository contains the code for a social media platform featuring user profiles, messaging, and friend management. Follow the instructions below to set up your local development environment and get started.

Prerequisites
Before you begin, ensure you have the following installed on your machine:

XAMPP (includes Apache, MySQL, and PHP)
A web browser (e.g., Chrome, Firefox)

Firstly unzip the file

2. Start XAMPP
Open XAMPP Control Panel and start the following services:

Apache
MySQL
3. Set Up the Database
You need to create a MySQL database and the necessary tables for the application to function properly.

a. Access phpMyAdmin
Open your web browser and go to http://localhost/phpmyadmin.

b. Create a New Database
Click on the "Databases" tab.
Enter a name for your database, e.g., social_media_db.
Click "Create".
c. Import the Database Schema
Download the database_schema.sql file from this repository.
In phpMyAdmin, select the newly created database from the left sidebar.
Click on the "Import" tab.
Choose the database_schema.sql file and click "Go".
The database_schema.sql file should include the following tables:

users

id (INT, AUTO_INCREMENT, PRIMARY KEY)
username (VARCHAR, UNIQUE)
email (VARCHAR, UNIQUE)
password (VARCHAR)


messages

id (INT, AUTO_INCREMENT, PRIMARY KEY)
sender (VARCHAR)
recipient (VARCHAR)
message (TEXT) 
friend

username (VARCHAR)
fname (VARCHAR)
funi (VARCHAR)
fcourse (VARCHAR)


4. Configure the Application
You may need to update your configuration files to match your local environment. Look for a configuration file, typically named config.php or .env, and adjust the database connection settings as follows:
define('DB_SERVER', 'localhost');
define('DB_USERNAME', 'root'); // default XAMPP username
define('DB_PASSWORD', ''); // default XAMPP password is empty
define('DB_DATABASE', 'social_media_db');

Key Features
Messaging
Send Message: Users can send messages to each other. Messages are stored in the messages table with details such as sender, recipient, and message content.
Load Messages: Messages between users are loaded dynamically via AJAX.
Friend Management
Add Friend: Users can add friends based on university and course filters. Friend information is stored in the friend table.
Remove Friend: Users can remove friends from their list.
User Management
Change Username: Users can change their username by providing their email and password. The application updates related records in the users, friend, and messages tables.
