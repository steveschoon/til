### VS2008 Compact Framework Project Does Not Open After Windows Upgrades

Sometimes after installing a Windows upgrade or feature update, opening a Compact Framework project with VS2008 fails with an error message like this:

> C:\gitlab-runner\builds\6d799bcb\0\ctsoft\sharp2\src\hh\Sharp2-99ex\Sharp-99ex.csproj(1204,11): The imported project "C:\Windows\Microsoft.NET\Framework\v3.5\Microsoft.CompactFramework.CSharp.targets" was not found. Confirm that the path in the <Import> declaration is correct, and that the file exists on disk.
Unable to read the project file 'Sharp.Core.csproj'. 

What probably happened was the a recent Windows update removed 2 files:

```
C:\Windows
    \Microsoft.Net
		\Framework
			\v3.5
				Microsoft.CompactFramework.Common.targets
				Microsoft.CompactFramework.CSharp.targets
```

Put those files back and everything should work.

- [Microsoft.CompactFramework.Common.targets](Microsoft.CompactFramework.Common.targets)
- [Microsoft.CompactFramework.CSharp.targets](Microsoft.CompactFramework.CSharp.targets)
