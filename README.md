# Thread‑Clothing‑final  

A lightweight PHP‑based e‑commerce platform for managing and selling clothing items. The repository contains the full source code for the admin dashboard, buyer‑side utilities (including PHPMailer), and the database schema.

---

## Overview  

Thread‑Clothing‑final is a simple yet functional online clothing store built with PHP. It provides an admin interface for product, category, and order management, as well as buyer‑side features such as order notifications via email. The project is structured for easy deployment on a typical LAMP stack.

---

## Features  

- **Admin Dashboard**  
  - Secure login (`admin_login.php`)  
  - CRUD for products, categories, and users  
  - Order reporting and status updates  
  - View complaints and customer reviews  

- **Buyer Utilities**  
  - Email notifications using PHPMailer (SMTP configuration)  
  - Order placement and status tracking  

- **Database**  
  - MySQL schema (`Database/thread_db.sql`) with tables for users, products, categories, orders, reviews, and complaints  

- **Responsive UI**  
  - Custom CSS (`admin/css/style.css`) for a clean admin experience  

- **Extensible Architecture**  
  - Separate configuration file (`admin/config.php`) for database and email settings  

---

## Tech Stack  

| Layer | Technology |
|-------|------------|
| Backend | PHP 7.4+ |
| Database | MySQL / MariaDB |
| Front‑end | HTML5, CSS3 |
| Email | PHPMailer (included in `buyer/PHPMailer/`) |
| Server | Apache / Nginx (LAMP) |
| Version Control | Git |

---

## Installation  

1. **Clone the repository**  

   ```bash
   git clone https://github.com/yourusername/Thread-Clothing-final.git
   cd Thread-Clothing-final
   ```

2. **Create the database**  

   ```bash
   mysql -u root -p < Database/thread_db.sql
   ```

3. **Configure the application**  

   Edit `admin/config.php` and set your environment variables:

   ```php
   // Database
   define('DB_HOST', 'YOUR_DB_HOST');
   define('DB_NAME', 'YOUR_DB_NAME');
   define('DB_USER', 'YOUR_DB_USER');
   define('DB_PASS', 'YOUR_DB_PASSWORD');

   // PHPMailer (SMTP)
   define('SMTP_HOST', 'YOUR_SMTP_HOST');
   define('SMTP_USER', 'YOUR_SMTP_USERNAME');
   define('SMTP_PASS', 'YOUR_SMTP_PASSWORD');
   define('SMTP_PORT', 587); // or 465 for SSL
   ```

4. **Set up the web server**  

   - Point your virtual host document root to the project folder.  
   - Ensure the `admin/` directory is accessible and that `admin/config.php` is **outside** the public web root for production deployments.

5. **Install Composer dependencies (optional)**  

   PHPMailer is already bundled, but if you prefer to manage it via Composer:

   ```bash
   cd buyer/PHPMailer
   composer install
   ```

6. **Adjust file permissions**  

   ```bash
   chmod -R 755 admin/
   chmod -R 755 buyer/
   ```

7. **Launch**  

   Open `http://your-domain/admin/admin_login.php` in a browser. Use the credentials seeded in the SQL file (or create a new admin user via the dashboard).

---

## Usage  

### Admin  

| Action | File | Description |
|--------|------|-------------|
| Login | `admin/admin_login.php` |