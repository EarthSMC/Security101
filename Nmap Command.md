### Nmap command

| Port Scan Type         | Example Command           |
| :---------------       | :----------------:        |
| TCP Null Scan          | sudo nmap -sN IP_target |
| TCP FIN Scan           | sudo nmap -sF IP_target |
| TCP Xmas Scan          | sudo nmap -sX IP_target |
| TCP Maimon Scan        | sudo nmap -sM IP_target |
| TCP ACK Scan           | sudo nmap -sA IP_target |
| TCP Window Scan        | sudo nmap -sW IP_target |
| Custom TCP Scan        | sudo nmap --scanflags URGACKPSHRSTSYNFIN IP_target |
| Spoofed Source IP      | sudo nmap -S SPOOFED_IP IP_target |
| Spoofed MAC Address    | --spoof-mac SPOOFED_MAC |
| Decoy Scan    | nmap -D DECOY_IP,ME IP_target  |
| Idle (Zombie) Scan    | sudo nmap -sI ZOMBIE_IP IP_target |
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
