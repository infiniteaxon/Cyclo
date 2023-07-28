**Overview:** 

These types of port scan can bypass many stateless firewalls, but should fail when attempting to pass a stateful firewall.

|Port Scan Type|Example Command|
|---|---|
|TCP Null Scan|`sudo nmap -sN [IP]`|
|TCP FIN Scan|`sudo nmap -sF [IP]`|
|TCP Xmas Scan (FIN, PSH, URG)|`sudo nmap -sX [IP]`|
|TCP Maimon Scan|`sudo nmap -sM [IP]`|
|TCP ACK Scan|`sudo nmap -sA [IP]`|
|TCP Window Scan|`sudo nmap -sW [IP]`|
|Custom TCP Scan|`sudo nmap --scanflags URGACKPSHRSTSYNFIN MACHINE_IP`|
|Spoofed Source IP|`sudo nmap -S SPOOFED_IP MACHINE_IP`|
|Spoofed MAC Address|`--spoof-mac SPOOFED_MAC`|
|Decoy Scan|`nmap -D DECOY_IP, ME, MACHINE_IP`|
|Idle (Zombie) Scan|`sudo nmap -sI ZOMBIE_IP MACHINE_IP`|
|Fragment IP data into 8 bytes|`-f`|
|Fragment IP data into 16 bytes|`-ff`|


These scan types rely on setting TCP flags in unexpected ways to prompt ports for a reply. Null, FIN, and Xmas scan provoke a response from closed ports, while Maimon, ACK, and Window scans provoke a response from open and closed ports.

|Option|Purpose|
|---|---|
|`--reason`|explains how Nmap made its conclusion|
|`-v`|verbose|
|`-vv`|very verbose|
|`-d`|debugging|
|`-dd`|more details for debugging|
|`-Pn` |Tells nmap not to expect a ping|
|`-e interface`|Sets interface nmap will utilize|
|`--reason`| Provides reasoning and conclusions|
|`--source-port PORT_NUM`|specify source port number|
|`--data-length NUM`|append random data to reach given length|



**Specific Attacks:**

|Port Scan Type||
|---|---|
|TCP Null Scan| Can be used to find what ports are not closed.|
|TCP FIN Scan| Can be used to find what ports are not closed, but firewalls may 'silently' drop the RST packet.|
|TCP Xmas Scan| Utilizes FIN, PSH, and URG flags and can be used to find what ports are not closed. |
|TCP Maimon Scan| Utilizes FIN and ACK flags which sometimes expose open ports. |
|TCP ACK Scan| Sends an unprompted ACK packet, this type of scan is more suitable to discover firewall rule sets and configuration.|
|TCP Window Scan| Used to detect whether a firewall protects a port, similar to ACK scan but shows opposite results.|
|Custom TCP Scan| Can be utilized to customize what flags are set on a packet.|


**Useful Commands**

|Options||
|---|---|
|Spoofed Source IP| Used to spoof source IP Address which is only useful on same network - Common to use -Pn to not expect a ping, and -e to set network interface. |
|Spoofed MAC Address| Used to spoof course MAC Address on same subnet.|
|Decoy Scan|Used to send a packet from multiple sources so some act as Decoys for the real source.|
|Idle (Zombie) Scan| First, trigger the idle host to respond so that you can record the current IP ID on the idle host. Second, send a SYN packet to a TCP port on the target. The packet should be spoofed to appear as if it was coming from the idle host (zombie) IP address. Lastly, trigger the idle machine again to respond so that you can compare the new IP ID with the one received earlier. An increase of 0 or 1 is closed, 2 is open. |
|Fragment IP data into 8, 16, 24, 32 bytes| Breaks packets up into certain byte sizes |