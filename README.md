# ssl

=====================

#No.1

#Install certbot : نصب سرتیفیکیت

#sudo apt install certbot

#sudo apt install python3-certbot-nginx

#sudo apt install python3-certbot-apache


#sudo certbot --nginx --agree-tos --redirect --hsts --staple-ocsp --email YOUR-EMAIL-ADDRESS -d YOUR-SITE-ADDRESS

#sudo certbot-auto certonly --standalone -d YOUR-SITE-ADDRESS  -d www.YOUR-SITE-ADDRESS

#ls /etc/letsencrypt/live/YOUR-SITE-ADDRESS

#The result will be the following lines :

#fullchain.pem

#privkey.pem

#Enable Config file 

#nano /etc/nginx/sites-available/YOUR-SITE-ADDRESS (Without Suffix- ForEx : vira.conf).conf

#Paste the following lines :

ssl on;

ssl_certificate /etc/letsencrypt/live/YOUR-SITE-ADDRESS/fullchain.pem;

ssl_certificate_key /etc/letsencrypt/live/YOUR-SITE-ADDRESS/privkey.pem;


========================================

#No.2

#Install acme.sh

curl  https://get.acme.sh | sh

#Install netcat if needed

sudo apt-get -y install netcat

#generate Cert

#sudo ~/.acme.sh/acme.sh --issue -d YOUR-SITE-ADDRESS --standalone -k ec-256

#Renew cert

#sudo ~/.acme.sh/acme.sh --renew -d YOUR-SITE-ADDRESS --force --ecc

#or

#sudo ~/.acme.sh/acme.sh --renew -d YOUR-SITE-ADDRESS --force


