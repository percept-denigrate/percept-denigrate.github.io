DNS (domain name system) in a protocol for resolving domain names and obtaining corresponding IP addresses.

DNS is implemented over [[UDP]] (port 53) by default. But there are implementations over [[TLS]] and [[HTTP|HTTPS]]

When a client wants to resolve a domain name, he makes a recursive request to a resolution server. This server makes iterative requests for each domain level. For instance, a query to `www.wikipedia.org` is first sent to the DNS resolver. The resolver asks the root server for the TLD server for `org`. The resolver queries this TLD server, which then redirects the resolver to the SLD server for `wikipedia`, which then redirects to the server for `www`.

![[dns.png]]

DNS servers use caches where they store DNS query results with a timestamp.

# DNS cache poisoning

DNS cache poisoning is an attack on DNS servers. 

- The client queries the DNS resolver.
- The resolver asks authoritative servers for the associated IP.
- The attacker sends a forged DNS reply to the resolver, by guessing the transaction ID or flooding.
- If the forged reply is accepted, the fake record is cached.
- All users querying the domain name will be redirected to the attacker-controlled IP.

# DNSsec

DNSsec adds cryptographic signatures to DNS records. This allows resolvers to verify responses are authentic and unmodified. It adds authenticity and integrity but not encryption.

Validation starts at the root server, and continues downwards to other levels.
