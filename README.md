# Install NGINX with self signed SSL certificate integration at Ubuntu 18.04
##steps below :
1. Update repo and install Nginx 
2. create openssl self sign private key and self signed certificate 
3. Create a Configuration Snippet Pointing to the SSL Key and Certificate
4. Configure Nginx sites-availabale/config file for SSL integration & website directory
5. Soft link between sites-available/config file   with sites-enable/ directory
6. Verify NGINX connection
7. Finally browse website and check whether it works or not 

## Implementation:
1. Update repo and install Nginx<br/> 
```
sudo apt-get update && apt-get install nginx -y
sudo /etc/init.d/nginx start
[ ok ] Starting nginx (via systemctl): nginx.service.
sudo /etc/init.d/nginx status
```
2. create openssl self sign private key and self signed certificate <br \>
sudo openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout /etc/ssl/private/nginx-selfsigned.key -out /etc/ssl/certs/nginx-selfsigned.crt<br \>
Generating a RSA private key<br \>
........................................................+++++<br \>
..+++++<br \>
writing new private key to '/etc/ssl/private/nginx-selfsigned.key'<br \>
-----<br \>
You are about to be asked to enter information that will be incorporated<br \>
into your certificate request.<br \>
What you are about to enter is what is called a Distinguished Name or a DN.<br \>
There are quite a few fields but you can leave some blank<br \>
For some fields there will be a default value,<br \>
If you enter '.', the field will be left blank.<br \>
-----<br \>
Country Name (2 letter code) [AU]:BD<br \>
State or Province Name (full name) [Some-State]:DHK<br \>
Locality Name (eg, city) []:DHK<br \>
Organization Name (eg, company) [Internet Widgits Pty Ltd]:Self<br \>
Organizational Unit Name (eg, section) []:self<br \>
Common Name (e.g. server FQDN or YOUR name) []:asifops.io<br \>
Email Address []:<br \>

both of the private key and certificate files created under /etc/ssl directory <br \>

