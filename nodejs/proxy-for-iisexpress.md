# Proxy for IISExpress

IISExpress is nice for debugging web services with Visual Studio but listening for requests coming from outside machine IISExpress is running on is difficult to configure and/or not possible.  

This helps:  https://www.npmjs.com/package/iisexpress-proxy

For example, if IISExpress is hosting a web service at http://localhost:13131::

- `npx iisexpress-proxy 13131 to 81` runs it without installing
- `npm install -g iisexpress-proxy` to install and then just `iisexpress-proxy 13131 to 81`

Either of these listens for requests on port 81, and redirects them to the  IISExpress site listening on port 13131.   

