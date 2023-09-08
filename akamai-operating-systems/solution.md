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
4. Execute `sudo chown :sharegroup srv/sharedirectory` to change the group ownership of the directory.
5. Execute `sudo chmod 770 srv/sharedirectory` to set appropriate permissions.

Encryption of Shared Directory:
1. Install encryption tools via `sudo apt install ecryptfs-utils cryptsetup`.
2. Follow the steps to encrypt the sharedDirectory.

File Structure and Sample Files:
1. Execute `sudo touch /home/dummyuser/sharedDirectory/sample1.txt` and `sudo touch /home/dummyuser/sharedDirectory/sample2.txt` to add two sample files.

Permissions:
1. Add the manager to the sudoers file: `sudo usermod -aG sudo manager`.

Install Software:
1. Execute `sudo apt update` and then `sudo apt install [software-package-names]` to install desired software.

Backup:
1. Create a text file (e.g., backup_commands.txt) with the commands needed for backup.
2. Use cron for automated backups. Execute `sudo crontab -e` and add a line like `0 2 * * * tar -czf /path/to/backup/location/backup-$(date +\%Y\%m\%d).tar.gz /path/to/data` to perform a compressed backup every day at 2 AM.