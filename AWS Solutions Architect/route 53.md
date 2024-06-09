## dns overview
- domain name system that translates freidnly hostnames into the machine ip adderss
- google.com => 172.x.x.x.
- DNS is the backbone of the internet
- DNS uses a hierarchial system
- domain registar amazon route 53 godaddy google any company that can sell the domain name
- dns record a aaaa cname ns
- zone file contains all the dns recored
- name server resolves the dns queries aut ir no auth
- top level domain .com .us .in etc
- the last dot is the root the .com is a tld id example subdomain apu is FNQDN protrocall url

# route 53
## overview
- a highly availavle scaleable fully managed and authorative dns
- the customer can upadatethe dnd recores
- route 53 is also a domain name registart so you can store your domain names there
- has the ability check the heatlh of your resources
- the only aws service whicha provides a 100 sla

# record
**overview**: how you want to route traffic for a domain

## each will contain
- domain subdomain example.com
- record type a or aaaa
- value 1;2;3;4
- routing policy how rout 53 responds to queries
- ttl timt to live amount of time that the record cached at dns resolver
- dnvs record dypes a cname ns

# record types
**a**: maps a hostname to an ipv4 address

**aaaa**: maps a hostname to ipv6

**cname**: maps a hostname to another hostname the targer domain which must have a or aaaa record and cannot create a cnmae record for the top node of a dns namespace

**NS**: name server record specifes the dns servers for your nomain

## Hosted Zones
- a container for records that define how to route traffic to a domainn and its subdomain
- public hostes zone contains records that specify howo to route traffic on the interenet
- private hosted zone contian records that specify how you route traffic wihin one vpc
- any hosted zone you pay 50 per month
- you have have high and low ttl
- if you set a high ttl you will have less traffiv to your route 53 but you will have to wait for the ttl to expire so you could have outdated recorods
- if you set a low ttl you will have more traffic to your route 53 but the records will be outdated for less tim
- except for alias records ttl is mandatory for each dns record

# cname vs alias
**overview**: aws resources lb cf etc expose an aws hostome like lb;us-east-2.elm

## cname
- Points a hostname to any other hostname app.mydomain.com => helo.anythign.com
- only for non roor domain aka somehting.com

## alias
- points a hostname to an aws resource my app domain.com => blalala.amazonaws.com
- workd for rood domain and non rorot domain
- free of charge and native health check built wihtin them

## alias records
- maps a hostname to only aws resources
- extension to dns functionality
- Automaticly recognizes changes in resourse ip address
- unlike cnmae it can be used for the top node of a dns namespace zone apex example.com
- cannot set tht ttl the ttl is set by aws for free

## alias records targets
- elastic load balancers
- clodfront distributions
- api gateway
- elastic beanstalk enviorent
- s3 websites not when used as storage but when setup as websites
- vpc intereface endpont
- global acceertator acceleratoer
- route 54 record in the same hosted zone
- you cannot set an alais record for an ec2 instance dns name

## route 53 health checks
- https health checks are only ro public resoures
- health check =>  automated dns failover
- health checks that monitor an ednpoint application server other aws resources
- calculated healthcheck for oother health checks
- cloudwathc alarsms
- 15 globals health chekcers will check the endpoing helth
- healthy / unleahtly threshold 3 default
- interval 30 seconds can be set to 10 seconds but will have higher costs
- supported protocol for http https and tcp
- to check the private resourse you cannot use health checks you can create a clodwatch metric and associate a clodwatch alarm whtn create a health check that checks the alarm itsself

## routing policies failover
- if the health check become unhealth it will route to the failover

## geolocation
- the routing is based on user location
- specify location by conent country or by us satate
- shoudl create a default record in case there no match on locantion
- can be assostate with halth check wnsite location restriciton conenet diteoru laod

## geoproxikity
- route traffic to your resourse based on the geographic location if users and resourse
- abilityu to shift more traffic to resourse based on th edefined basas
- you can use bias value to diret more traffic to a resourse
- advancded traffic flow

## ip based
- route traffic to your resourse based on the ip address

