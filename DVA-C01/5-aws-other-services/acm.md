# ACM - AWS Certificate Manager

- Used to host public SSl certificates in AWS
- There are two way of hosting an SSL certificate in AWS:
    - We can buy our own certificate and upload it to ACM using the CLI
    - We can have ACM provision and renew public SSL certificates for us (at no cost!)
- ACM loads SSL certificates on the following integrations:
    - Load balancers (including the ones created by Beanstalk)
    - CloudFront distributions
    - APIs and API Gateways

