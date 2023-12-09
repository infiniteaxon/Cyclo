
#### Basic Info Locations
- OS Release
	- `/etc/os-release`
- User Accounts
	- `/etc/passwd`
		- For readability pipe to `column -t -s :`
- Group Information
	- `/etc/group`
- Sudoers List
	- `/etc/sudoers`


#### Logs
- Login Information
	- `last -f /var/log/wtmp`
- Authentication
	- `/var/log/auth.log`
		- Pipe to `tail`
