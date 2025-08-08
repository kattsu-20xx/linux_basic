There are some commands to manage network and network interface in linux

### **1. NetworkManager (nmcli & nmtui)**

 **`nmcli` (Command-Line Tool)**
 
- Check network status:
  ```sh
  nmcli general status
  ```
- List all connections:
  ```sh
  nmcli connection show
  ```
- Show active connections:
  ```sh
  nmcli connection show --active
  ```
- Connect/disconnect a network interface:
  ```sh
  nmcli connection up <connection-name>
  nmcli connection down <connection-name>
  ```
- Add a new Wi-Fi connection:
  ```sh
  nmcli device wifi connect <SSID> password <password>
  ```
- Reload NetworkManager:
  ```sh
  nmcli networking off && nmcli networking on
  ```

`nmtui`: **(Text-Based UI)**
  ```sh
  nmtui
  ```

---
### 2. `ip` Command

`ip [ OPTIONS ] OBJECT { COMMAND | help }`

**Some common OBJECT**: link, addr, route.
#### **OBJECT: link**
There are two common `link` options: show and set.

Show all device interface
```sh
ip link show # It wil list all NIs that Kernel recognized
```

Bring NIs up or down
```sh
ip link set dev wlan0 up
ip link set dev wlan0 down
```

Temporary change MAC address
```sh
ip link set dev wlan0 address CC-0E-A9-3D-CA-EC
```

#### **OBJECT: addr**
There are some common `addr` options: add, del, show

Show address
```sh
ip addr show # Show address of all NIs
```

Set static ip address
```sh
ip addr add 192.168.1.10/24 dev wlan0
```

Remove static ip Address
```sh
ip addr del 192.168.1.10/24 dev wlan0
```

#### **OBJECT: route** 
set the default Gateway configuration
```sh
ip route add default via 192.168.1.1
```

To delete a gateway
```sh
ip route del default
```

To show default gateway route
```sh
ip route show 
```

---

### 3. `ifconfig` Command

To Show interfaces:
  ```sh
  ifconfig -a
  ```
- Enable/disable an interface:
  ```sh
  ifconfig <interface> up
  ifconfig <interface> down
  ```
  
---


### 4. `ping`  (Connectivity Testing)**

To Ping a host:
  ```sh
  ping google.com
  ```

---

### 5. `ss` Command (Checking sockets)

- List all listening ports:
  ```sh
  ss -tulnp
  ```
- Show all TCP/UDP connections:
  ```sh
  ss -tua
  ```

---

### 6. `iwconfig` & `iw` (Wireless Tools)
- Show wireless interfaces:
  ```sh
  iwconfig
  ```
- Scan for Wi-Fi networks:
  ```sh
  iwlist <interface> scan
  ```
- Modern alternative (`iw` from `iproute2`):
  ```sh
  iw dev <interface> scan
  ```
