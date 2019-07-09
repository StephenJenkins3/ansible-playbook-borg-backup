Backup with borg
=======================

This playbook will backup a local folder on a remote server using borg. Borg must be installed on the remote server.
Old backups will be pruned. 7 backups will be kept daily, 4 weekly, 6 monthly and 2 yearly.

Usage example
-------------

### With ansible

```bash
ansible-playbook borg-backup/main.yml \
    -e "ssh_connection=myserver@backup_user" \
    -e "private_key_path=/path/to/private/key" \
    -e "borg_repo_path=/home/backup_user/borg_repositories" \
    -e "borg_repo_name=folder_to_backup" \
    -e "borg_passphrase=wHaTever" \
    -e "local_folder=/var/backup/folder_to_backup"
```

### Use a docker image to run this playbook periodically

This can be useful to backup docker volumes using borg features. See https://github.com/Ovski4/docker-borgbackup-cron
