## Task

The Nautilus devops team got some requirements related to some Apache config changes. They need to setup some redirects for some URLs. There might be some more changes need to be done. Below you can find more details regarding that:

1.) httpd is already installed on app server 3. Configure Apache to listen on port 8082.

Configure Apache to add some redirects as mentioned below:

a.) Redirect http://stapp03.stratos.xfusioncorp.com:<Port>/ to http://www.stapp03.stratos.xfusioncorp.com:<Port>/ i.e non www to www. This must be a permanent redirect i.e 301

b.) Redirect http://www.stapp03.stratos.xfusioncorp.com:<Port>/blog/ to http://www.stapp03.stratos.xfusioncorp.com:<Port>/news/. This must be a temporary redirect i.e 302.

## Configuration Changes

```conf
# change Listen as well
Listen 8082
NameVirtualHost *:8082
<VirtualHost *:8082>
  ServerName stapp01.stratos.xfusioncorp.com

  RewriteEngine On
  RewriteCond "%{HTTP_HOST}" "!^www\." [NC]
  RewriteCond "%{HTTP_HOST}" "!^$"
  RewriteRule "^/?(.*)"      "http://www.%{HTTP_HOST}:%{SERVER_PORT}/$1" [L,R=301,NE]
</VirtualHost>

<VirtualHost *:8082>
  ServerName www.stapp01.stratos.xfusioncorp.com
  DocumentRoot "/usr/local/apache2/htdocs"

  RewriteEngine On
  RewriteRule   "^/blog$"  "http://www.stapp01.stratos.xfusioncorp.com:%{SERVER_PORT}/news"  [R=302,L]
  RewriteRule   "^/blog/$"  "http://www.stapp01.stratos.xfusioncorp.com:%{SERVER_PORT}/news/"  [R=302,L]
  RewriteRule   "^/blog/(.*)"  "http://www.stapp01.stratos.xfusioncorp.com:%{SERVER_PORT}/news/$1"  [R=302,L]
</VirtualHost>
```

## How to verify

```
# verify

curl -I http://stapp01.stratos.xfusioncorp.com:8082 --resolve 'stapp01.stratos.xfusioncorp.com:8082:172.30.174.170'

curl -I http://www.stapp01.stratos.xfusioncorp.com:8082/blog/ --resolve 'www.stapp01.stratos.xfusioncorp.com:8082:172.30.174.170'
curl -I http://www.stapp01.stratos.xfusioncorp.com:8082/blog/index.html --resolve 'www.stapp01.stratos.xfusioncorp.com:8082:172.30.174.170'
```
