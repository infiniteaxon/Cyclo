Armitage is essentially just a GUI for Metasploit. After installation, and confirmation that Metasploit is also installed, you're ready to start using Armitage. There are two sides of this program you should be aware of:

1: Teamserver
    Takes an IP address and Password

2: Armitage
    This is the code that allows you to interact with the Teamserver

Prepare the Enviornment:

```
systemctl start postgresql && systemctl status postgresql
```

```
msfdb --use-defaults delete

msfdb --use-defaults init
```
(^do not use root for this^)

Start Armitage:

```
cd /opt/armitage/release/unix && ./teamserver [IP] [Password]
```
```
cd /opt/armitage/release/unix && ./armitage
```
