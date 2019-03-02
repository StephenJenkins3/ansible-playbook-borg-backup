Backup with borg
=======================

This playbook will backup a local folder on a remote server using borg. Borg must be installed on the remote server.

Usage example
-------------

### with ansible only

ansible-playbook borg-backup/main.yml
    -e ssh_connection=myserver@backup_user
    -e private_key_path=/path/to/private/key
    -e borg_repo_path=/home/backup_user/borg_repositories
    -e borg_repo_name=folder_to_backup
    -e borg_passphrase=wHaTever
    -e local_folder=/var/backup/folder_to_backup

### Using the borgbackup-cron image

See https://gitlab.com/ovski-projects/infra/docker-images/borgbackup-cron