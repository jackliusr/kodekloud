Day by day traffic is increasing on one of the websites managed by the Nautilus production support team. Therefore, the team has observed a degradation in website performance. Following discussions about this issue, the team has decided to deploy this application on a high availability stack i.e on Nautilus infra in Stratos DC. They started the migration last month and it is almost done, as only the LBR server configuration is pending. Configure LBR server as per the information given below:



a. Install nginx on LBR (load balancer) server.


b. Configure load-balancing with the an http context making use of all App Servers.


c. Also make sure Apache service is up and running on all app servers.


d. Once done, you can access the website using StaticApp button on the top bar.

```
# stlb01	172.16.238.14	stlb01.stratos.xfusioncorp.com	loki	Mischi3f	Nautilus HTTP LBR

#stapp01	172.16.238.10	stapp01.stratos.xfusioncorp.com	tony	Ir0nM@n	Nautilus App 1
#stapp02	172.16.238.11	stapp02.stratos.xfusioncorp.com	steve	Am3ric@	Nautilus App 2
#stapp03	172.16.238.12	stapp03.stratos.xfusioncorp.com	banner	BigGr33n	Nautilus App 3

#stapp01 0.0.0.0:8085
#stapp02 0.0.0.0:8085
#stapp03 0.0.0.0:8085

ssh loki@stlb01
#make httpd running in all app servers
yum install -y httpd 
```

```nginx
http {
    upstream myapp1 {
        server stapp01:8085;
        server stapp01:8085;
        server stapp03:8085;
    }

    server {
        listen 80;

        location / {
            proxy_pass http://myapp1;
            proxy_redirect off;
            proxy_set_header X-Forwarded-Host $host;
            proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
            proxy_set_header X-Real-IP $remote_addr;
        }
    }
}
```