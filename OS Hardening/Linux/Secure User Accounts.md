#### Add Users to sudo (or if named different) group
- usermod -aG sudo username
	- - `usermod` modifies a user acct
	- `-aG` appends to group
	- `sudo` group we're adding to (may be {wheel})
	- `username` user we're modifying

#### Disable root (or another account)
- Modify `/etc/passwd`
	- Change shell from `/bin/bash` to  `/sbin/nologin`

#### User accounts need strong passwords
- Could use `libpwquality`
	- `apt-get install libpam-pwquality`
- Config in
	- `/etc/security/pwquality.conf` - RedHat / Fedora
	- `/etc/pam.d/common-password` - Debian / Ubuntu
- Options

| Operator | Arg |
|---|---|
|`difok`|# of chars in new password not present in old password|
|`minlen`|min # of chars|
|`minclass`|min # of classes (lower, upper, digits, special)|
|`badwords`|list of words that cannot be used, separated by spaces|
|`retry`| N times user can attempt before throwing error|


	