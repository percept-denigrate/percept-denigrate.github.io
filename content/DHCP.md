DHCP (dynamic host configuration protocol) is protocol designed to attribute an [[IP]] address to machines connecting to a local network.

It runs over [[UDP]] (client on port 68, server on 67) at works even when the client has no IP address.

- Discover: the client sends a request to the DHCP server
- Offer: the server sends an available IP address and options
- Request: the client asks to use that IP
- ACK: the server confirms and leases the address

The two first steps are sent to broadcast.

Clients trust the first DHCP offer they receive, and there is no authentication by default. This can lead to rogue DHCP servers: an attacker runs an unauthroized DHCP server on the network, and  It can send the wrong gateway or [[DNS]] to clients, do [[MitM]], or redirect clients to malicous sites.

It can be mitigated by DHCP snooping: a layer 2 security feature that makes the switch inspect DHCP messages, control which ports can send DHCP responses, and build an IP-MAP-port table.

