Say you had a data source with 2,000 events. This source had the fields as listed below:

- host
- domain
- usr
- type (fail/lock, etc)

If you wanted to draw a useful picture using SPL, you could use the following command:

```
host=hostname domain=* usr=* type=fail OR lock | table _time usr domain type
```

For a better looking table, you could pipe this once again but change the variable names using AS commands.