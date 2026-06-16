# Day 35 – Understanding and Using the ping Command in Linux

## Lab Summary (June 11th, 2026)

This lab covers the `ping` command — how it works, its common use cases, and key options for network troubleshooting.

### Topics Covered

- **What is ping?** "Packet InterNet Groper" — sends an ICMP Echo Request to a remote host and listens for an ICMP Echo Reply to confirm connectivity, reachability, and routing.
- **Testing connectivity**: `ping google.com` (tests internet + DNS) and `ping 8.8.8.8` (tests raw IP reachability, bypassing DNS).
- **Stopping ping**: `Ctrl + C` ends the process and shows a summary (packets sent/received, loss, average response time).
- **Controlling packet count**: `-c` (count), e.g. `ping -c 4 google.com` sends exactly 4 packets.
- **DNS resolution check**: `ping -c 1 google.com` shows the resolved IP address next to the hostname.
- **Adjusting intervals**: `-i` sets the delay between packets (e.g., `-i 4` = every 4 seconds, `-i 0.5` = every half second, generating more traffic).
- **Summary-only output**: `-q` (quiet mode) suppresses per-packet replies and shows only final statistics.
- **Loopback testing**: `ping 127.0.0.1` (IPv4), `ping ::1` (IPv6), and `ping localhost` verify the local TCP/IP stack is functioning.
- **Help**: `ping --help` lists all available options.

**Recommended troubleshooting order**: 127.0.0.1 → localhost → own IP → default gateway → 8.8.8.8 → google.com — this isolates where a connectivity problem occurs.

---

## Review Questions — Answers

1. **What does ping stand for?**
   Packet InterNet Groper.

2. **Which protocol does ping use?**
   ICMP (Internet Control Message Protocol).

3. **What is ICMP?**
   A network-layer protocol used for diagnostic and control messages, such as the echo request/reply used by ping.

4. **Why do network administrators use ping?**
   To test connectivity, verify reachability of remote hosts, troubleshoot network issues, test DNS resolution, and measure response times.

5. **What does `ping google.com` test?**
   Internet connectivity and DNS resolution (it resolves the hostname to an IP and tests reachability).

6. **What does `ping 8.8.8.8` test?**
   Direct IP reachability/connectivity, without involving DNS resolution.

7. **What does the `-c` option do?**
   Limits ping to send a specific number (count) of packets, e.g. `-c 4` sends 4 packets.

8. **What does the `-i` option do?**
   Sets the interval (in seconds) between each packet sent.

9. **What does the `-q` option do?**
   Enables quiet mode — hides individual packet replies and shows only summary statistics.

10. **What does `Ctrl + C` do?**
    Stops the running ping process and displays a summary (packets sent/received, packet loss, average response time).

11. **What is the loopback address for IPv4?**
    127.0.0.1.

12. **What is the loopback address for IPv6?**
    ::1.

13. **What does a successful loopback test indicate?**
    The local TCP/IP stack is working correctly, independent of any external network connection.
