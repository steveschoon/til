# Increase Max Upload Size

This morning a C# program on ServerA was trying to send a 7MB file to ServerB via an ASMX web service.  It was failing with error `There was an exception running the extensions specified in the config file. ---> Maximum request length exceeded.`  

The problem is that IIS 7 (Server 2008) and IIS 8 (Server 2012) by default are limited to a 4MB max request size.  (https://docs.microsoft.com/en-us/dotnet/api/system.web.configuration.httpruntimesection.maxrequestlength?redirectedfrom=MSDN&view=netframework-4.8)

To fix this, 2 changes had to be made to the `web.config` in this applications private web.config:

Under `system.web`

```
<httpRuntime maxRequestLength="1048576" executionTimeout="3600" />
```

Under `system.webServer`

```
<security>
    <requestFiltering>
        <requestLimits maxAllowedContentLength="1073741824" />
    </requestFiltering>
</security>
```

### NOTE
`maxRequestLength` under  `system.web` is expressed in megabytes, and `maxAllowedContentLength` under `system.webServer` is expressed in bytes.  The values should match when converted to megabytes, in this case 1,024.

