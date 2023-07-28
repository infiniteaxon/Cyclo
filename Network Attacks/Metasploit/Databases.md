Metasploit has a database function to simplify project management and avoid possible confusion when setting up parameter values. 


Start the PostgreSQL database which Metasploit will use with the following commands: 

```
systemctl start postgresql
```
  
```
msfdb init
```

```
db_status
```

```
workspace -a/-d name [add/delete]
```

**Scan and Save into Database:**

```
db_nmap -sV IP
```

**Search results with:**

```
hosts
```

```
services
```
