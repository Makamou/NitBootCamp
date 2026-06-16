# Day 32 – Login Process, systemd, Shells and Initialization Files

## Lab Summary (June 8th, 2026)

This lab covers basic Linux system administration fundamentals through 12 hands-on tasks: system identification, shell basics, filesystem navigation, networking, troubleshooting commands, initialization files, and safe config editing practices (backup first, change later).

### Topics Covered

- Checking kernel and OS version (`uname -a`, `uname -r`, `cat /etc/os-release`)
- Verifying systemd runs as PID 1 (`ps 1`, `ps -e`)
- Identifying the current shell (`echo $SHELL`) and its PID (`ps $$`, `echo $$`, `echo $0`)
- Exploring the `/etc` configuration directory
- Reading `/etc/shells` via absolute and relative paths
- Using `ping` to test connectivity and stopping processes with `Ctrl + C`
- Running basic troubleshooting commands (`date`, `uptime`, `hostname`, `whoami`, `pwd`, `cd ~`)
- Identifying global initialization files (`/etc/profile`, `/etc/bashrc`)
- Backing up critical configuration files before editing

**Golden Rule: Backup first, change later.**

---

## Final Review Questions — Answers

1. **What command shows the kernel version?**
   `uname -r` (or `uname -a` for full kernel info).

2. **What command displays operating system information?**
   `cat /etc/os-release`.

3. **What is PID 1?**
   The first process started by the kernel at boot — on most modern Linux systems, this is `systemd`.

4. **Why is systemd important?**
   It's the parent process of nearly all other processes and manages system initialization, services, and shutdown.

5. **What command displays your current shell?**
   `echo $SHELL`.

6. **What command displays your shell PID?**
   `echo $$` (or `ps $$` to show the process details).

7. **What is the purpose of the `/etc` directory?**
   It holds system-wide configuration files (e.g., `/etc/profile`, `/etc/passwd`, `/etc/shells`).

8. **What is the difference between an Absolute Path and a Relative Path?**
   An absolute path starts from root (`/etc/shells`) and works from anywhere; a relative path (`shells`) is interpreted relative to the current working directory.

9. **What does the ping command test?**
   Network connectivity, DNS resolution, internet access, response time, and reachability of remote hosts.

10. **How do you stop a running process?**
    Press `Ctrl + C`.

11. **What are the two major Global Initialization Files?**
    `/etc/profile` (login shells) and `/etc/bashrc` (interactive/non-login shells).

12. **Why should configuration files be backed up before modification?**
    To allow recovery to a working state if changes cause errors or break the system.

13. **What is the difference between `rm` and `rmdir`?**
    `rm` removes files (and with `-r`, directories and their contents); `rmdir` removes only empty directories.
