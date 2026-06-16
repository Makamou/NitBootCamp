# 🐧 Linux Lab 22 – Deleting Directories and Files Summary

## 📚 What I Learned

In this lab, I learned how to manage and remove files and directories in Linux. I started by reviewing the directories and files created in the previous lab using the `ls -l` command. I then learned how to delete empty directories with the `rmdir` command and discovered that it only works when a directory contains no files or subdirectories.

## 🗂️ Difference Between `rmdir` and `rm -rf`

One of the key lessons in this lab was understanding the difference between `rmdir` and `rm -rf`.

* 📁 **`rmdir`** removes only empty directories.
* 🗑️ **`rm -rf`** removes directories, subdirectories, and files recursively, even if they contain data.

When I created a file named `contacts.css` inside the `projects` directory, the `rmdir` command failed because the directory was no longer empty. Using `rm -rf` successfully removed the directory and all its contents.

## 📍 Working with Absolute and Relative Paths

I also practiced deleting directories using both Absolute and Relative Paths. An Absolute Path specifies the full location of a file or directory from the root (`/`), while a Relative Path works from the current directory. For example, deleting `docs` while already inside `/var/opt` demonstrated the use of a Relative Path.

## ⭐ Most Useful Command

The most useful command in this lab was:

```bash
rm -rf
```

because it allows the removal of non-empty directories and all their contents in a single command.

## 🆕 New Command Learned

The command that was new to me was:

```bash
rmdir
```

I learned that it is a safer way to remove directories because it only deletes directories that are completely empty.

## 📝 Overall Takeaway

This lab strengthened my understanding of Linux file and directory management. I learned how to safely remove empty directories, forcefully delete non-empty directories, and clear all contents inside a directory while preserving the parent directory. These skills are important for maintaining an organized Linux filesystem and managing storage efficiently.
