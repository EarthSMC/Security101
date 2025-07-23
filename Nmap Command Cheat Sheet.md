# 🔍 Nmap Command Summary (Cheat Sheet)

A quick reference guide to common and advanced Nmap scanning techniques.

---

## 🔧 Basic Scan Types

| Scan Type / Option           | Example Command                                           | Explanation                                                                 |
|-----------------------------|-----------------------------------------------------------|-----------------------------------------------------------------------------|
| **TCP SYN Scan (Stealth)**  | `sudo nmap -sS IP_target`                                | Sends half-open SYN packets to detect open ports while evading detection.  |
| **TCP Connect Scan**        | `nmap -sT IP_target`                                     | Uses full TCP connection (connect()) — useful without raw socket privileges.|
| **UDP Scan**                | `sudo nmap -sU IP_target`                                | Scans for open UDP ports. Slow and may produce many false negatives.       |
| **TCP Null Scan**           | `sudo nmap -sN IP_target`                                | Sends a TCP packet with no flags set — stealth scan to identify open ports.|
| **TCP FIN Scan**            | `sudo nmap -sF IP_target`                                | Sends FIN flag only — designed to bypass some simple firewall rules.       |
| **TCP Xmas Scan**           | `sudo nmap -sX IP_target`                                | Sends FIN, URG, and PSH flags — stealth scan to obfuscate origin.          |
| **TCP Maimon Scan**         | `sudo nmap -sM IP_target`                                | Exploits quirks in TCP stack using FIN/URG — avoids some packet filters.   |
| **TCP ACK Scan**            | `sudo nmap -sA IP_target`                                | Sends ACK packets — tests firewall rules or for filtered/unfiltered state. |
| **TCP Window Scan**         | `sudo nmap -sW IP_target`                                | Uses difference in TCP window size to guess port states.                   |
| **Custom TCP Flags Scan**   | `sudo nmap --scanflags URGACKPSHRSTSYNFIN IP_target`     | Sends custom combination of TCP flags — used in very stealthy scans.       |

---

## 🕵️‍♂️ Evading Detection

| Option / Scan Type         | Example Command                                           | Explanation                                                                 |
|---------------------------|-----------------------------------------------------------|-----------------------------------------------------------------------------|
| **Spoofed Source IP**      | `sudo nmap -S FAKE_IP IP_target`                         | Spoofs the source IP — needs non-response IP and careful routing.          |
| **Spoofed MAC Address**    | `--spoof-mac 00:11:22:33:44:55`                          | Fakes source MAC address — useful against MAC-filtered networks.           |
| **Decoy Scan**             | `nmap -D RND,RND,YOUR_IP IP_target`                     | Uses fake IPs to mask the origin of the scan.                              |
| **Idle Scan (Zombie Scan)**| `sudo nmap -sI ZOMBIE_IP IP_target`                      | Fully stealth scan using third-party idle zombie host.                     |
| **Fragment IP Packets (8B)**| `nmap -f IP_target`                                     | Splits packets to evade deep-packet inspection or intrusion detection.     |
| **More Fragmentation (16B)**| `nmap -ff IP_target`                                    | Sends even more granular fragments for evasion.                            |
| **Set Custom Source Port** | `nmap --source-port 53 IP_target`                        | Uses specific source port (like 53) to potentially bypass firewall rules.  |
| **Append Random Payload**  | `nmap --data-length 100 IP_target`                       | Adds random bytes to packets to obfuscate signatures.                      |

---

## 🛠️ Detection & Analysis

| Option                    | Example Command               | Explanation                                                                 |
|--------------------------|-------------------------------|-----------------------------------------------------------------------------|
| **Show Scan Reason**     | `--reason`                    | Shows why each port was marked open/closed (e.g., based on TTL/RST).       |
| **OS Detection**         | `nmap -O IP_target`           | Attempts OS fingerprinting (requires root privilege).                       |
| **Service Detection**    | `nmap -sV IP_target`          | Detects software service name and version info.                            |
| **Aggressive Scan**      | `nmap -A IP_target`           | Enables OS detection, version detection, traceroute, and NSE scripts.      |
| **Fast Scan**            | `nmap -F IP_target`           | Scan top 100 most common ports — faster scan.                              |
| **Scan All Ports**       | `nmap -p- IP_target`          | Scan all 65,535 TCP ports.                                                 |
| **Scan Specific Ports**  | `nmap -p 22,80,443 IP_target` | Only scan specified ports.                                                 |

---

## 📂 Target Handling

| Option                       | Example Command                    | Explanation                                                                 |
|-----------------------------|------------------------------------|-----------------------------------------------------------------------------|
| **Read Targets from File**  | `nmap -iL targets.txt`             | Loads target list from file.                                                |
| **Exclude Targets**         | `nmap --exclude IP1,IP2`           | Skip scanning specified IP addresses.                                      |
| **Disable Host Discovery**  | `nmap -Pn IP_target`               | Assume hosts are up — scan without pinging first.                          |

---

## 🗣️ Verbose and Output

| Option           | Example               | Explanation                                                  |
|------------------|-----------------------|--------------------------------------------------------------|
| **Verbose**       | `-v`                 | Show more scan info and results.                            |
| **Very Verbose**  | `-vv`                | Even more detailed than `-v`.                               |
| **Debug Mode**    | `-d`                 | Adds debug output.                                           |
| **Extra Debug**   | `-dd`                | Shows advanced debug information (packet details).          |

---

> ⚠️ **Important:**  
> Most advanced flags require **root (sudo)** privileges.  
> Always ensure you have **permission** to scan any network — unauthorized scanning may be **illegal** or **malicious** depending on context.  

---

## 📚 References

- [https://nmap.org/book/](https://nmap.org/book/)
- [https://nmap.org/man/](https://nmap.org/man/)

