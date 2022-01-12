# Escape Special Chars

Today I was trying to stop and start a MSSQL named instance from the command line.  My first try was:

`net stop mssql$sql17`

But that didn't work.  And I could see that the `$` char highlighted in a different color.  

Here's what worked

``net stop mssql`$sql17``
