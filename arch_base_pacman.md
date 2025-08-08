There're two types of package in arch. The first is offical packages, they're maintained by Arch Linux developers and package maintainers. they're also pre-built and can be installed by `pacman command`. The second is AUR(Arch User Repository) that are developed and maintainced by Arch User Community (can be installed by paru, yay, etc)

Basic `pacman` and `paru` command
```sh
pacman <operation> [options] [targets]
operation:
-D --database
-Q --query
-R --remove
-S --sync
-U --upgrade

TRANSACTION OPTIONS (APPLY TO -S, -R AND -U)
-d --nodeps(skips dependency check) (pecify this option twice to skip all dependency checks)

REMOVE OPTIONS (APPLY TO -R)
-c, --cascade (specify one for clean cache (keep the latest version), twice for clean all cache packages)
-n, --nosave (remove conflict files)
-s, --recursive (remove dependecies)
-u, --unneeded (remove unneeded dependcies)
SYNC OPTIONS (APPLY TO -S)
-c Clean cache
-s Search package
-u Upgrade packages
-y sync new package database
QUERY OPTIONS (APPLY TO -Q)
-q less package info
-i more package info
```


## **1. System Update & Upgrade**

Update package databases and upgrade all packages
  ```bash
  sudo pacman -Syu
  ```
  
Update package databases only (no upgrade)
  ```bash
  sudo pacman -Sy
  ```
  
Upgrade packages (without syncing databases)
  ```bash
  sudo pacman -Su
  ```
  
---

## **2. Installing Packages**
Install a package
  ```bash
  sudo pacman -S <package_name>
  ```
  
Install multiple packages at once
  ```bash
  sudo pacman -S <package1> <package2> <package3>
  ```
  
Install a `.pkg.tar.zst` file (local package)
  ```bash
  sudo pacman -U /path/to/package.pkg.tar.zst
  ```

---

## **3. Removing Packages**
Remove a package (keep dependencies)
  ```bash
  sudo pacman -R <package_name>
  ```
  
Remove a package + unused dependencies
  ```bash
  sudo pacman -Rs <package_name>
  ```
  
Remove a package + dependencies + config files
  ```bash
  sudo pacman -Rns <package_name>
  ```
  
---

## **4. Querying Packages**

List installed packages
  ```bash
  pacman -Q
  ```
  
Check if a specific package is installed
  ```bash
  pacman -Q <package_name>
  ```
  
---

## **5. Cleaning Up**
Clear package cache (keeps latest versions)
  ```bash
  sudo pacman -Sc
  ```
  
Clear ALL cached packages
  ```bash
  sudo pacman -Scc
  ```

Downgrade a package
  ```bash
  sudo pacman -U oldversion.pkg.tar.zst
  ```
  
