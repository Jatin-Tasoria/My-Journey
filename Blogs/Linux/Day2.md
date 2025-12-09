# Understanding file permissions, Users, Groups and essential commands
After getting familiar with linux file system on Day 1, today is all about file permissions,
user, groups and some essential but powerful everyday commands.

## Understanding file permission
Permission determines who can read, write or execute a file and a directory.
Every file has three permissions for three categories of users.

### User Categories
1. Owner (u): The user who created the file.
2. Group (g): The users who are part f the same group
3. Other (o): Everyone else.

### Permission types
1. Read (r): Allows viewing file.
2. Write (w): Allows modifying file context.
3. Execute (x): Allows executing files as programs or accessing directories.

> **Viewing File permissions**
- Use command: ls -l
  - Permission Indicators
    - -indicates a regular file
    - rw-(Owner): Read & Write.
    - r--(Group): Read Only.
    - r--(Other): Read Only.
  
Eg:
```bash
-rw-r--r-- <filename>
```
---

## Modifying permissions
### Use chmod to change permission
> Changing permissions using chmod with symbolic operators(+,-,=)
  - Add permission(+)
  - Remove permission(-)
  - Set exact permission(=)

Eg:
```bash
chmod u+x script.sh
chmod g-w file.txt
```
> Changing permissions with octal mode
  Permissions can be set using numeric values.
  - 4 : Read(r)
  - 2 : Write(w)
  - 1 : Execute(x)
  - Combine values to set permissions

Eg:
```bash
chmod 764 script.sh
``` 
---

### Use chown to change ownership of file
- Change file owner:
  Use chown command to change the owner of a file.
- Change file group:
  Use chown command to change the group of a file.
- Change both group and owner:
  Use chown command to change the group and owner of a file.
- Recursively change ownership
  Use the -R option with chown to change ownership for directories and their contexts.

Eg:
```bash
chown [new_owner] [file]
chown :[new_group] [file]
chown [new_owner]:[new_group] [file]
```

## User and Groups
- User: Individuals who use the Linux system. Each user has a unique UID.
- Group: A collection of users. Useful for setting permissions n files/folders for multiple users.

### User management command
1. Add a new user
```bash
 useradd [options] <username>
 ```
- Options:
  - -m : creates the user's home directory.
  - -g : assigns the new user to an already existing group.
  - -p : sets an encrypted password.

2. To check user is created
```bash
id <username>
```

3. To set password after user is created
```bash
passwd <username>
```
4. To delete a user
```bash
userdel [option] <username>
```
- options:
  - -r : remove user's home directory as well.
  - -f : force removal f user.

### Group management command
1. To add new user
```bash
groupadd <groupname>
```

2. To delete a group
```bash
groupdel <groupname>    
```

3. To manage password and membership
```bash
gpasswd [options] <groupname>
```

- Options:
  - -a : Add user to group
  - -d : Remove user from group
  - -A : Set group admin
  - -M : Set group members(overwrite the old ones)

## Essential Commands
| Commands | Purpose                |
|----------|----------------------------|
| pwd      | Shows current directory    |
| ls       | Shows content of pwd       |
| cd       | Change current directory   |
| touch    | To create a new file       |
| rm       | To remove a file           |
| mkdir    | To make a new directory    |
| rmdir    | To remove a directory      |
| man      | Opens a manual page        |
| clear    | Clears terminal screen     |
| cp       | Copy a file                |
| mv       | Move or rename a file      |