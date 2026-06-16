# Day 34 – Creating, Managing and Deleting Aliases in Linux

## Lab Summary (June 10th, 2026)

This lab covers how to create, use, and remove both temporary and permanent command aliases in Linux to improve administrator productivity.

### Topics Covered

- **What is an alias?** A shortcut name for a longer command (e.g., `alias lh='ls -l /root'` lets you type `lh` instead of `ls -l /root`). Syntax: `alias alias_name='actual_command'`.
- **Viewing aliases**: `alias` lists all currently defined aliases (many distros predefine `ll`, `la`, `l`, etc.).
- **Temporary aliases**: Created with `alias name='command'`; only exist for the current session and are lost on logout, terminal close, or reboot.
- **Removing temporary aliases**: `unalias name` removes it immediately (running it afterward gives "command not found").
- **Permanent aliases**: Added as a line in `~/.bashrc` (e.g., `alias llroot='ls -l /root'`), then activated with `source ~/.bashrc` so they persist across sessions and reboots.
- **Removing permanent aliases**: Delete the line from `~/.bashrc` and re-run `source ~/.bashrc`.
- **Practical admin aliases**: e.g., `mylogs='ls -l /var/log'`, `mynet='ip addr'`, `mydisk='df -h'`, `mymem='free -h'`, `myproc='ps -ef'`.

---

## Review Questions — Answers

1. **What is an Alias?**
   A shortcut/alternate name for a command or sequence of commands.

2. **Why are aliases useful?**
   They simplify long commands, save time, reduce typing errors, and increase productivity.

3. **What command displays all aliases?**
   `alias` (run with no arguments).

4. **What command creates an alias?**
   `alias alias_name='actual_command'`.

5. **What command removes an alias?**
   `unalias alias_name`.

6. **What is the difference between a temporary alias and a permanent alias?**
   A temporary alias only exists for the current session (lost on logout/terminal close/reboot), while a permanent alias is stored in a config file (like `~/.bashrc`) and persists across sessions and reboots.

7. **Which file is commonly used to store permanent aliases?**
   `~/.bashrc`.

8. **What does `source ~/.bashrc` do?**
   It reloads the `.bashrc` file in the current shell session, applying any changes (like new aliases) without needing to log out and back in.

9. **Why should Linux Administrators use aliases?**
   To streamline repetitive tasks, reduce errors from retyping long/complex commands, and work more efficiently.

10. **Give three examples of aliases you would use daily.**
    Examples: `mylogs='ls -l /var/log'` (check logs), `mydisk='df -h'` (check disk usage), `mymem='free -h'` (check memory usage) — or `myproc='ps -ef'` and `mynet='ip addr'`.
