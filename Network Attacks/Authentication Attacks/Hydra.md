|**Operators:**||
|---|---|
|`-l username`| `-l` should precede the `username`, i.e. the login name of the target.|
|`-P wordlist.txt`:| `-P` precedes the `wordlist.txt` file, which is a text file containing the list of passwords you want to try with the provided username.|
|`server`| is the hostname or IP address of the target server.|
|`service`| indicates the service which you are trying to launch the dictionary attack.|
|`-s port`| specify a non-default port for the service in question.|
|`-V` or `-vV`| verbose|
|`-t n`| where n is the number of parallel connections to the target. `-t 16` will create 16 threads used to connect to the target.|
|`-d`|debugging|



```
hydra -l username -P wordlist.txt -f server service
```

```
hydra -L users.txt -P wordlist.txt -vV ftp://[MACHINE_IP]:PORT
```