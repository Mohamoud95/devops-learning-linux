# Linux Commands Cheat Sheet

This document serves as a quick reference guide for essential Linux commands used frequently in DevOps and system administration.

## 1. File & Directory Management
- **`ls`**: List directory contents.
  - `ls -la`: List all files (including hidden) with detailed formatting.
- **`cd`**: Change directory.
  - `cd -`: Go to the previous directory.
- **`pwd`**: Print working directory.
- **`mkdir`**: Create a new directory.
  - `mkdir -p /path/to/dir`: Create nested directories.
- **`rm`**: Remove files or directories.
  - `rm -rf /dir`: Forcefully remove a directory and its contents recursively.
- **`cp`**: Copy files and directories.
  - `cp -r source/ dest/`: Copy directories recursively.
- **`mv`**: Move or rename files and directories.
  - `mv file.txt newname.txt`: Rename a file.

## 2. Viewing & Editing Files
- **`cat`**: Concatenate and print file contents.
- **`less` / `more`**: View file contents interactively (page by page).
- **`head` / `tail`**: Output the first/last parts of a file.
  - `tail -f /var/log/syslog`: Continuously follow new lines in a log file.
- **`nano` / `vim`**: Command-line text editors.

## 3. Searching & Processing Text
- **`grep`**: Search text for patterns.
  - `grep -r "error" /var/log/`: Recursively search for "error" in a directory.
- **`find`**: Search for files in a directory hierarchy.
  - `find / -name "*.conf"`: Find all `.conf` files.
- **`awk`**: Pattern scanning and processing language.
  - `awk '{print $1}' file.txt`: Print the first column of a file.
- **`sed`**: Stream editor for filtering and transforming text.
  - `sed 's/old/new/g' file.txt`: Replace all occurrences of "old" with "new".

## 4. System & Process Management
- **`top` / `htop`**: Display interactive system process and resource usage.
- **`ps`**: Report a snapshot of current processes.
  - `ps aux | grep nginx`: Find process IDs for 'nginx'.
- **`kill`**: Send a signal to a process.
  - `kill -9 <PID>`: Force kill a process.
- **`df`**: Report file system disk space usage.
  - `df -h`: Human-readable format.
- **`free`**: Display amount of free and used memory.
  - `free -m`: Display memory in Megabytes.
- **`systemctl`**: Control the systemd system and service manager.
  - `systemctl restart nginx`: Restart the nginx service.

## 5. Networking
- **`ping`**: Send ICMP ECHO_REQUEST to network hosts.
- **`curl`**: Transfer data from or to a server.
  - `curl -I https://example.com`: Fetch HTTP headers only.
- **`netstat` / `ss`**: Print network connections, routing tables, and interface statistics.
  - `netstat -tuln`: List all listening ports.
- **`ip`**: Show / manipulate routing, network devices, interfaces, and tunnels.
  - `ip addr`: Show IP addresses assigned to interfaces.

## 6. Permissions & Ownership
- **`chmod`**: Change file access permissions.
  - `chmod 755 script.sh`: Make a script executable.
- **`chown`**: Change file owner and group.
  - `chown user:group file.txt`: Change ownership.
