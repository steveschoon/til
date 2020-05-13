# Write To Config Files

Today I needed to look into config files (whatever.exe.config) and check for SQL Server connect strings that had unencrypted password, encrypt the passwords, and save the changes back to disk.  Turne dout to be easy:

```
// open the config file for manipulation
var a = Assembly.GetEntryAssembly();
var config = ConfigurationManager.OpenExeConfiguration(a.Location);

// change a value
config.AppSettings.Settings["foo"].Value = "bar";

// add a new key/value pair
config.AppSettings.Settings.Add($"newKey", "newValue");

// remove a key
config.AppSettings.Settings.Remove("byebye");

// save
config.Save(ConfigurationSaveMode.Minimal);

// make changes availble without a restart
ConfigurationManager.RefreshSection("appSettings");
```
