Link: https://www.freecodecamp.org/news/gobuster-tutorial-find-hidden-directories-sub-domains-and-s3-buckets/


**Operators**:

```
Mode: dir, dns, s3 
Target: -u, -d, s3 ... [domain, ip:port] 
Wordlist: path to wordlist (e.g. /usr/share/wordlists/dirb/common.txt) 
Type: -x [pdf, jpeg, png] 
```


**Setup:** 

```
gobuster [mode] -? [target] -w [wordlist] -x [extension type] 
```


**Example:** 

```
gobuster dir -u axonia.co -w /usr/share/wordlists/dirb/common.txt -x pdf,png,jpeg
```


**Target Area Specific Examples**

- Directory:

```
gobuster dir -u [dns/ip:port] -w /usr/share/wordlists/dirb/common.txt -x [type: png, jpeg, pdf] 
```


- Subdomain: 

```
gobuster dns -d [dns/ip:port] -w /usr/share/wordlists/dirb/common.txt 
```


- S3 Bucket: 

```
gobuster s3 -w bucket_list.txt 
```
