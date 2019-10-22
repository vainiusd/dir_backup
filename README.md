# dir_backup
 
Run by issuing:  
ansible-playbook -i hosts playbook.yml

### Roles

#### files_by_dir

Uses inventroy variables to check locally existing directory (*local_path*) for files (by *pattern*, default is \*) that are newer than *age* (default is 12h).
Pattern allows using the same local directory multiple times with different types/naming of files.
These files are copied to remote storage corresponding directories (*remote_path*). 
If the directory will have only one configuration file that is refreshed and the latest copy should be kept in remote storage with a custom name, *custom_name* needs to be defined.

#### to_remote

Sends all files gathered in previous role to remote storage *remote_path*.
If *custom_name* is defined, the newest file is named accordingly and put in the same directory.

#### log_play

Logs play success locally in *joblog_path* and remotely in *remote_joblog_path*. Creates log files named *inventory_hostname*.log