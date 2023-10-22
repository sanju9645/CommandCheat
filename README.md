# CommandCheat
Bits 'n' Bytes Bliss: My Nerd Cookbook


## Creating a log file in the Linux server

```
sudo touch log.log
```

> To monitor a log file in real-time
```
tail -f log.log
```

>To display the last N lines of the file
```
tail -n 10 log.log
```

## To list the modified files in the last 60 mins
```
find /var/www/html/sanju/ -cmin -60 -type f -printf '.' | wc -c
```

## To List the total count of modified files in last 60 mins
```
find /home/eliteh10/private/delivery/ -cmin -60 -type f -printf '.' | wc -c
```
>Another solution for count is
```
find /home/eliteh10/private/delivery/ -cmin -60 -type f | wc -l
```

## Sort Files Based on Time and Date
```
ls -l
ls -lt
ls -ltr
```
>to show hidden files
```
ls -latr
```

## Displaying file permission
```
stat -f %A file.txt
```

## To set the file size to zero
```
sudo truncate -s 0 /var/log/newLog.log
```

## To create symlinks
```
ln -s APP-2443/app.homewav.com html
```

## Renaming Git Branch
Follow the steps below to rename a Local and Remote Git Branch:
> 1. Start by switching to the local branch which you want to rename:
```
git checkout <old_name>
```
> 2. Rename the local branch by typing:
```
git branch -m <new_name>Copy
```

> 3. At this point, you have renamed the local branch.

>4. If you’ve already pushed the <old_name> branch to the remote repository, perform the next steps to rename the remote branch.

>5. Push the <new_name> local branch and reset the upstream branch:
```
git push origin -u <new_name>
```

>6. Delete the <old_name> remote branch
```
git push origin --delete <old_name>
```

## To see the currently running process in Linux
```
ps -aux
```
>To kill them
```
kill [PID]
kill -SIGTERM [PID]
```
>you may get an ‘operation not permitted’ error message. then
```
kill -9 [PID]   or
sudo kill -9 [PID] 
```

## To display line number in nano 
```
To display line number in nano 
nano -l foo.txt
nano --linenumbers foo.txt
```

## Screen
``` screen --version ```
> Starting Linux Screen
```
screen
```
>Starting Named Session
```
screen -S session_name
```
>Detach from Linux Screen Session
```
Ctrl+a d
```
>Reattach to a Linux Screen
```
screen -r
```
> If it is not working, try
```
screen -r -d <PID>
```

> To find the session ID list the current running screen sessions with
```
screen -ls
```

## MySQL: To see all foreign keys to a table or column?
> For a table
```
SELECT 
  TABLE_NAME,COLUMN_NAME,CONSTRAINT_NAME, REFERENCED_TABLE_NAME,REFERENCED_COLUMN_NAME
FROM
  INFORMATION_SCHEMA.KEY_COLUMN_USAGE
WHERE
  REFERENCED_TABLE_SCHEMA = '<database>' AND
  REFERENCED_TABLE_NAME = '<table>';
```

> For a column
```
SELECT 
  TABLE_NAME,COLUMN_NAME,CONSTRAINT_NAME, REFERENCED_TABLE_NAME,REFERENCED_COLUMN_NAME
FROM
  INFORMATION_SCHEMA.KEY_COLUMN_USAGE
WHERE
  REFERENCED_TABLE_SCHEMA = '<database>' AND
  REFERENCED_TABLE_NAME = '<table>' AND
  REFERENCED_COLUMN_NAME = '<column>';
```

## MySQL: delete a row ignoring foreign key constraint
```
SET foreign_key_checks = 0;
DELETE FROM calls WHERE id = 70628241;
SET foreign_key_checks = 1;
```

## php interactive shell
```
php -a
```

## scp command
```
scp ec2-user@devsp:/var/log/newLog.log /Users/macbook/Documents/
```

## Git user configuration
```
git config --global user.name "Sanju S Nath"
git config --global user.email "sanju@nethram.com"
```

