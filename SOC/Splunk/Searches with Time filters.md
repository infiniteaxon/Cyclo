Time can tell a lot in a story, so it's important you can display it correctly.

|Time Variable|Description|
|---|---|
|%H|Hour (24hr)|
|%I|Hour (12hr)|
|%M|Minute|
|%S|Second|
|%p|AM/PM|

Use the following command:

```
cmd | eval time=strftime(_time, "%H:%M")
```

More Time Variables:

|Time Variable|Description|
|---|---|
|%A| Full Day Name|
|%d|Day of Month (01 - 31)|
|%e|Day of Month w/o 0 (1 - 31)|
|%B|Full Month (January)|
|%b|Abbr Month (Jan)|
|%m|Months as numbers (01 - 12)|
|%Y|Four Digit Year (2023)|
|%y|Two Digit Year (23)|