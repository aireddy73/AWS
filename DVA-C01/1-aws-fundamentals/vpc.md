# VPC: Virtual Private Cloud

- Within a region, you’re able to create VPCs. Each VPC contain subnets (networks). Each subnet must be mapped to an AZ. It’s common to have a public ip and private ip subnet. It’s common to have many subnets per AZ.

- Public Subnets usually contain:
    - Load Balancers
    - Static Websites
    - Files
    - Public Authentication Layers

- Private Subnets usually contain:
    - Web application servers
    - Databases

- Public and Private subnets can communicate if they’re in the same VPC

## AWS VPC Summary

- VPC & Regions aren’t much asked at the developer associate exam
- All new accounts come with a default VPC
- It’s possible to use a VPN to connect to a VPC
- VPC flow logs allow you to monitor the traffic within, in and out of your VPC (useful for security, performance, audit)
- VPC are per Account per Region
- Subnets are per VPC per AZ
- Some AWS resources can be deployed in VPC while others can’t
- You can peer VPC (within or across accounts) to make it look like they’re part of the same network

## ENI (Elastic Network Interface)

- An elastic network interface is a logical networking component in a VPC that represents a virtual network card. It can include the following attributes:
    - A primary private IPv4 address from the IPv4 address range of our VPC
    - One or more secondary private IPv4 addresses from the IPv4 address range of our VPC
    - One Elastic IP address (IPv4) per private IPv4 address
    - One public IPv4 address
    - One or more IPv6 addresses
    - One or more security groups
    - A MAC address
    - A source/destination check flag
    - A description
- We can create and configure network interfaces in your account and attach them to instances in your VPC.
- An AWS account might also have requester-managed network interfaces, which are created and managed by AWS services to enable to use other resources and services.