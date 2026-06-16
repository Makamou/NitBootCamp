# Day 36 – Changing Date and Time on the Linux Command Line

## Lab Summary (June 12th, 2026)

This lab covers viewing, formatting, changing, and restoring the Linux system clock, plus why accurate time matters for system administration.

### Topics Covered

- **Why time matters**: Logging, security auditing, authentication, cron jobs, backups, monitoring, databases, SSL certificates, and network troubleshooting all depend on accurate system time.
- **Viewing date/time**: `date` shows the current date, time, and timezone.
- **Custom formats**: `date +"%Y-%m-%d"` (date only), `date +"%H:%M:%S"` (time only), `date +"%A %d %B %Y %H:%M:%S"` (full readable format).
- **Changing the date only**: `date +%Y%m%d -s "20260615"` (requires root).
- **Changing the time only**: `date +%T -s "14:30:00"`.
- **Changing date and time together**: `date -s "2026-06-20 09:15:00"`.
- **Verifying changes**: `date` and `uptime`.
- **Restoring correct time**: manually with `date -s "..."`, or via NTP — check status with `timedatectl status`, `systemctl status chronyd`, `cat /etc/chrony.conf`, and `chronyc sources -v` (the `^*` marks the active NTP source).
- **Real-world impact**: A site outage traced to an "SSL Certificate Not Yet Valid" error was caused by an incorrect server date — illustrating how clock errors cause seemingly unrelated problems.

**Golden Rule: Always Verify System Time Before Troubleshooting Complex Problems** — check `date`, `timedatectl`, and `uptime` early in any troubleshooting session.

---

## Review Questions — Answers

1. **What command displays the current date and time?**
   `date`.

2. **Why is system time important?**
   It underpins logging, security auditing, authentication, scheduled tasks (cron), backups, monitoring, databases, and SSL certificate validity — incorrect time can break or misrepresent all of these.

3. **Which command changes only the date?**
   `date +%Y%m%d -s "YYYYMMDD"` (e.g., `date +%Y%m%d -s "20260615"`).

4. **Which command changes only the time?**
   `date +%T -s "HH:MM:SS"` (e.g., `date +%T -s "14:30:00"`).

5. **Which command changes both date and time?**
   `date -s "YYYY-MM-DD HH:MM:SS"` (e.g., `date -s "2026-06-20 09:15:00"`).

6. **Why must a System Administrator verify changes?**
   To confirm the system clock was actually updated correctly and matches the intended date/time before relying on it for other operations.

7. **What is NTP?**
   Network Time Protocol — a service that automatically synchronizes a system's clock with accurate external time servers.

8. **Why are timestamps important?**
   They record exactly when events (file changes, log entries, logins) occurred, which is essential for auditing, troubleshooting, and correlating events across systems.

9. **What problems can incorrect time cause?**
   Incorrect logs, backup failures, authentication failures, SSL certificate errors, and scheduled jobs (cron) running at the wrong time.

10. **How can you verify the current system time?**
    Run `date` (and optionally `timedatectl` or `uptime`) to check the current date, time, timezone, and clock sync status.
