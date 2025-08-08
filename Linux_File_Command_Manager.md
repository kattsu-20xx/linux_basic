
### **1. File Navigation**
| Command | Description |
|---------|-------------|
| `pwd`   | Print the current working directory |
| `ls`    | List files and directories |
| `ls -l`  | List files in long format (details) |
| `ls -a` | List all files (including hidden) |
| `cd`    | Change directory |
| `cd ~`  | Go to the home directory |
| `cd ..` | Move up one directory |
| `cd -`  | Switch to the previous directory |

---

### **2. File Operations**
| Command | Description |
|---------|-------------|
| `touch file.txt` | Create an empty file |
| `cat file.txt` | Display file content |
| `less file.txt` | View file page by page |
| `head file.txt` | Show first 10 lines of a file |
| `tail file.txt` | Show last 10 lines of a file |
| `nano file.txt` | Edit a file using Nano editor |
| `vim file.txt` | Edit a file using Vim editor |
| `cp file1.txt file2.txt` | Copy a file |
| `mv file1.txt newname.txt` | Rename or move a file |
| `rm file.txt` | Delete a file |
| `rm -r dir/` | Delete a directory recursively |
| `ln -s file.txt link_name` | Create a symbolic (soft) link |

---

### **3. Directory Operations**
| Command              | Description                                                        |
| -------------------- | ------------------------------------------------------------------ |
| `mkdir dirname`      | Create a directory                                                 |
| `mkdir -p dir1/dir2` | Create nested directories                                          |
| `rmdir dirname`      | Remove an empty directory                                          |
| `rm -r dirname`      | Remove a directory and its contents                                |

---

### **4. File Permissions & Ownership**
| Command | Description |
|---------|-------------|
| `chmod 755 file.txt` | Change file permissions (read/write/execute) |
| `chown user:group file.txt` | Change file owner and group |
| `chgrp groupname file.txt` | Change file group ownership |

---

### **5. File Searching**
| Command                       | Description                   |
| ----------------------------- | ----------------------------- |
| `find /path -name "file.txt"` | Search for files by name      |
| `grep "text" file.txt`        | Search for text inside a file |
| `locate file.txt`             | Find files quickly            |

---

### **6. File Compression & Archiving**
| Command | Description |
|---------|-------------|
| `tar -cvf archive.tar dir/` | Create a tar archive |
| `tar -xvf archive.tar` | Extract a tar archive |
| `gzip file.txt` | Compress a file (creates `.gz`) |
| `gunzip file.txt.gz` | Decompress a `.gz` file |
| `zip archive.zip file.txt` | Create a ZIP archive |
| `unzip archive.zip` | Extract a ZIP archive |

---

### **7. Disk & Storage Management**
| Command | Description |
|---------|-------------|
| `df -h` | Show disk space usage |
| `du -sh dir/` | Check directory size |
| `mount /dev/sdX /mnt` | Mount a filesystem |
| `umount /mnt` | Unmount a filesystem |

---

### **8. File Transfer & Download**
| Command | Description |
|---------|-------------|
| `scp file.txt user@remote:/path` | Securely copy files over SSH |
| `rsync -avz src/ dest/` | Sync files efficiently |
| `wget http://example.com/file.txt` | Download a file from the web |
| `curl -O http://example.com/file.txt` | Download using cURL |

---

### **9. Miscellaneous**
| Command | Description |
|---------|-------------|
| `file file.txt` | Determine file type |
| `diff file1.txt file2.txt` | Compare two files |
| `stat file.txt` | Display file details (size, permissions, etc.) |
| `md5sum file.txt` | Generate a checksum for a file |
