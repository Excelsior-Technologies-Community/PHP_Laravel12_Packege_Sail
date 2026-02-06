#  PHP_Laravel12_Package_Sail

<p align="center">
<a href="#"><img src="https://img.shields.io/badge/Laravel-12-red" alt="Laravel Version"></a>
<a href="#"><img src="https://img.shields.io/badge/Docker-Sail-blue" alt="Docker Sail"></a>
<a href="#"><img src="https://img.shields.io/badge/WSL-Ubuntu-green" alt="WSL Ubuntu"></a>
<a href="#"><img src="https://img.shields.io/badge/MySQL-Database-orange" alt="MySQL Database"></a>
<a href="#"><img src="https://img.shields.io/badge/Frontend-Vite-purple" alt="Vite Frontend"></a>
<a href="#"><img src="https://img.shields.io/badge/License-MIT-lightgrey" alt="License"></a>
</p>

##  Overview

**PHP_Laravel12_Packege_Sail** is a Laravel 12 development setup powered by Docker through Laravel Sail.  
It provides a clean, modern, and consistent development environment without requiring manual installation of PHP, MySQL, or a local web server like XAMPP.

The project runs entirely inside containers using WSL and Docker, making it portable, isolated, and close to a real production environment.

This setup is ideal for learning Laravel, building new applications, or developing scalable web projects with a professional workflow.

---

##  Features

-  Docker-based development environment using Laravel Sail  
-  Runs inside WSL (Linux on Windows) for better performance  
-  MySQL database container included by default  
-  Secure Laravel setup with generated application key  
-  Dependency management via Composer and NPM  
-  Modern frontend asset bundling using Vite  
-  Accessible locally at `http://localhost`  
-  Easy start/stop development environment with simple Sail commands  
-  Clean separation between system and project dependencies  
-  Production-like environment for realistic development



This project uses a modern Laravel development environment powered by Docker.

##  Tech Stack

* Docker Desktop
* Windows Subsystem for Linux (WSL)
* Laravel Sail

❌ We do NOT use XAMPP
❌ We do NOT install PHP manually

---

##  STEP 1 — Install Required Software

### 1️ Install Docker Desktop

Download and install **Docker Desktop**, then open it and keep it running.

### 2️ Install WSL (Linux inside Windows)

Open **PowerShell as Administrator** and run:

```
wsl --install
```

Restart your PC when prompted. After restart, open **Ubuntu** from the Start menu and create your Linux username and password.

---

##  STEP 2 — Where Should Laravel Be Installed?

⚠️ **Important:** Laravel + Sail projects must be installed inside Linux (WSL), **NOT** in `C:\xampp` or Desktop.

###  Correct location:

```
/home/your-username/projects
```

### Example:

```
/home/hp983/projects
```

---

##  STEP 3 — Create Laravel Project

```
cd ~
mkdir -p projects
cd projects
composer create-project laravel/laravel PHP_Laravel12_Sail
```

Wait until installation finishes.

---

##  STEP 4 — Install Sail

```
cd PHP_Laravel12_Sail
composer require laravel/sail --dev
php artisan sail:install
```

When asked which services to install, select:

```
mysql
```

Press **Enter**.

---

##  STEP 5 — Start Laravel

```
./vendor/bin/sail up -d
```

Wait 1–2 minutes the first time.

---

##  STEP 6 — Generate App Key

```
./vendor/bin/sail artisan key:generate
```

---

##  STEP 7 — Run Database Migration

```
./vendor/bin/sail artisan migrate
```

---

##  STEP 8 — Open in Browser

Open your browser and visit:

```
http://localhost
```
<img width="1403" height="689" alt="Screenshot 2026-02-04 122752" src="https://github.com/user-attachments/assets/3b44503f-c747-49a3-ba90-bf8249a194a5" />


The Laravel welcome page should appear.

---

##  FIX: Page Looks Plain (No Styling)

If Laravel loads but looks like plain text (no design), it means frontend assets are not running.

Laravel 12 uses **Vite** for CSS and JavaScript.

---

##  STEP 9 — Install Frontend Dependencies

```
./vendor/bin/sail npm install
```

---

##  STEP 10 — Start Vite Dev Server

```
./vendor/bin/sail npm run dev
```

You will see output like:

```
VITE ready in XXX ms
➜ Local: http://localhost:5173/
```

⚠️ Keep this terminal running while developing.

---

##  STEP 11 — Refresh Browser

Reload:

```
http://localhost
```

Now you will see the styled Laravel welcome page 🎉

---

##  Stopping the Project

When you finish working:

```
./vendor/bin/sail down
```

---

##  Starting Again Later

```
cd ~/projects/PHP_Laravel12_Sail
./vendor/bin/sail up -d
./vendor/bin/sail npm run dev
```

---

##  WHERE IS MY PROJECT FOLDER?

Your project lives here:

```
/home/hp983/projects/PHP_Laravel12_Sail
```

###  Open in Windows Explorer:

```
\\wsl$\Ubuntu\home\hp983\projects\PHP_Laravel12_Sail
```

###  Open in VS Code:

```
code .
```

---

### Docker Desktop Output:-

<img width="1275" height="724" alt="Screenshot 2026-02-04 135453" src="https://github.com/user-attachments/assets/66a3b9da-eb0e-43f7-b338-3e22656766b9" />

