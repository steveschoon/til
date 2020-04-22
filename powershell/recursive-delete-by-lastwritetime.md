# Recursive Delete By LastWriteTime

- Delete all files
- in current directory and subdirectories
- older than 3 days
- with no confirmation prompts

```
Get-ChildItem –Path "." -Recurse | Where-Object {($_.LastWriteTime -lt (Get-Date).AddDays(-3))} | Remove-Item -Recurse -Confirm:$false -Force
```
This is nice because it handles subdirectories and doesn't leave empty subdirectories behind.

> If you're not sure what will get deleted

To see what would be deleted but not delete it, add `-WhatIf` at the end

