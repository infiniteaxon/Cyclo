
| **Relevant Operators:** |
|---|---|
| -F | Fast Mode: Scans 100 common ports instead of 1000 |
| -r | Consecutive: Scans ports in consecutive order instead of random |
| -v | Verbose: Shows more information |
| -p1,2,3 or -p1-3| Specify Ports: This will scan ports 1, 2, and 3 |
| -p- | Scan all (65535) ports |
| -T<0-5> | Will change timing, speed. In order, Paranoid, Sneaky, Polite, Normal, Aggressive, Insane |
| --min-rate 10 | Control minimum packet rate |
| --max-rate 100 | Control maximum packet rate |
| --min-parallelism 64 | Controls minimum number of probes to be ran in parallel |
| --max-parallelism 512 | Controls maximum number of probes to be ran in parallel |


- TCP Connect Scan: 
	(SYN, SYN/ACK, ACK)
	Available to non root/sudo users
	Connection will be briefly established, then reset.
	
```
nmap -sT [IP]
```

- TCP SYN Scan:
	(SYN, SYN/ACK, RST)
	Need root/sudo
	No connection will be established.
	
```
nmap -sS [IP]
```

- UDP Scan:
	(UDP, ICMP [Type 3, Code 3])
	Need root/sudo
	UDP scan will not show a port is open, only if it is closed.
	No connection will be established.
	
```
nmap -sU [IP]
```