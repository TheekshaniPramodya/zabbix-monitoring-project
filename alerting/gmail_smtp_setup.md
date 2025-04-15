### Gmail SMTP Setup for Zabbix Alerts

1. Enable 2FA in Gmail.
2. Generate an App Password for SMTP usage.
3. In Zabbix:
   - Go to Administration > Media Types > Email.
   - SMTP Server: smtp.gmail.com
   - SMTP Port: 587
   - SMTP HELO: gmail.com
   - SMTP Email: your-email@gmail.com
   - Authentication: Username & App Password
