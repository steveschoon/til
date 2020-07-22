# Query For Server Ip Address

Needed to send a list of all SmartGrocer sql server ip addrsses today. `local_net_address` is what I needed, and the other stuff was helpful too.

```
select 
	@@VERSION as server_ver
	,@@SERVERNAME as server_name
	,@@SERVICENAME as svc_name
	,CONNECTIONPROPERTY('net_transport') AS net_transport
	,CONNECTIONPROPERTY('protocol_type') AS protocol_type
	,CONNECTIONPROPERTY('auth_scheme') AS auth_scheme
	,CONNECTIONPROPERTY('local_tcp_port') AS local_tcp_port
	,CONNECTIONPROPERTY('local_net_address') AS local_net_address
	,CONNECTIONPROPERTY('client_net_address') AS client_net_address
```
