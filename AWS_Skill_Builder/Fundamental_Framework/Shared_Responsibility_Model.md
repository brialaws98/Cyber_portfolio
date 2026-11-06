###### Understanding this model is important because it defines who is responsible for what. This ensures that there are no unintentional gaps in your security posture that could expose your organization to risk

## AWS responsibilities: Security *of* the cloud
* AWS is responsible for protecting the vast global infrastructure provided by AWS
  * ***Hardware:***
    * *Physical servers and processors:* SSDs, HDDs, and tape systems for data storage
    * *Memory components:* RAM and other physical memory installations
    * *Network appliances:* Physical routers, switches, and load balancers
    * *Power supply systems:* Redundant power sources and backup generators
    * *Cooling systems:* Temperature control equipment for data centers
  * ***Software:****
    * *Virtualization layer:* Hypervisors that manage virtual machines
    * *Host operating systems:* The base OS running on physical servers
    * *AWS service software:* Code that runs services like Amazon Simple Storage Service (Aamzon S3), Amazon Elastic Compute Cloud (Amazon EC2), and Amazon DynamoDB
    * *AWS Management Console software:* The AWS web interface and portal
    * *API endpoints and infrastructure:* Software that handles API requests
    * *Database management software:* Underlying database management systems (DBMSs) for Amazon Relational database Service (Amazon RDS)
    * *Network management software:* Traffic control and routing systems
  * ***Networking:***
    * *Internal network infrastructure:* Data center network connections
    * Edge locations:* Content delivery network points of presence
    * *Network segmentation:* Internal security zones and boundaries
    * *Internet connectivity:* Redundant connections to internet service providers (ISPs)
    * *Inter-Region connectivity:* Private global network between AWS Regions
    * *Network monitoring systems:* Traffic analysis and anomaily detection
  * ***Facilities:***
    * *Data center buildings:* Physical structures hosting AWS equipment
    * *Physical security;* Guards, fences, biometric access controls
    * *Surveillance systems:* Closed-circuit television (CCTV) and other monitoring equipment
    * *Fire suppression systems:* Automated fire detection and prevention
    * *Environmental controls:* Humidity and temperature monitoring
    * *Entry and access point:* Secure entrances with multi-factor authentication
    * *Backup power infrastructure:* Generators and uninterruptible power supply (UPS) systems
## Customer responsibilities: Security *in* the cloud
* Depends on the AWS service selected and how it is configured
* Manage data
* The guest operating system on virtual servers
* Appliances
* Security configurations that are applied
* Virtual firewalls
  * Security and network access control lists (network ACLs)
  *  Network configurations within virtual private cloud (VPC)

# Introduction to the Well-Architected Framework and Security Pillar
