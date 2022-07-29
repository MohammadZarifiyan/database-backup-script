# database-backup-script
A simple bash script that creates backup from specified database and uploads backup file to a FTP server.

# How to run ?
Please fill `FTP_SERVER`, `FTP_USERNAME` and `FTP_PASSWORT` first.

Notice: it's strongly recommended to use base64 encrypted password in `FTP_PASSWORD` variable.

Then run this command:
```bash
bash backup.sh <Your database name>
```

You can run this command using CronJob to take backup from database every day or etc.

# Contribution
All contribution will be accepted.

Todo:
- Use a more secure behavior to login to FTP server. (Atleast using `.env` file for FTP server credentials)
- Backup only specific database tables.
