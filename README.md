-------------------------------------- C O D E     E X P L A N A T I O N ---------------------------------------

This project is a simple web application for user signup and login, built using Flask, MySQL, and bcrypt for password hashing.

Importing Required Modules
----------------------------------------------------------------------------------------------------------------
flask - A micro web framework for Python.
mysql.connector - A MySQL driver for Python.
bcrypt - A library for hashing passwords.
----------------------------------------------------------------------------------------------------------------

-------------------------------------- F I L E S    A N D    D I R E C T O R I E S -----------------------------
/app.py - The main application file containing the Flask routes and database connection logic.
/templates/ - Directory containing HTML templates for the application.
/static/css/ - Directory containing static CSS files, including Bootstrap.
----------------------------------------------------------------------------------------------------------------

-------------------------------------- F L A S K    R O U T E S -----------------------------------------------
/ - User login page.
/signup - User signup page.
/dashboard - User dashboard displaying personal information.
/add - Add personal information.
/edit/<int:id> - Edit personal information.
/delete/<int:id> - Delete personal information.
/logout - User logout.
----------------------------------------------------------------------------------------------------------------

-------------------------------------- M Y S Q L    C O N T E N T S --------------------------------------------
CREATE DATABASE IF NOT EXISTS pims_db;
USE pims_db;

CREATE TABLE IF NOT EXISTS users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    username VARCHAR(255) NOT NULL UNIQUE,
    password VARCHAR(255) NOT NULL
);

CREATE TABLE IF NOT EXISTS personal_info (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(255) NOT NULL,
    email VARCHAR(255) NOT NULL,
    phone VARCHAR(255) NOT NULL,
    address TEXT NOT NULL,
    user_id INT NOT NULL,
    FOREIGN KEY (user_id) REFERENCES users(id)
);
----------------------------------------------------------------------------------------------------------------

-------------------------------------- H O W    T O    R U N ---------------------------------------------------
1. Install the required Python packages:
pip install flask mysql-connector-python bcrypt


2. Set up the MySQL database using the provided SQL commands.

3. Run the Flask application:
python app.py


4. Open your web browser and navigate to `http://127.0.0.1:5000/` or what you can see in the flask terminal IP of link to access the application.
----------------------------------------------------------------------------------------------------------------