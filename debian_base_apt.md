
### **Basic Package Management**
| Command                      | Description                                                         |
| ---------------------------- | ------------------------------------------------------------------- |
| `sudo apt update`            | Update the package list (always run this first).                    |
| `sudo apt upgrade`           | Upgrade all installed packages.                                     |
| `sudo apt full-upgrade`      | Upgrade packages and handle dependencies (may remove old packages). |
| `sudo apt install <package>` | Install a package.                                                  |
| `sudo apt remove <package>`  | Remove a package (keeps config files).                              |
| `sudo apt purge <package>`   | Remove a package and its config files.                              |
| `sudo apt autoremove`        | Remove unused dependencies.                                         |
| `sudo apt clean`             | Clear downloaded `.deb` files from `/var/cache/apt/archives`.       |
| `sudo apt autoclean`         | Remove old versions of cached packages.                             |

---

### **Searching & Information**
| Command                 | Description                         |
| ----------------------- | ----------------------------------- |
| `apt search <keyword>`  | Search for a package.               |
| `apt show <package>`    | Show detailed info about a package. |
| `apt list --installed`  | List all installed packages.        |
| `apt list --upgradable` | List packages that can be upgraded. |
| `apt depends <package>` | Show package dependencies.          |

---

### **Managing Repositories**
| Command                          | Description                                                |
| -------------------------------- | ---------------------------------------------------------- |
| `sudo apt-add-repository <repo>` | Add a new repository (needs `software-properties-common`). |
| `sudo apt edit-sources`          | Edit `/etc/apt/sources.list`                               |

---

### **Troubleshooting & Fixes**
| Command                         | Description                            |
| ------------------------------- | -------------------------------------- |
| `sudo apt --fix-broken install` | Fix broken dependencies.               |
| `sudo dpkg --configure -a`      | Fix interrupted package installations. |
| `sudo apt-get check`            | Check for dependency problems.         |
