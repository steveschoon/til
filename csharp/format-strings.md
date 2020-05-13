# Format Strings

### DateTime

|Format String|Output|Comments|
|-------------|-------|--------|
|`yyyyMMdd-HHmmss`|`20200505-211459`|Good for filenames that should be sortable.  Note `HH` means military time|
|`yyyyMMdd-HHmmss-fff`|`20200505-211722-169`|`fff` adds milliseconds for sub-second resolution|
|`u`|`2020-05-05 21:19:17Z`|Easier to read but doesn't work for filenames|
|`o`|`2020-05-13T16:27:56.1362818-04:00`|Includes time zone info|
