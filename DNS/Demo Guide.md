+ PURPOSE: 

This document outlines the components of an F5 Distributed Cloud DNS Demo necessary to publish a demo. The demo guide is accessible to Field SEs/SAs and AMs. The primary purpose of a demo guide is to provide a pre-built demo platform, that an SEs/SAs can show to a customer/prospect and, where appropriate, make minor changes/clone objects to show customizations/behaviors illustrating management, visibility and ease of use elements of F5 Distributed Cloud DNS. 

+ KEY COMPONENTS: 

 + Primary DNS 
    Use case description – Organizations can simplify delivery of modern, multi-cloud sites/apps with SaaS-based primary authoritative DNS, which quickly (and easily) delivers a scalable, highly performant and secure DNS solution for distributed user bases wherever your site/applications require. As a primary DNS solution, Distributed Cloud DNS brings maximum performance with improved response times via a geo-distributed cloud network, built-in DDoS protection, DNSEC (Coming Soon) and the flexibility to scale automatically to meet growing site/app demands (no hardware or software required). 

+ Customer pain point 
    Extending traditional DNS (often on premises) to an ever-growing number of sites/applications across different environments, especially those running in the cloud/across clouds and on premises, this can be time-consuming and cumbersome for many organizations. Not to mention the cost and complexity to manage as most on-premises DNS solutions don’t scale as easily to support the growing number of sites/apps and bandwidth demands of today. 

+ Secondary DNS 
    Use case description – Organizations can reduce load on, add resilience and scale to their existing/primary DNS infrastructure ensuring high availability and optimized performance of their DNS environments with seamless failover to F5 Distributed Cloud DNS. This serves to provide redundancy in the event of a primary service failure and improved response times if existing primary DNS service is disabled or degraded in any way. 

+ Customer pain point
    DNS is often taken for granted, if it stops working internet facing assets can be/are inaccessible. Many organizations have limited to no redundancy in case of attack, accidental failure or degraded performance. Today DNS infrastructure continues to be burdened by increasingly heavier loads and is often an easy attack target for someone interested in causing trouble so having a backup plan with the right scale, performance and security is more critical than ever. 

 

+ PRE-DEMO ENVIRONMENTAL SETUP: 

+ List of items/objects pre-provisioned: 

We have a DNS domain (INSERT DOMAIN)  for our web application, obtained from the Internet domain registrar 

We have name servers set up for managing our DNS records. 

To ensure that zone transfers are successful, we added the following IP addresses to our firewall/ACL allow list: 

52.14.213.208 
3.140.118.214 


+ DEMO GUIDE: 

+ Primary DNS: 

 + Problem Statement: Scaling legacy, on-prem DNS infrastructure/services to support modern, distributed sites/apps can be costly and difficult to manage. 

 + Expected outcome: Simplify delivery of modern, multi-cloud sites/apps with SaaS-based primary authoritative DNS which streamlines delivery of scalable, highly performant and secure authoritative DNS service supporting distributed user bases wherever sites/apps require. 

 + Steps: With just a few clicks and inputs you can show how easy and quick it is to set up this SaaS delivered, authoritative DNS solution. We can deliver both primary and secondary DNS…but will start by showing the setup of a primary DNS service for our demo app (INSERT NAME OF APP/SITE). Here is the opening services menu of the F5 Distributed Cloud Console, just select ‘DNS Management’ and within the DNS management workspace click on ‘Add DNS Zone’ and you will be off and running. 

[* Insert screenshot *] 

You will need to give this DNS Zone based on the site or apps domain & configure/set the zone type as a 'Primary DNS Configuration' then click on ‘Configure’ to move the next stage of setup. 

[* Insert screenshot *] 

If desired establish customer SOA (Start of Authority) parameters or simply select default parameters before create resource records. 

[* Insert screenshot *] 

Next we need to create the appropriate resource records, for example, A, AAAA, CNAME, ALIAS etc. You’ll just Click on ‘Add Item’ to set up resource records with the basic fields 

1) Set up a ‘time to live’ 
2) Select the appropriate ‘record set’ (e.g. type) 
3) Give the record a name and 
4) Provide IPv4 address/address range or block 

[* Insert screenshot *] 

[* Do you want to include resource record sets here? *] 

 
That’s really it. Now click ‘Save and Exit’ and we are done. It will take some time for the zone to change the status from pending to active so we can validate our Primary DNS Zone is up and running. 


The name servers listed here, and this information is needed in next step, where customers will delegate their domain to the F5 Distributed Cloud Platform so queries can be served and the domain can be hosted publicly on the internet with the F5 Distributed Cloud DNS service. 

 

+ Secondary DNS: 
 + Problem Statement: The existing (on-prem) DNS infrastructure/solution is struggling to keep up with growing request/traffic demands on the site/app and is being hampered by constant barrage of DDoS attacks impacting site uptime and performance.  
 
 + Expected outcome: A more resilient DNS solution, that can scale as needed, to keep up with growing site/app footprint, traffic demands. A backup DNS solution that can ease the burden on legacy DNS infrastructure and enhance the uptime and performance/reliability of a site/app.  

 + Steps to illustrate outcome (screenshots where needed) 
 We will now pivot to show you set up of secondary DNS with F5 Distributed Cloud DNS. We are starting with the same services menu of the F5 Distributed Cloud Console, just select ‘DNS Management’ and within the DNS management workspace click on ‘Add DNS Zone’ and you are ready to reinforce your existing primary DNS solution. 

 
You will need to give this DNS Zone a name based on the site or apps domain & configure/set the zone type as a 'Secondary DNS Configuration' then click on ‘Configure’ to move the next stage of setup. 

  
+ Steps:
1) Enter the DNS primary server IP address(es) 
2) Next we need to set up authentication (e.g. TSIG) if configured on the primary DNS service. Simply give the key a name, enter the key algorithm and secret info. Then copy the key string (we will need this later). That’s really it. 
3) Then click ‘Save and Exit’. It will take some time for the zone to change the status from pending to active so we can validate our Secondary DNS Zone is up and running 
4) We just need to verify the secondary zone we created is listed un the DNS management pain and lets ensure the zone is active. 

Edit the configuration, to see last successful AXFR timestamp, and zone file with RRs  
 

The name servers listed here, and this information is needed in next step, where customers will delegate their domain to the F5 Distributed Cloud Platform so queries can be served and the domain can be hosted publicly on the internet with the F5 Distributed Cloud DNS service. 


SIGN-OFF NOTES: 

Closing thoughts/guidance for sellers regarding takeaways from demo, and value-prop reinforcement statement 

 