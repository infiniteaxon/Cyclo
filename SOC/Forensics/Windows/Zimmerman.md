(All in EZTools)
### Use PEC for Prefetch files parsing

Prefetch files contain the last run times of the application, the number of times the application was run, and any files and device handles used by the file.

Location
- `C:\Windows\Prefetch`

File
- `PECmd.exe -f <path-to-Prefetch-files> --csv <path-to-save-csv>`

Directory
- `PECmd.exe -d <path-to-Prefetch-directory> --csv <path-to-save-csv>`


### WxTC for Timelining

Contains the application that was executed and the focus time of the application

Location of Timeline 
- ``C:\Users\<username>\AppData\Local\ConnectedDevicesPlatform\{randomfolder}\ActivitiesCache.db``

Use the Tool
- `WxTCmd.exe -f <path-to-timeline-file> --csv <path-to-save-csv>`


### JLECmd.exe for Windows Jump Lists

Jumplists include information about the applications executed, first time of execution, and last time of execution of the application against an AppID.


Location of Jumplist
- `C:\Users\<username>\AppData\Roaming\Microsoft\Windows\Recent\AutomaticDestinations`

Use the Tool
- `JLECmd.exe -f <path-to-Jumplist-file> --csv <path-to-save-csv>`


### LECmd.exe by for Shortcut Files / Search History

The shortcut files contain information about the first and last opened times of the file and the path of the opened file, along with some other data.

Location
- `C:\Users\<username>\AppData\Roaming\Microsoft\Windows\Recent\`
- ``C:\Users\<username>\AppData\Roaming\Microsoft\Office\Recent\``

Use the Tool
- `LECmd.exe -f <path-to-shortcut-files> --csv <path-to-save-csv>`
	
	IE/Edge History

	Includes files opened in the system as well, whether those files were opened using the browser or not.

	Location
	- ``C:\Users\<username>\AppData\Local\Microsoft\Windows\WebCache\WebCacheV*.dat``
	
	Analyze with Autopsy