# XKCD Comic Email Subscription 🎯

This project is a PHP-based XKCD comic email subscription system where users:
- Register their email via a verification code ✅
- Receive a **new random XKCD comic every 24 hours** via email 💌
- Can unsubscribe securely with confirmation 🔓

---
## Screenshots
<img width="1895" height="903" alt="image" src="https://github.com/user-attachments/assets/c312e4ff-771e-43b6-ad5f-591e2c738efa" />


<img width="1884" height="887" alt="image" src="https://github.com/user-attachments/assets/5c322b7f-06b2-44e5-aecb-795e5e123646" />



<img width="1897" height="894" alt="image" src="https://github.com/user-attachments/assets/3680dea9-7661-49ab-8114-4f8ee2a80036" />


## 🚀 Features Implemented

### 1️⃣ Email Verification Flow
- User enters email in a form (`index.php`)
- 6-digit code is generated and sent via email ✉️
- User enters the code to complete registration ✅
- Verified email stored in `src/registered_emails.txt`

### 2️⃣ XKCD Comic Delivery via CRON
- `cron.php` fetches a random XKCD comic from `https://xkcd.com/[comic_id]/info.0.json`
- Formats content as **HTML**
- Sends comic to all verified users every 24 hours
- Setup done using **Windows Task Scheduler**

### 3️⃣ Unsubscribe System
- Each comic email contains an **unsubscribe link**
- Clicking leads to `unsubscribe.php`
- User enters their email and receives a 6-digit code
- Code confirmation removes them from the email list

---

## 📁 Folder Structure

src/
├── index.php # Email registration & verification form
├── unsubscribe.php # Handles unsubscription flow
├── functions.php # Core logic (email, OTP, fetch comic, etc.)
├── cron.php # Fetch & send XKCD comic daily
├── setup_cron.sh # (For Linux cron setup)
├── registered_emails.txt # Stores verified user emails


---

## 💻 Technologies Used

- PHP 8.3  
- HTML/CSS  
- Gmail SMTP (via XAMPP Sendmail)  
- Git & GitHub  
- Windows Task Scheduler for CRON ⏰  

---

## 🔧 Local Setup Instructions

### 1. Clone Repo & Create Branch
```bash
git clone https://github.com/11PRIA/ComicCourier.git
cd ComicCourier
git checkout -b priyanka-submission
```
2. Set Up Email
Configure php.ini and sendmail.ini in XAMPP to use Gmail SMTP

Use an App Password for Gmail

Restart Apache in XAMPP

3. Test Locally
Open in browser:

http://localhost/xkcd-mailer/xkcd-11PRIA/src/index.php
Register, verify code, and test the flow

## 👩‍💻 Author
Priyanka Kumari

📧 Email: priyanka11062003@gmail.com

🌐 GitHub: 11PRIA

📝 Attribution
Originally inspired by rtlearn XKCD Mailer, extended and maintained by Priyanka Kumari.
