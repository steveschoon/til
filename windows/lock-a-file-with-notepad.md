# Lock A File With Notepad

Today I was trying to code a check for being able to exclusively access a file before writing to it.  Basically using `FileStream.Lock` before trying to write to the file.  That code was easy enough, but what I had to Google for was now to lock the file in the first place.  These things didn't lock the file:

- Edit with Notepad
- Edit with gVim

But this works from a simple non-elevated command prompt:

```
notepad >> file-i-want-to-lock.txt
```

