# Count Lines In File

The does the same thing as Linux `wc -l file.txt`

```
Get-Content -Path .\file.txt | Measure-Object -Line
```

This one-liner is faster:

```
$count=0; switch -File .\file.txt { default { ++$count}};$count
```
