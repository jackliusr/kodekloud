The production support team of xFusionCorp Industries has deployed some of the latest monitoring tools to keep an eye on every service, application, etc. running on the systems. One of the monitoring systems reported about Apache service unavailability on one of the app servers in Stratos DC.



Identify the faulty app host and fix the issue. Make sure Apache service is up and running on all app hosts. They might not hosted any code yet on these servers so you need not to worry about if Apache isn't serving any pages or not, just make sure service is up and running. Also, make sure Apache is running on port 8086 on all app servers.

```bash
iptables -A INPUT -p tcp -m multiport --dports 8086 -m conntrack --ctstate NEW,ESTABLISHED -j ACCEPT
iptables-save
curl http://stapp01:8086
```