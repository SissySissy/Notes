# DNS
[https://www.cloudflare.com/learning/dns/what-is-dns/](https://www.cloudflare.com/learning/dns/what-is-dns/)

Domain Name System. 
You access information through domain names.
web browser interact through Internet Protocol IP addresses

DNS translates domain names to IP. so that browser can load the resources.


## process

the DNS resolution involves converting a hostname into an IP

there are 4 DNS involved:

**DNS recursor:** designed to receive queries from client machines, Typically the recursor is then responsible for making additional requests in order to satisfy the client’s DNS query
**Root nameserver:** the root serves translates queries into IP. typically it serves as a reference to other more specific locations
**TLD nameserver:** the top level domain. for example *.com* 
** authoritative nameserver** returns the right IP to the DNS recursor

It’s worth mentioning that in instances where the query is for a subdomain such as foo.example.com or [blog.cloudflare.com](https://blog.cloudflare.com/), an additional nameserver will be added to the sequence after the authoritative nameserver, which is responsible for storing the subdomain’s [CNAME record](https://www.cloudflare.com/learning/dns/dns-records/dns-cname-record/).

## caching

The purpose of caching is to temporarily stored data in a location that results in improvements in performance and reliability for data requests. DNS caching involves storing data closer to the requesting client so that the DNS query can be resolved earlier and additional queries further down the DNS lookup chain can be avoided, thereby improving load times and reducing bandwidth/CPU consumption. DNS data can be cached in a variety of locations, each of which will store DNS records for a set amount of time determined by a [time-to-live (TTL)]

Recursive DNS resolvers do not always need to make multiple requests in order to track down the records needed to respond to a client; [caching](https://www.cloudflare.com/learning/cdn/what-is-caching/) is a data persistence process that helps short-circuit the necessary requests by serving the requested resource record earlier in the DNS lookup.

#### Browser DNS caching

Modern web browsers are designed by default to cache DNS records for a set amount of time. the purpose here is obvious; the closer the DNS caching occurs to the web browser, the fewer processing steps must be taken in order to check the cache and make the correct requests to an IP address. When a request is made for a DNS record, the browser cache is the first location checked for the requested record.

In chrome, you can see the status of your DNS cache by going to chrome://net-internals/#dns.

#### Operating system (OS) level DNS caching

The operating system level DNS resolver is the second and last local stop before a DNS query leaves your machine. The process inside your operating system that is designed to handle this query is commonly called a “stub resolver” or DNS client. When a stub resolver gets a request from an application, it first checks its own cache to see if it has the record. If it does not, it then sends a DNS query (with a recursive flag set), outside the local network to a DNS recursive resolver inside the Internet service provider (ISP).

When the recursive resolver inside the ISP receives a DNS query, like all previous steps, it will also check to see if the requested host-to-IP-address translation is already stored inside its local persistence layer.

The recursive resolver also has additional functionality depending on the types of records it has in its cache:

1.  If the resolver does not have the  [A records](https://www.cloudflare.com/learning/dns/dns-records/dns-a-record/), but does have the  [NS records](https://www.cloudflare.com/learning/dns/dns-records/dns-ns-record/)  for the authoritative nameservers, it will query those name servers directly, bypassing several steps in the DNS query. This shortcut prevents lookups from the root and .com nameservers (in our search for example.com) and helps the resolution of the DNS query occur more quickly.
2.  If the resolver does not have the NS records, it will send a query to the TLD servers (.com in our case), skipping the root server.
3.  In the unlikely event that the resolver does not have records pointing to the TLD servers, it will then query the root servers. This event typically occurs after a DNS cache has been purged.

## What is a DNS A record?

The ‘A’ stands for ‘address’ and this is the most fundamental type of  [DNS](https://www.cloudflare.com/learning/dns/what-is-dns/?utm_referrer=https://www.cloudflare.com/learning/dns/what-is-dns/)  record, it indicates the  [IP address](https://www.cloudflare.com/learning/dns/glossary/what-is-my-ip-address/?utm_referrer=https://www.cloudflare.com/learning/dns/what-is-dns/)  of a given  [domain](https://www.cloudflare.com/learning/dns/glossary/what-is-a-domain-name/?utm_referrer=https://www.cloudflare.com/learning/dns/what-is-dns/). For example if you pull the DNS records of google.com, the ‘A’ record currently returns an IP address of: 172.217.5.78. ‘A’ records only hold Ipv4 addresses, if the site has a Ipv6 address, it will instead use an ‘AAAA’ record.

The ‘@’ here indicates that this is a record for the root domain, and the ‘14400’ value is the  [TTL (Time To Live)](https://www.cloudflare.com/learning/cdn/glossary/time-to-live-ttl/?utm_referrer=https://www.cloudflare.com/learning/dns/what-is-dns/), listed in seconds. The default TTL for A records is 14400 seconds. This means that if an A record gets updated, it takes 240 minutes (14400 seconds) to take effect.

The vast majority of websites only have one A record, but it’s possible to have several. Some higher profile websites will have several different A records as part of a technique called  [round robin load balancing](https://www.cloudflare.com/learning/dns/glossary/round-robin-dns/?utm_referrer=https://www.cloudflare.com/learning/dns/what-is-dns/), which can distribute request traffic to one of several IP addresses, each hosting identical content.
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTM2NzEzMTkyMywxMTAxMTc3NzcxLDEwNj
Q4MTY4MTAsLTMyMTQzMjA0MF19
-->