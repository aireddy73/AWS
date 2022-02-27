# Route 53

- Route 53 is a managed DNS (Domain Name System)
- DNS is a collection of rules and records which helps clients understand how to reach a server through URLs.

- In AWS, the most common records are (will be on exam):
    - A: URL to IPv4
    - AAAA: URL to IPv6
    - CNAME: URL to URL
    - ALIAS: URL to AWS resource

- Route 53 can use:
    - Public domain names you own
    - Private domain names that can be resolved by your instances in your VPCs

- Route53 has advanced features such as:
    - Load balancing (through DNS - also called client load balancing)
    - Health checks (although limited…)
    - Routing policy: simple, failover, geolocation, geoproximity, latency, weighted

- Prefer Alias over CNAME for AWS resources (for performance reasons)

## DNS Records TTL (Time to Live)

- TTL a is way for web browser adn clients to cache the response of the DNS query
- Reason for caching is not to overload the DNS
- The client will cache the DNS response for the duration of the TTL value (duration value is seconds)
- High TTL (24 hours):
    - Less traffic for DNS
    - Possibility of outdated records
- Low TTL (60 seconds):
    - More traffic on DNS
    - DNS records wont be outdated for longer periods which makes changing DNS records easier
- **TTL is mandatory for each DNS record!**

## CNAME Records vs Alias Records

- AWS resources usually expose an AWS hostname
- CNAME (Canonical Name record): 
    - Points a domain name to any another domain name (example: app.mydomain.com => other.domain.com)
    - **CNAME records work only for non root domains!** (example of a non-root domain: something.rootdomain.com)
- Alias records:
    - Point a hostname to an AWS resource (app.mydomain.com => something.amazonaws.com)
    - Alias records work for both root and non-root domain
    - They are free of charge
    - They can do health checks

## Route53 Health Checks

- If an instance is unhealthy, Route53 does not send traffic to it
- An instance is unhealthy if if fails to respond to X (default 3) amount of requests in a row
- It becomes healthy again if passes X (default 3) health checks in a row
- Default health checks interval is 30s (Fast Health Checks: can be set to 10s - higher cost)
- About 15 health checkers will check the end-point's health
- Health check protocols: HTTP, TCP, HTTPS (no SSL verification)
- Can be integrated with CloudWatch

## Routing Policies

### Simple Routing Policy

- Used to redirect to a single source
- We can not attach health checks to a simple routing policy
- Simple routing policy can return multiple values to a client
- If multiple values are returned the client can chose a random value

### Weighted Routing Policy

- Controls the percentage of the requests that go to a specific end-point
- Helpful to test a certain percentage of traffic on a new application version
- Helpful to split traffic between two regions
- Can be associated with health checks

### Latency Routing Policy

- Redirects to a server that has the least latency to the client
- Mainly used when latency is a priority for the clients
- Latency is evaluated in terms of user to designed AWS Region

### Failover Routing Policy

- Requires a primary record and a secondary record (disaster recovery)
- If the primary record fails, traffic is routed to the secondary record
- Requires a health check in order to work, failover is detected based on health checks

### Geo Location Routing Policy

- It is routing based on the user's location
- We can specify where the traffic should be routed if the user is requesting from an IP that originates from a country
- Requires a default policy (in case there is no match for a location)

### Multi Value Routing Policy

- Can be used when we need to route traffic to multiple resources and we want to associate Route53 health checks to the records
- It will return up to 8 healthy records for each Multi Value query
- It is not a substitute for Elastic Load Balancer!