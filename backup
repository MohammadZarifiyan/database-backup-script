#!/bin/bash

DATE=`date +%Y-%m-%d_%H%M`
LOCAL_BACKUP_DIR="/tmp"

FTP_SERVER="<ftp server>"
FTP_USERNAME="<ftp username>"#Fill here
FTP_PASSWORT=$(echo <base64 encoded password> | base64 --decode)#Fill here
FTP_UPLOAD_DIR="/backup"

LOG_FILE=/tmp/backup-$DATE.log

FILE_NAME=$DATE-$1.sql.gz

mysqldump $1 | gzip > $LOCAL_BACKUP_DIR/$FILE_NAME

ftp -invp $FTP_SERVER <<EOF
    user $FTP_USERNAME $FTP_PASSWORT
    binary
    lcd $LOCAL_BACKUP_DIR
    cd $FTP_UPLOAD_DIR
    put $FILE_NAME
    quit
EOF >> $LOG_FILE
