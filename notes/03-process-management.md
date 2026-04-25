# 03. Process Management

In Linux, a process is any currently executing instance of a program. Managing processes is a critical administrative skill for troubleshooting performance and ensuring system stability.

## Foreground vs. Background Processes

- **Foreground**: By default, commands run in the foreground, blocking the terminal until they complete.
- **Background**: You can append an ampersand (`&`) to a command to run it in the background, immediately returning control of the terminal.
  - Example: `sleep 60 &`

## Process Identification

Every process is assigned a unique identifier called the **PID (Process ID)**. The `init` or `systemd` process, which is the first process to start during boot, always has a PID of 1.

## Key Process Management Tools

### 1. `ps` (Process Status)
Provides a static snapshot of running processes.
- `ps`: Shows processes for the current shell.
- `ps aux`: A highly standard command to show all running processes across the system, including the user, CPU/RAM usage, and the command that started it.
- `ps -ef`: Another standard format for viewing all system processes.

### 2. `top` and `htop`
Provides a dynamic, real-time, interactive view of running processes and system resources (CPU, Memory, Swap).
- `top`: Built into most Linux distributions.
- `htop`: A more user-friendly, colorful alternative that allows scrolling and easier process termination (often needs to be installed via a package manager).

### 3. `kill`
Sends signals to processes, typically used to terminate them.
- `kill <PID>`: Sends a graceful termination signal (SIGTERM, 15). The process is asked to shut down cleanly.
- `kill -9 <PID>`: Sends a forceful kill signal (SIGKILL, 9). The kernel immediately terminates the process without allowing it to clean up. Use as a last resort.

### 4. `pgrep` and `pkill`
Allows you to find or kill processes based on their name rather than their PID.
- `pgrep nginx`: Returns the PIDs of all running `nginx` processes.
- `pkill -9 nginx`: Forcefully kills all processes named `nginx`.

## Process States
A process can be in several states:
- **Running (R)**: Currently executing or in the run queue.
- **Sleeping (S / D)**: Waiting for an event or resource (Interruptible or Uninterruptible).
- **Zombie (Z)**: A process that has terminated but its parent has not yet read its exit status. It consumes no resources other than an entry in the process table.
- **Stopped (T)**: Suspended, usually by a user signal (like pressing Ctrl+Z).
