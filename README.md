# Zabbix Monitoring Project
![zabbix](https://i.ibb.co/zW20mNcb/Screenshot-2025-04-15-191835.png)
![agent](https://i.ibb.co/sdJ58TGp/Screenshot-2025-04-15-192056.png)
![hostdone](https://i.ibb.co/B57k9kqT/Screenshot-2025-04-15-191741.png)
This project documents the complete process of installing and configuring **Zabbix 7.0** on **Ubuntu Server 22.04.5** using **MySQL** as the backend. It includes installation commands, configuration files, trigger templates, and alerting via **Gmail SMTP**.

---

## 📌 Project Overview

- **Objective:** Deploy Zabbix to monitor systems and network devices.
- **OS:** Ubuntu Server 22.04.5 (minimal install)
- **Monitoring Tool:** Zabbix 7.0
- **Database:** MySQL
- **Web Server:** Apache2 + PHP
- **Alerts:** Configured with Gmail SMTP

---

## 🛠️ Features

- Real-time host monitoring via Zabbix Agent
- Email alert notifications for triggers (e.g., high CPU, downtime)
- Custom dashboards and graphs
- Installation done entirely via terminal

---

## 📦 Folder Structure

zabbix-monitoring-project/ ├── setup/ # Shell scripts and firewall rules ├── alerting/ # Email and trigger configuration ├── screenshots/ # UI and alert examples ├── zabbix_server.conf # Main Zabbix server config ├── zabbix_agentd.conf # Sample agent config └── README.md


---

## 🚀 Setup Summary

### Step 1: Install Zabbix and MySQL
```bash
sudo apt update && sudo apt install mysql-server apache2 php php-mysql
sudo wget https://repo.zabbix.com/zabbix/7.0/ubuntu/...
sudo apt install zabbix-server-mysql zabbix-frontend-php ...

### Step 2: Create Zabbix Database
CREATE DATABASE zabbix CHARACTER SET utf8mb4 COLLATE utf8mb4_bin;
CREATE USER 'zabbix'@'localhost' IDENTIFIED BY 'yourpassword';
GRANT ALL PRIVILEGES ON zabbix.* TO 'zabbix'@'localhost';

### Step 3: Import Schema
zcat /usr/share/zabbix-sql-scripts/mysql/server.sql.gz | mysql -u zabbix -p zabbix

### Step 4: Configure Server
Edit /etc/zabbix/zabbix_server.conf with your DB credentials.

### 📬 Gmail SMTP Alert Setup
Used app password for SMTP auth

Configured Media Type > Email in Zabbix with:

   SMTP Server: smtp.gmail.com

   Port: 587

   Username: your Gmail

   Password: app password
 

### ⚠️ Challenges & Solutions
        Challenge	                              Solution
Forgot MySQL password	                      Reset via safe mode
Zabbix version mismatch with Ubuntu 24.04	  Downgraded to Ubuntu 22.04.5
Missing MySQL in web config	                  Corrected socket path and used correct DB port
Admin account blocked	                      Cleared failed login attempts in DB manually
 




#### Summary : A full guide to installing and configuring Zabbix on Ubuntu Server 22.04.5 using MySQL, covering system setup, frontend configuration, and real-time monitoring.

Sections include:

Project overview

Tech stack used (Zabbix 7.0, Ubuntu Server 22.04, MySQL, Apache)

Installation steps summary

Challenges & solutions

How to use this repo

Screenshots preview

License

#### ✅ Completed Objectives
 Zabbix Installed and Running

 Frontend Configured

 MySQL Connected Successfully

 Email Alerts Working

 Dashboard Customized

 Agent Installed on Hosts


 ###### 👨‍💻 Author
Theekshani CS/2020/042 

For university coursework on Open Source Network Monitoring Tools