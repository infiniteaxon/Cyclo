- TCP Dump
Sniffing attack refers to using a network packet capture tool to collect information about the target. When a protocol communicates in cleartext, the data exchanged can be captured by a third party to analyse. A simple network packet capture can reveal information, such as the content of private messages and login credentials, if the data isn't encrypted in transit.

|Operator| |
|---|---|
|-A| ASCII Mode|

```
sudo tcpdump port 110 -A
```


- Wireshark
Can be used to search protocols in the search bar.

```
imap
```