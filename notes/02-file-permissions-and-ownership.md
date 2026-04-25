# 02. File Permissions & Ownership

Linux is a multi-user operating system, which necessitates a strict permissions model to govern who can access, modify, or execute files and directories.

## The Permission Model

Every file and directory in Linux has three distinct sets of permissions tied to three entities:
1. **User (Owner)**: The account that owns the file.
2. **Group**: Other users who are members of the file's assigned group.
3. **Others (World)**: Everyone else on the system.

For each entity, there are three types of permissions:
- **Read (`r`)**: Permission to view the file's contents or list the directory's contents.
- **Write (`w`)**: Permission to modify or delete the file, or add/remove files in a directory.
- **Execute (`x`)**: Permission to run the file as a program, or `cd` into a directory.

## Viewing Permissions

You can view permissions using `ls -l`. A typical output looks like this:
```
-rwxr-xr-- 1 user group 1024 Jan 1 12:00 script.sh
```

- `-`: Indicates it is a regular file (`d` would indicate a directory).
- `rwx`: The Owner has read, write, and execute permissions.
- `r-x`: The Group has read and execute permissions, but cannot write.
- `r--`: Others have only read permissions.

## Changing Permissions (`chmod`)

The `chmod` command modifies file permissions. It can be used in two modes:

### 1. Symbolic Mode
Uses letters to add (`+`), remove (`-`), or set (`=`) permissions.
- `chmod u+x script.sh` (Add execute permission for the User/Owner)
- `chmod g-w script.sh` (Remove write permission for the Group)
- `chmod o=r file.txt` (Set Others to exactly read-only)

### 2. Numeric (Octal) Mode
Uses a 3-digit number to represent the permissions for User, Group, and Others.
- Read = 4
- Write = 2
- Execute = 1

*Examples:*
- `chmod 755 script.sh`: User=7 (4+2+1, rwx), Group=5 (4+1, r-x), Others=5 (r-x).
- `chmod 644 file.txt`: User=6 (rw-), Group=4 (r--), Others=4 (r--). Typical for regular files.

## Changing Ownership (`chown`)

The `chown` command changes the owner and group of a file or directory.
- `chown username file.txt` (Changes owner)
- `chown username:groupname file.txt` (Changes owner and group)
- `chown -R username:groupname /path/to/dir` (Changes recursively for all contents)
