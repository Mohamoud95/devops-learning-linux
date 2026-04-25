# 01. Linux File System Hierarchy

Understanding the Linux file system hierarchy is crucial for navigating and managing a Linux environment. Linux uses a unified directory structure where everything starts from the root (`/`).

## Key Directories

- **`/` (Root)**: The top-level directory. All other directories branch off from here. Only the `root` user has write privileges under this directory.
- **`/bin` (User Binaries)**: Contains essential executable command binaries (e.g., `ls`, `cp`, `bash`) that must be available for single-user mode and to all users.
- **`/sbin` (System Binaries)**: Similar to `/bin`, but contains system administration commands typically executed by the `root` user (e.g., `iptables`, `reboot`, `fdisk`).
- **`/etc` (Configuration Files)**: Contains core configuration files required by all programs, as well as startup/shutdown shell scripts. **Never** contains executable binaries.
- **`/dev` (Device Files)**: Contains special device files representing hardware components (e.g., `/dev/sda` for the primary hard drive, `/dev/null` for the bit bucket).
- **`/proc` (Process Information)**: A virtual filesystem providing detailed information about running processes and the system kernel. For example, `/proc/cpuinfo` contains CPU details.
- **`/var` (Variable Data)**: Contains files whose content is expected to continually change during normal operation, such as system logs (`/var/log`), spool files (`/var/spool`), and temporary files (`/var/tmp`).
- **`/usr` (User Programs)**: The secondary hierarchy for read-only user data. Contains the majority of multi-user utilities and applications. Includes `/usr/bin`, `/usr/sbin`, and `/usr/lib`.
- **`/home` (Home Directories)**: Contains the personal directories for standard users (e.g., `/home/username`). Users have full write access to their own home directory.
- **`/boot` (Boot Loader Files)**: Contains files required for the boot process, including the Linux kernel and the bootloader (like GRUB) configurations.
- **`/opt` (Optional Applications)**: Used for the installation of add-on, third-party application software packages.
- **`/mnt` / `/media` (Mount Points)**: Temporary mount points for physically mounting removable media (like USB drives) or temporary filesystems.
- **`/tmp` (Temporary Files)**: Used for storing temporary files created by system and users. Files here are usually deleted upon system reboot.
