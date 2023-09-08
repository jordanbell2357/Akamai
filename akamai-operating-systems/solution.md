# Akamai SecureHub

User Creation:
1. Open the terminal and execute `sudo adduser manager` to create the manager user with sudo privileges.
2. Execute `sudo adduser salesperson` to create the salesperson user.
3. Execute `sudo adduser clientSupportIntern --force-badname` for the client support intern.
4. Execute `sudo adduser techTeamIntern --force-badname` for the tech team intern.

Modify Account Expiration:
1. For the manager, no action is needed as the account won't expire.
2. For the salesperson, execute `sudo chage -E "1 year" salesperson` to set expiration in 1 year.
3. For the interns, execute `sudo chage -E "6 months" clientSupportIntern` and `sudo chage -E "6 months" techTeamIntern`.

Group and Directory Creation:
1. Execute `sudo addgroup sharegroup` to create a new group for sharing files.
2. Execute `sudo usermod -aG sharegroup manager` and `sudo usermod -aG sharegroup salesperson` to add the manager and salesperson to the group.
3. Execute `sudo mkdir /srv/sharedirectory` to create the shared directory.
4. Execute `sudo chown :sharegroup /srv/sharedirectory` to change the group ownership of the directory.
5. Execute `sudo chmod 770 /srv/sharedirectory` to set appropriate permissions.


`gpg --full-gen-key`

`sudo mkdir -p /var/backups/SecureHub`

```bash
sudo chown manager:manager /var/backups/SecureHub
sudo chmod 700 /var/backups/SecureHub
```

`backup_commands.sh`

```bash
#!/bin/bash

# Current date variable
DATE=$(date +%Y%m%d)

# Directories to be backed up
USER_DIR1="/home/manager"
USER_DIR2="/home/salesperson"
USER_DIR3="/home/clientSupportIntern"
USER_DIR4="/home/techTeamIntern"
SHARED_DIR="/srv/sharedirectory"

# Backup destination (conventionally under /var/backups)
BACKUP_DIR="/var/backups/SecureHub"

# Ensure the backup directory exists
mkdir -p $BACKUP_DIR

# GPG recipient email (for encrypting backups)
GPG_RECIPIENT="SecureHub@Akamai.com"

# Create compressed and encrypted backups
tar -czf - $USER_DIR1 | gpg -e -r $GPG_RECIPIENT -o $BACKUP_DIR/manager_backup_$DATE.tar.gz.gpg
tar -czf - $USER_DIR2 | gpg -e -r $GPG_RECIPIENT -o $BACKUP_DIR/salesperson_backup_$DATE.tar.gz.gpg
tar -czf - $USER_DIR3 | gpg -e -r $GPG_RECIPIENT -o $BACKUP_DIR/clientSupportIntern_backup_$DATE.tar.gz.gpg
tar -czf - $USER_DIR4 | gpg -e -r $GPG_RECIPIENT -o $BACKUP_DIR/techTeamIntern_backup_$DATE.tar.gz.gpg
tar -czf - $SHARED_DIR | gpg -e -r $GPG_RECIPIENT -o $BACKUP_DIR/sharedDirectory_backup_$DATE.tar.gz.gpg
```

`sudo crontab -e`

`0 1 * * * /home/ubuntu/backup_commands.sh`

`gpg --armor --output public_key.asc --export 67D513D9394DAF08A6D334F66AFB0136AEBA2C61`

`sudo gpg --import public_key.asc`