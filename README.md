# 🌍 Travel Hub - Complete Travel Booking Portal


A full-stack travel agency website featuring package listings, secure bookings, contact forms, and AI chatbot integration.

## ✨ Key Features

### Core Functionality

✅ **6 Immersive Travel Packages**
- Beach Paradise *(Kund Malir)*
- Mountain Adventure *(Hunza Valley)*
- Desert Expedition *(Cholistan)*
- Cultural Exploration *(Lahore)*
- Safari Experience *(Lal Suhanra)*
- City Lights *(Karachi)*

✅ **Booking Management System**
- Dynamic pricing calculator  
- Date range selection  
- Guest count adjustments  
- Automatic cost computation  

✅ **Secure Communications**
- PHPMailer integration with SMTP  
- Google reCAPTCHA v3 protection  
- Form validation (client + server side)  


### User Experience

🎨 **Responsive Interface**
- Mobile-first design  
- SwiperJS carousels  
- Interactive elements  

🤖 **AI Chatbot Integration**
- Denser.ai powered assistant  
- Toggleable chat interface  
- FAQ automation  

🔍 **Smart Search**
- AJAX-powered live search  
- Cross-page results  

### 🤖 AI Chatbot Integration

- Powered by Denser.ai virtual assistant  
- Toggleable chat interface on all pages  
- Automates FAQs and user support  
- Enhances user engagement and navigation  


## 🛠 Technology Stack

### Frontend

| Technology     | Usage                  |
|----------------|------------------------|
| HTML5          | Semantic markup        |
| CSS3           | Flexbox/Grid layouts   |
| JavaScript     | DOM manipulation       |
| SwiperJS       | Image carousels        |
| FontAwesome    | Icons                  |

### Backend

| Component      | Implementation         |
|----------------|------------------------|
| Server         | PHP 7.4+               |
| Database       | MySQL(phpMyAdmin)                  |
| Email          | PHPMailer v6.6+        |
| Security       | reCAPTCHA v3           |

### DevOps

Compatible with:
- Apache/Nginx  
- cPanel/Plesk  
- Docker (PHP-FPM + MySQL)  


## 📂 Project Architecture

```bash
/travel-hub-website
├── /assets
│   ├── /images       (for all PNG/JPG files)
│   ├── /css          (for style.css)
│   └── /js           (for script.js, search.js)
├── /php              (for all PHP files)
└── index.php         (or home.php as main entry)
```



## ⚙️ Installation Guide

### Prerequisites
- PHP 7.4+ with MySQLi 
- MySQL 5.7+ (phpMyAdmin)
- SMTP credentials (for emails)  
- reCAPTCHA API keys  

### Setup Steps

#### Clone Repository
```bash
git clone https://github.com/waseem-sial/Travel-Hub-Website.git
cd travel-hub-website
```

#### Import Database Using phpMyAdmin

1. Open `http://localhost/phpmyadmin`
2. Create a database (e.g., `travel_hub`)
3. Click the **Import** tab
4. Select the file `bookings/database/schema.sql`
5. Click **Go**


#### Configuration
Create `includes/config.php`:

```php
<?php
// Database
define('DB_HOST', 'localhost');
define('DB_USER', 'travel_user');
define('DB_PASS', 'secure_password');
define('DB_NAME', 'travel_hub');

// reCAPTCHA
define('RECAPTCHA_SITE_KEY', 'your_site_key');
define('RECAPTCHA_SECRET_KEY', 'your_secret_key');

// SMTP
define('SMTP_USER', 'your@email.com');
define('SMTP_PASS', 'app_specific_password');
?>
```

#### Permissions
```bash
chmod 755 -R assets/uploads/
```


## 🔐 Security Measures

### Data Protection
- Prepared statements for all SQL queries  
- `htmlspecialchars()` for output escaping  
- Password hashing (if implementing user accounts)  

### Rate Limiting
```php
// Example in contact_send_email.php
session_start();
if (isset($_SESSION['last_submit']) && (time() - $_SESSION['last_submit'] < 60)) {
    die("Please wait 1 minute between submissions");
}
$_SESSION['last_submit'] = time();
```

### .htaccess Protections
```apache
# Prevent directory listing
Options -Indexes

# Protect config files
<FilesMatch "^(config\.php|\.env)$">
  Order allow,deny
  Deny from all
</FilesMatch>
```



## 🚀 Deployment Options

### Option 1: cPanel or Shared Hosting

- Upload all files to `public_html/` via cPanel File Manager or FTP  
- Import `schema.sql` into your server's phpMyAdmin  
- Update `includes/config.php` with production DB and SMTP credentials  

### Option 2: Localhost (XAMPP/WAMP)

- Place project in `htdocs/`  
- Access via `http://localhost/travel-hub`  
- Import DB using phpMyAdmin  



## 👥 Team

This project was developed by the **IWY Explorers** group:

- **Muhammad Waseem**  
- **Isha Shabab**  
- **Yumna Arif**  


## 📜 License

**MIT License** – See `LICENSE`


## 📞 Support

- 📧 Email: info.travelhubofficial@gmail.com  
- 📌 GitHub Issues: Report Here  


## 🎉 Pro Tips
- Use Cloudflare for DDoS protection  
- Implement cron jobs for booking reminders  
- Consider adding a payment gateway (Stripe/PayPal)  


## 💡 Suggestions

Would you like me to add:
- API documentation for potential mobile app integration?  
- Load testing results?  
- Accessibility audit report?  
- Multi-language support guide?  

## 🎥 **Video Demonstration**: [Watch on Google Drive](https://drive.google.com/drive/folders/1ix3HtqPZH9MroSCh8KqXWjkN9wWaZIYA?usp=drive_link)


_Last Updated: June 25, 2025_

![GitHub stars](https://img.shields.io/github/stars/your-username/travel-hub?style=social)  
![PHP Version](https://img.shields.io/badge/PHP-7.4%252B-777BB3?logo=php)
