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
1. Update repo and install Nginx 

` sudo apt-get update && apt-get install nginx -y\ 
sudo /etc/init.d/nginx start\  
[ ok ] Starting nginx (via systemctl): nginx.service.  
sudo /etc/init.d/nginx status `  
