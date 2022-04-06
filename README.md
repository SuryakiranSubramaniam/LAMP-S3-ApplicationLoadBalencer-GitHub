# LAMP-S3-ApplicationLoadBalencer-GitHub

In this project we setup a LAMP server and host a wordpress site in it.The images in the wordpress site will be loaded from the S3 bucket

![alt text](https://github.com/SuryakiranSubramaniam/LAMP-S3-ApplicationLoadBalencer-GitHub/blob/main/image/Diagram1.png)

amazon-linux-extras install php7.4

yum install php-xmlwriter

yum install git

~~yum install libxml2
yum install php-xml
yum install php-gd
~~


yum install httpd -y ; systemctl restart httpd.service ; systemctl enable httpd.service

yum install mariadb-server -y ; systemctl restart mariadb.service ; systemctl enable mariadb.service

mysql_secure_installation

mysql -u root -p123

wget https://wordpress.org/latest.tar.gz

tar -xvf latest.tar.gz

cp -r wordpress/* /var/www/html/
chown -R apache:apache /var/www/html/*

vim /var/www/html/info.php

cp /var/www/html/wp-config-sample.php /var/www/html/wp-config.php

vim /var/www/html/wp-config.php

systemctl restart httpd
systemctl restart php-fpm

ssh-keygen
ls
cat new.pub 
eval $('ssh-agent')
ssh-add -k /root/new
ssh-add -l
chmod 400 new

cd /var/www/html/
git init

git config user.name "suryakiransubramaniam"

git config user.email "suryakiran.ssat@gmail.com"

git remote add origin git@github.com:SuryakiranSubramaniam/dev.suryakiran.online.git

git status

git add .

git status 

git commit -m "31-03-2022"

git push -u origin master
 
 
 
