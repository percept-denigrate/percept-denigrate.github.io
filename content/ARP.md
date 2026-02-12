ARP (address resolution protocol) is a layer 2 protocol to resolve MAC addresses in a local network and associate them with an [[IP]] address.

- A device broadcasts a request to ask "who has IP X?"
- The owner responds his MAC address in unicast
- The sender saves the association in his ARP cache

The protocol is stateless. Devices trust replies, even if they didn't ask. This can lead to [[ARP cache poisoning]].