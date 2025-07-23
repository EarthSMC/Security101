### Nmap command

| Port Scan Type         | Example Command           |
| :---------------       | :----------------:        |
| TCP Null Scan          | sudo nmap -sN <IP target> |
| TCP FIN Scan           | sudo nmap -sF <IP target> |
| TCP Xmas Scan          | sudo nmap -sX <IP target> |
| TCP Maimon Scan        | sudo nmap -sM <IP target> |
| TCP ACK Scan           | sudo nmap -sA <IP target> |
| TCP Window Scan        | sudo nmap -sW <IP target> |
| Custom TCP Scan        | sudo nmap --scanflags URGACKPSHRSTSYNFIN IP target |
| Spoofed Source IP      | sudo nmap -S SPOOFED_IP IP target |
| Spoofed MAC Address    | --spoof-mac SPOOFED_MAC |
| Decoy Scan    | nmap -D DECOY_IP,ME IP target  |
| Idle (Zombie) Scan    | sudo nmap -sI ZOMBIE_IP IP target |
| Fragment IP data into 8 bytes    | -f |
| Fragment IP data into 16 bytes    | -ff |
| --source-port PORT_NUM    | 	specify source port number |
| --data-length NUM    | -ff |
| --reason    | append random data to reach given length |
| -v    | verbose |
| -vv    | very verbose |
| -d    | debugging |
| -dd    | more details for debugging |

___https://tryhackme.com/room/nmap03___
