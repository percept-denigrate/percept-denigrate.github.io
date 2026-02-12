DNS (domain name system) in a protocol for resolving domain names and obtaining corresponding IP addresses.

When a client wants to resolve a domain name, he makes a recursive request to a resolution server. This server makes iterative requests for each domain level. For instance, a query to `www.wikipedia.org` is first sent to the DNS resolver. The resolver asks the root server for the TLD server for `org`. The resolver queries this TLD server, which then redirects the resolver to the SLD server for `wikipedia`, which then redirects to the server for `www`.

![[dns.png]]

DNS servers use caches where they store DNS query results with a timestamp.

DNS is vulnerable to [[DNS cache poisoning]] if it does not use [[DNSsec]].