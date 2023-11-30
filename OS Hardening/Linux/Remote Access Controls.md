#### Disable RA as Root
- Navigate to /etc/ssh/sshd_config
	- add line `PermitRootLogin no`

#### Use PKI for SSH
- Generate ssh key
	- `ssh-keygen -t rsa`
- Copy pub key to server
	- `ssh-copy-id username@server`
- Check `sshd_config` for if PKI enabled
	- `PubkeyAuthentication yes`
	- `PasswordAuthentication no`
