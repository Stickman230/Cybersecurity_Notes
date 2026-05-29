#shodan #Tools 
Shodan is a **search engine for the Internet of Things (IoT)**, 

 Shodan continuously scans the internet, searching for
 -  networking equipment, 
 - industrial control systems,
 - traffic cameras, 
 - virtually anything else with a public network connection to see what's running and where.
   
Shodan also supports its own query filters, which let you narrow results significantly:

|   |   |   |
|---|---|---|
|**Filter**|**Description**|**Example**|
|`country`|Restrict results to a specific country code.|`country:IE`|
|`port`|Filter by a specific port number or a range.|`port:22`|
|`org`|Scope results in a named organisation or ASN Identifier (Who owns a range of IP addresses).|`AS7224`  <br>(Amazon Web Services)|
|`hostname`|Match against a specific hostname or domain.|`hostname:fakebank.thm`|