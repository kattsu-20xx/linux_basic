
# Tài liệu Tổng hợp Quản trị Linux Cơ bản

## 1. Quản lý Mạng (Linux Networking Basics)

### Các lệnh phổ biến:

- `ifconfig`: Xem thông tin giao diện mạng.
  - **Ví dụ**: `ifconfig eth0` – Hiển thị thông tin của giao diện `eth0`.
- `ip -4 addr` / `ip -6 addr`: Xem địa chỉ IPv4/IPv6.
  - **Ví dụ**: `ip -4 addr show eth0` – Hiển thị IPv4 của giao diện `eth0`.
- `netstat`: Hiển thị thông tin kết nối mạng, định tuyến, giao diện, PID:
  - `netstat -a`, `-l`, `-r`, `-t`, `-u`, `-i`, `-p`, `-st`, `-e`
  - **Ví dụ**: `netstat -tulnp` – Xem các dịch vụ đang mở cổng và PID tương ứng.
- `ping`: Kiểm tra kết nối mạng, xác định mất gói.
  - **Ví dụ**: `ping google.com` – Gửi ICMP đến google để kiểm tra kết nối mạng.
- `curl`: Kiểm tra API, truyền dữ liệu từ/to máy chủ.
  - **Ví dụ**: `curl -I https://example.com` – Hiển thị tiêu đề HTTP từ trang.
- `tcpdump`: Bắt lưu lượng mạng, phân tích gói tin.
  - **Ví dụ**: `sudo tcpdump -i eth0 port 80` – Bắt các gói HTTP trên eth0.

### Trạng thái cổng:
- LISTEN, ESTABLISHED, TIME WAIT, FIN WAIT2.

---

## 2. Log Hệ thống (Advanced Log Parsing and Analysis)

### Cấu trúc Log:
- **Timestamp** | **Log Level** | **Component** | **Message** | **Additional Info**

### Công cụ phân tích log:
- `grep`: Tìm kiếm mẫu, regex, đếm dòng, tìm đệ quy.
  - **Ví dụ**: `grep ERROR /var/log/syslog`
- `sed`: Thay thế/xóa/in dòng khớp.
  - **Ví dụ**: `sed 's/error/ERROR/' logfile.log`
- `awk`: Phân tích theo trường, lọc, thống kê.
  - **Ví dụ**: `awk '{print $1, $3}' logfile.log` – In trường 1 và 3.
- `cut`: Cắt cột cụ thể, trích xuất IP, cấp độ log.
  - **Ví dụ**: `cut -d' ' -f4 logfile.log`
- `sort`, `uniq`: Sắp xếp, loại bỏ trùng, đếm số dòng lặp.
  - **Ví dụ**: `sort logfile.log | uniq -c`

### Kiểm tra log:
- Cron: `/var/log/syslog`
- Chuyển hướng output cron: `* * * * * sh script.sh &> log_file.log`
- Backup log trước khi thao tác.
- Kiểm tra lỗi phần cứng: `journalctl -k | grep -iE "error|fault|panic"`

---

## 3. Quản lý Người dùng (User Management)

### Loại người dùng:
- root (UID=0), system user, regular user.
- Kiểm tra UID/GID: `id`, `ps -u`, `/etc/passwd`, `/etc/group`
  - **Ví dụ**: `id username` – Hiển thị UID, GID của người dùng.

### Nhóm (Group):
- GID, nhóm chính và bổ sung, `/etc/group`
  - **Ví dụ**: `groups username` – Hiển thị nhóm người dùng tham gia.

### Quyền tệp:
- `ls -l`: Xem quyền rwx.
  - **Ví dụ**: `ls -l /etc/passwd`
- `chmod`: Thay đổi quyền (symbolic & octal mode)
  - **Ví dụ**: `chmod u+x script.sh`
- `chown`: Thay đổi chủ sở hữu và nhóm: `chown user:group file`, `-R`
  - **Ví dụ**: `chown user1:dev team.txt`

### Chuyển đổi người dùng:
- `su`, `su -`, `su user`
  - **Ví dụ**: `su -` – Chuyển sang tài khoản root với môi trường đầy đủ.
- `sudo`: Thực thi với quyền root, ghi log tại `/var/log/auth.log`
  - **Ví dụ**: `sudo apt update`

### Quản lý người dùng:
- Tạo người dùng: `useradd username`
  - **Ví dụ**: `sudo useradd -m user01`
- Đổi thông tin: `usermod -l`, `-d`, `-aG`, `-s`, `-e`, `-L`, `-U`, `-u`, `-g`
  - **Ví dụ**: `sudo usermod -aG sudo user01`
- Xóa người dùng: `userdel -r username`
  - **Ví dụ**: `sudo userdel -r user01`
- Đổi mật khẩu: `passwd username`
  - **Ví dụ**: `sudo passwd user01`

---

## 4. Quản lý Gói phần mềm (Managing Packages)

### Khái niệm:
- Package: Tập tin thực thi, thư viện, tài nguyên.
- Binary vs. Source.
- Phụ thuộc gói.

### Trình quản lý gói:
- apt (Debian/Ubuntu): `apt install`, `apt update`, `apt upgrade`, `apt remove`
  - **Ví dụ**:
    - `sudo apt install htop`
    - `sudo apt update && sudo apt upgrade`
    - `sudo apt remove nano`
- Log: `/var/log/dpkg.log`

### Kho phần mềm (Repositories):
- `/etc/apt/sources.list`
- Quá trình cài đặt:
  1. `apt update`
  2. `apt install <pkg>`
  3. Kiểm tra/phụ thuộc tự động
  4. `apt upgrade`

### GUI: Synaptic Package Manager.

### Cài gói thủ công:
- `.deb`:
  - Dòng lệnh: `sudo dpkg -i package.deb`
    - **Ví dụ**: `sudo dpkg -i chrome.deb`
  - GUI: Open With Other Application

---

**Chi tiết liên hệ: [instagram](https://www.instagram.com/_kogoro_/) 
