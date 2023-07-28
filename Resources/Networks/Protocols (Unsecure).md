**Overview:**

|Protocol|TCP Port|Application(s)|Data Security|
|---|---|---|---| 
|FTP|21|File Transfer|Cleartext| 
|HTTP|80|Worldwide Web|Cleartext| 
|IMAP|143|Email (MDA)|Cleartext| 
|POP3|110|Email (MDA)|Cleartext| 
|SMTP|25|Email (MTA)|Cleartext| 
|Telnet|23|Remote Access|Cleartext|

|Protocol|Default Port|Secured Protocol|Default Port with TLS|
|---|---|---|---|
|HTTP|80|HTTPS|443|
|FTP|21|FTPS|990|
|SMTP|25|SMTPS|465|
|POP3|110|POP3S|995|
|IMAP|143|IMAPS|993|


**Telnet:**
The Telnet protocol is an application layer protocol used to connect to a virtual terminal of another computer. Using Telnet, a user can log into another computer and access its terminal (console) to run programs, start batch processes, and perform system administration tasks remotely.


```
 telnet IP 
```


**HTTP:**
Hypertext Transfer Protocol Hypertext Transfer Protocol (HTTP) is the protocol used to transfer web pages. Your web browser connects to the webserver and uses HTTP to request HTML pages and images among other files and submit forms and upload various files. Anytime you browse the World Wide Web (WWW), you are certainly using the HTTP protocol.

```
 telnet IP 80 
```

```
 GET /page.ext HTTP/1.1
host: telnet 
```


**FTP:**
File Transfer Protocol File Transfer Protocol (FTP) was developed to make the transfer of files between different computers with different systems efficient. FTP also sends and receives data as cleartext; therefore, we can use Telnet (or Netcat) to communicate with an FTP server and act as an FTP client. Operators

```
STAT - additional information
SYST - system information
PASV - passive mode
ascii - TYPE A, ASCII transfer mode
binary - TYPE I, Binary transfer mode
```

```
 ftp IP 21 
```


**SMTP:**
Simple Mail Transfer Protocol A Mail User Agent (MUA), or simply an email client, has an email message to be sent. The MUA connects to a Mail Submission Agent (MSA) to send its message. The MSA receives the message, checks for any errors before transferring it to the Mail Transfer Agent (MTA) server, commonly hosted on the same server. The MTA will send the email message to the MTA of the recipient. The MTA can also function as a Mail Submission Agent (MSA). A typical setup would have the MTA server also functioning as a Mail Delivery Agent (MDA). The recipient will collect its email from the MDA using their email client.

```
telnet IP 25
```


**POP3:**
Post Office Protocol 3 Post Office Protocol version 3 (POP3) is a protocol used to download the email messages from a Mail Delivery Agent (MDA) server, as shown in the figure below. The mail client connects to the POP3 server, authenticates, downloads the new email messages before (optionally) deleting them. Operators

```
USER user
PASS pass
STAT - Status of mailbox "+OK  nn mm" nn is mesage quantity, mm is storage size
LIST - List avaliable mail
RETR 1 - retrieves first message in mailbox
```

```
telnet IP 110
```


**IMAP:**
Internet Message Access Protocol Internet Message Access Protocol (IMAP) is more sophisticated than POP3. IMAP makes it possible to keep your email synchronized across multiple devices (and mail clients). In other words, if you mark an email message as read when checking your email on your smartphone, the change will be saved on the IMAP server (MDA) and replicated on your laptop when you synchronize your inbox. Operators

```
c1, c2, c3 - all commands need preceding by string
c1 LOGIN username password
c2 LIST "" "+" - lists mail folders
c3 EXAMINE INBOX - checks for mail
```

```
telnet IP 143
```


