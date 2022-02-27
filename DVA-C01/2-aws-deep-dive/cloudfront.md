# CloudFront

- CloudFront is a content delivery network (CDN)
- Improved read performance by caching the static content at the edge locations
- AWS currently has around 216 edge locations (Points of Presence) globally
- Besides caching CloudFront offers:
    - DDoS protection
    - Integration with Shield and AWS Web Applications Firewall (WAF)
- We can expose HTTPS end-point by loading certificates onto CloudFormation
- CloudFormation can talk with internal services using HTTPS as well

## CloudFront Origins

- S3 bucket:
    - Common pattern for distributing files globally and caching them at the edge locations
    - Offers enhanced security with CloudFront **Origin Access Identity (OAI)** - only allow communication to S3 bucket from CloudFront for end users
    - CloudFront can be used as an ingress for uploading files to S3
- Custom Origin (HTTP):
    - Could be anything that respects the HTTP protocol, example EC2, S3 website, any HTTP back-end

### Restrict access to S3

- To restrict access to content that we serve from Amazon S3 buckets, we can follow these steps:
    1. Create a special CloudFront user called an origin access identity (OAI) and associate it with our distribution.
    2. Configure your S3 bucket permissions so that CloudFront can use the OAI to access the files in our bucket and serve them to our users. Make sure that users can’t use a direct URL to the S3 bucket to access a file there.

## CloudFront Geo Restriction

- We can restrict who can access our distribution be using:
    - Whitelist: allows our users to access our content if they are from countries that are on our list
    - Blacklist: prevents users to access our content if they are from countries which are on our list
- The country is determined by a 3rd party Geo-IP database

## CloudFront vs S3 Cross Region Replication

|CloudFront                                                   | S3 CRR                                                                        |
|-------------------------------------------------------------|-------------------------------------------------------------------------------|
| Global Edge Network                                         | Must be configured for each region where we want to replication to happen     |
| Files are cached for a TTL                                  | Files always latest                                                           |
| Great for static content which must be available everywhere | Great for dynamic content the must be available at low latency in few regions |

## CloudFront Caching

- We can cache data based on:
    - Request headers
    - Session Cookies
    - Query String Parameters
- The cache lives at each CloudFront Edge Locations
- In order to maximize cache hits we can control the TTL (form 0 seconds to 1 year). TTL can be set by the origin using the Cache-Control header and Expires header
- We can invalidate part of the cache using the **CreateInvalidation** API

## CloudFront Security

### HTTPS

- View Protocol Policy - between the end client and edge location
    - Redirect HTTP to HTTPS
    - Use HTTPS only
- Origin Protocol Policy - between edge location and origin
    - HTTPS only
    - Match Viewer: if the client is using HTTP, the connection between CloudFront and origin will also use HTTP. Same with HTTPS. In case origin access identity is enabled, the match viewer policy will be HTTPS
- Note: S3 bucket website will only support HTTPS connection

### CloudFront Signed URL / Signed Cookies

- Used for distributing premium content
- In order to create a Signed ULR / Cookie, first we need to create a policy with:
    - Includes URL expiration
    - Includes IP ranges to access the data from
    - Trusted signers (which AWS accounts can create signed URLs)
- How long should the URL be shared for:
    - Shared content (movie, music): we should make is short
    - Private content (private to user): we can make this last longer
- Signed URL = can give access to individual file
- Signed Cookies = can give access to multiple files

## CloudFront Signed URL vs S3 Pre-Signed URL

| CloudFront Signed URL                          | S3 Pre-Signed URL |
|------------------------------------------------|-------------------------------------------------------|
| Allows access to a path, no mather of origin   | Issues a request as the person whe pre-signed the URL |
| Account wide key-pair, only root can manage it | Uses the IAM key for the signing principle            |
| Can filter by IP, path, date expiration        | Limited lifetime                                      |
| Can leverage caching features                  |                                                       |