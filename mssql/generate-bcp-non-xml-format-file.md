# Generate BCP Non-XML Format File

```
bcp database..TableName format nul -c -f TableName.fmt -S server -Usa -Ppass;
```

Notes:
- Replace `\t` column delimiters with empty space for fixed width input files
- Pay attention to what version of BCP.EXE is executed because of system PATH, adjust the version # on the first line of the format file to be what you excpect
- Keep the blank line at the end
