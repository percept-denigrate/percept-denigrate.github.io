ARP spoofing is a [[MitM]] attack on [[ARP]].

The attacker responds to the broadcast request asking for the MAC address of another machine (typically the gateway), and responds with his own. The malicious MAC address is added to the victim's ARP cache. The attacker can then intercept the victim's trafic.

![](https://upload.wikimedia.org/wikipedia/commons/3/33/ARP_Spoofing.svg)

This can be prevented by certification of ARP responses.