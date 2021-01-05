# Count Lines In File

The does the same thing as Linux `wc -l file.txt`

```
Get-Content -Path .\file.txt | Measure-Object -Line
```
