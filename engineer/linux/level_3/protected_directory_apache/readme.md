xFusionCorp Industries has hosted several static websites on Nautilus Application Servers in Stratos DC. There are some confidential directories in the document root that need to be password protected. Since they are using Apache for hosting the websites, the production support team has decided to use .htaccess with basic auth. There is a website that needs to be uploaded to /var/www/html/data on Nautilus App Server 1. However, we need to set up the authentication before that.



1. Create /var/www/html/data direcotry if doesn't exist.


2. Add a user mark in htpasswd and set its password to YchZHRcLkL.


3. There is a file /tmp/index.html present on Jump Server. Copy the same to the directory you created, please make sure default document root should remain /var/www/html. Also website should work on URL http://<app-server-hostname>:8080/data/


```bash
cat <<EOF > /var/www/html/data/.htaccess
AuthType Basic
AuthName "Require Authentication"
AuthUserFile /var/www/html/data/.htpasswd
Require valid-user
EOF

htpasswd -c /var/www/html/data/.htpasswd mark


curl -u mark:YchZHRcLkL http://stapp01:8080/data
```