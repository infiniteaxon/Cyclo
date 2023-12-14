- On a Linux system, a solution such as [SELinux](https://github.com/SELinuxProject) or [AppArmor](https://www.apparmor.net/) can be used for more granular control over processes and their network access. For example, we can allow only the `/usr/bin/apache2` binary to use ports 80 and 443 while preventing any other binary from doing so on the underlying system. Both tools enforce access control policies based on the specific process or binary, providing a more comprehensive way to secure a Linux system.

### iptables
- Default Chains
	- Input
	- Output
	- Forward

#### Check iptables rules
`sudo iptables -L`

#### Create a basic ruleset
`sudo iptables -A INPUT -m conntrack --ctstate ESTABLISHED,RELATED -j ACCEPT`

-A # places rule at end of specified chain {INPUT}
-m # calls in an iptables module {conntrack}
--ctstate # looks for {ESTABLISHED} connection from user then allows {RELATED} packets to come back into the network to user
-j # {ACCEPT} user requested server

#### Allow SSH Connections
`sudo iptables -A input -p tcp --dport ssh -j ACCEPT`

-p # specify packets from {TCP} protocol
--dport # destination port {ssh}

#### Drop Everything Else (put at end of chain. or risk dropping unintended packets)
`sudo iptables -A INPUT -j DROP`

#### Insert loopback rule at start of chain
`sudo iptables -I INPUT 1 -i lo -j ACCEPT`

#### iptables persistence
`sudo apt install iptables-persistent`
