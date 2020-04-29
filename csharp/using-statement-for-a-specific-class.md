# Using Statement for a Specific Class

Today I had a Xamarin project where I was using ServiceStack.  `using ServiceStack;` pulls in some extensions methods that I was using (`Exception.IsAny400,500`) and those methods weren't available any other way. 

Unfortunately ServiceStack also has a `Command` that conflicts with `Xamarin.Forms.Command`. 

`using ServiceStack;` was necessary for the extension methods, so this additional using statement:

```
using Command = Xamarin.Forms.Command;
```
Allowed me to write code like this:

```
public Command SomeCommand => new Command(() =>
{
	// whatever...
});
```

Without specifically writing `Xamarin.Forms.Command` which was bumming me out.
