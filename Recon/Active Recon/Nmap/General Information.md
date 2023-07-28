1. **Save Scans:**

|Operator|Explanation|
|---|---|
|`-oN [filename]`|Saves scan in normal format|
|`-oG {filename}`|Saves scan in grep(able) format|
|`-oX {filename}`|Saves scan in XML format|
|`-oS {filename}`|Saves scan in Script Kiddie format|
|`-oA {filename}`|Saves scan in normal, grep, and script kiddie formats|


`scp pentester@10.10.50.191:/home/pentester/* . | cat scan_172_17_network.gnmap | grep 443`


