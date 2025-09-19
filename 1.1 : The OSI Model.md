

# 🏢 OSI Model – 7 Layers 

## 1️⃣ **Physical Layer (Layer 1)**

👉 **Main Work:** Raw data (bits = 0s & 1s) কে electrical signal, light signal, বা radio wave আকারে পাঠানো।

🔹 **What It Does:**

- Cables, connectors, voltages, frequency handle করে  
- শুধু “signal send & receive” করে, data বুঝে না  
- এখানে Protocol নেই, শুধু hardware standard আছে

🔹 **Examples:**

- Ethernet cables (Cat5e, Cat6)  
- Fiber optics  
- Wi-Fi signal  
- Hubs, Repeaters

🔹 **Interview Keywords:**

- “Layer 1 problem = Bad cable / No signal / Weak Wi-Fi”  
- Devices: Hub, Repeater, Cables, NIC (partially)

---

## 2️⃣ **Data Link Layer (Layer 2)**

👉 **Main Work:** Device-to-device communication, framing & error detection

🔹 **What It Does:**

- Data কে frame আকারে পাঠায়  
- Device-এর unique hardware address ব্যবহার করে – **MAC Address**  
- Error detection করে CRC (Cyclic Redundancy Check) দিয়ে  
- Flow control maintain করে

🔹 **Examples:**

- Ethernet (IEEE 802.3)  
- Wi-Fi (IEEE 802.11)  
- Switch (Layer 2 device)

🔹 **Interview Keywords:**

- “Layer 2 = Switching & MAC address”  
- Devices: Switch, Bridge  
- Problems: Duplicate MAC, Switch loop, Frame error

---

## 3️⃣ **Network Layer (Layer 3)**

👉 **Main Work:** Logical addressing (IP address) & routing

🔹 **What It Does:**

- Data কে packet আকারে পাঠায়  
- Routing করে – কোন পথে data যাবে সেটা ঠিক করে  
- Fragmentation করে – বড় packet কে ছোট করে পাঠায়

🔹 **Protocols:**

- IPv4, IPv6  
- ICMP (ping, traceroute)  
- IPsec (security at Layer 3)

🔹 **Examples:**

- Routers, Layer 3 Switch  
- IP addresses (e.g., 192.168.x.x)

🔹 **Interview Keywords:**

- “Layer 3 = Router & IP address”  
- Problems: Wrong IP, Subnet mismatch, Routing issue

---

## 4️⃣ **Transport Layer (Layer 4)**

👉 **Main Work:** End-to-end delivery of data + Reliability

🔹 **What It Does:**

- Data কে segment আকারে ভাগ করে  
- Error correction & re-transmission handle করে  
- Port number assign করে (e.g., Port 80 = HTTP, Port 443 = HTTPS)

🔹 **Protocols:**

- **TCP (Transmission Control Protocol):** Reliable, ordered, slower  
- **UDP (User Datagram Protocol):** Fast, not reliable

🔹 **Examples:**

- Web browsing (TCP 80/443)  
- Online gaming (UDP 27015)  
- DNS (UDP 53)

🔹 **Interview Keywords:**

- “Layer 4 = Ports (TCP/UDP)”  
- Problems: Firewall block ports, TCP handshake issue

---

## 5️⃣ **Session Layer (Layer 5)**

👉 **Main Work:** Start, manage, and end communication sessions

🔹 **What It Does:**

- দুই device-এর মধ্যে session establish করে (handshake)  
- Session maintain করে (timeout, reconnect)  
- Synchronization support করে

🔹 **Examples:**

- Remote login (Telnet, SSH)  
- Video conferencing session  
- NetBIOS

🔹 **Interview Keywords:**

- “Layer 5 = Session start/end”  
- Problems: Session timeout, VPN tunnel drop

---

## 6️⃣ **Presentation Layer (Layer 6)**

👉 **Main Work:** Data translation, encryption, compression

🔹 **What It Does:**

- Data কে human-friendly format-এ convert করে  
- Encryption / Decryption করে  
- Compression (ZIP, JPEG) করে

🔹 **Examples:**

- SSL/TLS (HTTPS security)  
- JPEG, PNG image formats  
- ASCII, Unicode text conversion

🔹 **Interview Keywords:**

- “Layer 6 = Encryption, compression, data format”  
- Problems: SSL certificate error, Encoding mismatch

---

## 7️⃣ **Application Layer (Layer 7)**

👉 **Main Work:** User interface & application-level communication

🔹 **What It Does:**

- Final layer যেখানে user directly interact করে  
- Application protocols run করে

🔹 **Protocols:**

- HTTP / HTTPS (web)  
- FTP (file transfer)  
- SMTP / POP3 / IMAP (email)  
- DNS (domain name resolution)

🔹 **Examples:**

- Gmail, YouTube, WhatsApp  
- Browser (Chrome, Firefox)

🔹 **Interview Keywords:**

- “Layer 7 = Apps & Application protocols”  
- Problems: App not working, DNS failure, Web server down

---

## 📊 Quick Layer & Function Table

| Layer | Name         | Data Unit | Device/Example      | Keywords             |
|-------|--------------|-----------|---------------------|----------------------|
| 7     | Application  | Data      | Browser, HTTP       | Apps & Protocols     |
| 6     | Presentation | Data      | SSL, JPEG           | Encryption, Format   |
| 5     | Session      | Data      | SSH, NetBIOS        | Start/End session    |
| 4     | Transport    | Segment   | TCP/UDP, Ports      | Reliable delivery    |
| 3     | Network      | Packet    | Router, IP address  | Routing & IP         |
| 2     | Data Link    | Frame     | Switch, MAC address | Switching            |
| 1     | Physical     | Bit       | Cable, Wi-Fi        | Signals              |

---

✅ **Ready to push to GitHub!**  
If you want, I can help you add a README intro, tag it for Bengali learners, or even structure it as a learning module. Want to take it further?
