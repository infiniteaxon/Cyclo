1. **Enumerating Targets:**

```
nmap -sL {IPs/Domains}
nmap -iL [path to file]
```


2. **Live Host Discovery:**

|**Relevant Operators:**||
|---|---|
|-n | no DNS lookup |
| -R | reverse-DNS lookup for all hosts |
| -sn | host discovery only (no port scan) |
| --dns-servers | DNS_SERVER |

- ARP

```
nmap -sn {IPs} (Discover hosts w/o port scan)
nmap -PR -sn {IP}/24 (ARP scan all subdomain systems w/o port scan)
```

- ICMP (Blocked by Windows Firewall by Default):

```
nmap -PE -sn {IP}/24 (ICMP Echo to all systems)
nmap -PP -sn {IP}/24 (Timestamp Request to all systems)
nmap -PM -sn {IP}/24 (Address Mark Request to all systems)
```

- TCP/UDP Ping:

```
sudo nmap -PS[Port1,Port2,Port3] -sn {IP}/30 (TCP SYN Ping Scan)
sudo nmap -PA[Port1,Port2,Port3] -sn {IP}/30 (TCP ACK Ping Scan)
sudo nmap -PU[Port1,Port2,Port3] -sn {IP}/30 (UDP Ping Scan)
```
