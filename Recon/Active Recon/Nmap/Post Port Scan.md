**Overview:** 

Use these options to identify routes packets take, what systems exist, and sometimes even what applications are running!

**Operators:**

|Option|Meaning|
|---|---|
|`-sV`|determine service/version info on open ports|
|`-sV --version-light`|try the most likely probes (2)|
|`-sV --version-all`|try all available probes (9)|
|`-O`|detect OS|
|`--traceroute`|run traceroute to target|
|`--script=SCRIPTS`|Nmap scripts to run|
|`-sC` or `--script=default`|run default scripts|
|`-A`|equivalent to `-sV -O -sC --traceroute`|


**Service Detection:**

```
nmap -sV --version-intensity [level] 10.10.103.134
```


**OS Detection:**

- Not always absolute

```
nmap -sS -O 10.10.103.134
```


**Traceroute:**

```
nmap -sS --traceroute 10.10.103.134
```
