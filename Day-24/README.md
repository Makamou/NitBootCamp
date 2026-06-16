### Linux Lab 23 – Review Questions

1. **What is an inode?**
   📄 An inode is a data structure that stores information about a file or directory.

2. **What information is stored in an inode?**
   🔍 Ownership, permissions, file size, timestamps, and disk block locations.

3. **Does an inode store the filename?**
   ❌ No. The filename is stored in the directory entry, not in the inode.

4. **What command displays disk space usage?**
   💾 `df -h`

5. **What command displays inode usage?**
   📊 `df -i`

6. **Can a filesystem have free disk space but no free inodes?**
   ✅ Yes.

7. **What happens when all inodes are consumed?**
   🚫 New files cannot be created even if disk space is available.

8. **Why does Linux display "No space left on device" when no inodes remain?**
   ⚠️ Because the system cannot allocate an inode for a new file.

9. **Why do administrators monitor both disk usage and inode usage?**
   👨‍💻 To prevent storage issues caused by either full disk space or inode exhaustion.

10. **What command can be used to check inode utilization on a filesystem?**
    📈 `df -i`

---

### 📝 Lab Summary

In this lab, I learned that an inode is a filesystem structure that stores metadata about files and directories, including permissions, ownership, size, timestamps, and data locations. I also learned the difference between disk space and inode usage. The command **`df -h`** shows available disk space, while **`df -i`** shows inode utilization. A system can report **"No space left on device"** even when free disk space exists because all available inodes have been used. The most useful command in this lab was **`df -i`**, as it helps identify inode exhaustion and troubleshoot file creation issues.
