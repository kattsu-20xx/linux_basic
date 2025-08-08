Log is an important part of system troubouleshooting and there're some common log command for every aspect of linux system.

### 1. Systemd-based Logging

If your system uses `systemd`, most logs are handled by the `journald` service.

### ***`journalctl`: Systemd Based***

```sh
journalctl                # Show all logs
journalctl -b             # Show logs from current boot
journalctl -k             # Show only kernel logs
journalctl -u ssh.service # Show logs for specific service
journalctl --since "1 hour ago" --until "now"
journalctl -xe           # Show recent logs with errors (diagnostics)
```

Control journal size or status:

```bash
journalctl --disk-usage         # Show journal size
journalctl --vacuum-time=7d     # Delete logs older than 7 days
```

---

### 3. **`dmesg`Kernel Log Messages**

```sh
dmesg # Show all kernel logs
```

```sh

dmesg -T # Show timestamps
```

---

### 4. **Service Logs**

 `systemctl status` – View recent log info of a service

```bash
systemctl status nginx.service
```

---

### 5. **Login log**

```sh
last #Show last logged in users
```

```sh
lastlog # Show last login of all users
```

```sh
who # current logged-in users
```

---

### 6. **Log File Locations**

| Log File                                             | Description                  |
| ---------------------------------------------------- | ---------------------------- |
| `/var/log/syslog` or `/var/log/messages`             | General system logs          |
| `/var/log/auth.log` or `/var/log/secure`             | Authentication and sudo logs |
| `/var/log/dmesg`                                     | Boot-time kernel log         |
| `/var/log/kern.log`                                  | Kernel logs                  |
| `/var/log/Xorg.0.log`                                | X server log                 |
| `/var/log/wtmp`, `/var/log/btmp`, `/var/log/lastlog` | Login/logout records         |
| `/var/log/faillog`                                   | Failed login attempts        |
