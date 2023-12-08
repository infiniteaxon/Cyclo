

**Volatility** is a terminal based tool, but has a variant known as Volatility Workbench with a GUI.
 - Refresh Process List - Generate Current Processes
 - Many 'commands' to be run
	 - `windows.malfind.Malfind` will search for evidence of process injection, malware behavior, etc
	 - `pslist` - Outputs list of all running processes during capture
	 - `psscan` - pslist but with more detail, may show 'hidden' processes
	 - `pstree` - parent/child process relations
	 - `procdump` - retrieve a process file for analysis
	 - `memdump` - retrieve a memory snapshot from a process
	 - `dumpfiles` - dump all cached files
	 - `modscan` - show drivers, hidden, disabled, etc
	 - `netscan` - show listening/established connections
	 - `imagecopy` - copy memdump
	 - `timeliner` - log a timeline of events
	 - `cmdscan`
	 - `consoles`

Important to Find what OS the Dump is from:
- `volatility -f {MEM_FILENAME} imageinfo`
- `volatility -f {MEM_FILENAME} --profile={PROFILE}`
	- {MEM_FILENAME} - memdump.mem
	- {PROFILE} - Win10x64_14393

Dump a process file
- `volatility -f {MEM_FILENAME} --profile={PROFILE} procdump -p {PID} --dump-dir={intended directory}`
- Could take this and run further analysis

Dump a process' memory
- `volatility -f {MEM_FILENAME} --profile={PROFILE} memdump -p {PID} --dump-dir={intended directory}`
- Could take this and run further analysis

Find a communication link with external server
- Open CMD in vol.exe directory.
- `vol.exe -f {MEM_FILENAME} {COMMAND}`
	- {COMMAND} - `windows.netstat` , `netscan`
- Find odd looking connections

Tips:
- `svchost.exe` should always have parent process `services.exe`