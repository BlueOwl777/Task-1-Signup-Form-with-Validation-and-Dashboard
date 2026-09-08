# User Signup, Login & Role-Based Dashboard

A full-stack web app for user registration, login, and a personalized dashboard, built with PHP, MySQL, HTML, CSS, and JavaScript.

## Features Implemented

- **Signup form** with username, email, password, and role (User / Admin) selection
- **Login form** with email + password authentication
- **Password hashing** — passwords are hashed server-side with PHP's `password_hash()` (bcrypt) before being stored; the plain-text password is never saved
- **Session-based authentication** using PHP sessions
- **Role-based dashboards** — Admins are redirected to an Admin Dashboard, regular Users to a User Dashboard, based on the role chosen at signup
- **Inline validation errors** — invalid logins or duplicate-email registrations show a message on the page itself instead of a generic browser alert
- **Logout** functionality that clears the session

## Additional Features (Beyond the Base Assignment)

- A real backend with **PHP + MySQL** — a relational `users` table with a unique constraint on `email` — instead of client-side-only storage
- **Role-based access control** with separate Admin and User dashboard views
- Server-side password hashing and verification with bcrypt (`password_hash` / `password_verify`)
- <!-- Keep this line only if true: --> SQL queries protected against SQL injection using prepared statements
- <!-- Optional: --> Deployed a live public version at: `<your live demo URL, if you deployed one>`

## Concepts Learned

- PHP fundamentals: sessions, handling form submissions with `$_POST`, redirects with `header()`
- MySQL database design: primary keys, unique constraints, `ENUM` columns, and connecting PHP to MySQL with `mysqli`
- Why and how to hash passwords instead of storing them in plain text
- Debugging across the full stack — mismatched CSS class names, unclosed PHP braces, SQL syntax errors, and database credential mismatches
- SQL injection as a real risk, and how prepared statements prevent it
- Setting up and using a local dev environment (XAMPP, phpMyAdmin)
- Version control basics with Git and GitHub

## Tech Stack

- **Frontend:** HTML, CSS, JavaScript
- **Backend:** PHP
- **Database:** MySQL (managed via phpMyAdmin)
- **Local environment:** XAMPP

## Project Structure

```
├── index.php              # Login + signup page (toggles between the two forms)
├── login_register.php     # Handles form submissions for both login and registration
├── config.php             # Database connection settings
├── logout.php             # Destroys the session and logs the user out
├── admin_dashboard.php    # Dashboard shown to users with the "admin" role
├── user_dashboard.php     # Dashboard shown to users with the "user" role
├── style.css              # Styling for all pages
├── script.js              # Client-side logic (form switching)
└── <your_database>.sql    # Exported database structure — import this to set up the users table
```

## How to Run This Project Locally

### 1. Install XAMPP
Download and install XAMPP from [apachefriends.org](https://www.apachefriends.org/) if you don't already have it. It bundles Apache (the web server) and MySQL (the database) together — no separate installs needed.

### 2. Get the project onto your machine
```
git clone https://github.com/<your-username>/<your-repo-name>.git
```
Or click **Code → Download ZIP** on the GitHub repo page and extract it.

### 3. Move the Source-App file into XAMPP's htdocs folder
Once you extract the file, copy the Source-Code folder and paste it into the XAMPP's htdos folder
Copy the whole project folder into:
- Windows: `C:\xampp\htdocs\`
- Mac: `/Applications/XAMPP/xamppfiles/htdocs/`
- Linux: `/opt/lampp/htdocs/`



### 4. Start Apache and MySQL
Open the XAMPP Control Panel and click **Start** next to both **Apache** and **MySQL**. Both rows should turn green.

### 5. Create the database
1. Go to [http://localhost/phpmyadmin](http://localhost/phpmyadmin) in your browser.
2. Click **New** in the left sidebar and create a database (the name must match `$database` in `config.php`, in this case being the name "users_db").
3. Click into the new database, open the **Import** tab, choose the included `.sql` file, and click **Go**. This recreates the `users` table automatically — no need to build it by hand.

### 6. Check your database credentials
Open `config.php` and confirm these match your local setup (XAMPP's defaults usually work without changes):
```php
$host = "localhost";
$user = "root";
$password = "";
$database = "users_db";
```

### 7. Open the site
Visit the project in your browser at:
```
http://localhost/Source-app/
```

## Usage

1. Click **Sign up** to create an account with a username, email, password, and role.
2. Log in with your email and password.
3. You'll land on a dashboard matching your role, showing your account info with a **Logout** button.

## Demo Video
Check google drive folder
