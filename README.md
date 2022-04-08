# LAMP-S3-ApplicationLoadBalencer-GitHub

In this project we setup a LAMP server and host a wordpress site in it.The images in the wordpress site will be loaded from the S3 bucket

![alt text](https://github.com/SuryakiranSubramaniam/LAMP-S3-ApplicationLoadBalencer-GitHub/blob/main/image/Diagram1.png)

## Create an EC2 instance called dev.suryakiran.online



amazon-linux-extras install php7.4 -y

yum install php-xmlwriter -y

yum install git -y

yum install php-gd -y

yum install httpd -y ; systemctl restart httpd.service ; systemctl enable httpd.service

yum install mariadb-server -y ; systemctl restart mariadb.service ; systemctl enable mariadb.service

## Mysql secure installation

mysql_secure_installation

## Wordpress user creation

mysql -u root -p123

create database wordpress;

create user 'wordpress'@'%' identified by 'wordpress';

grant all privileges on wordpress.* to 'wordpress'@'%';

flush privileges;

## Deploying wordpress site

wget https://wordpress.org/latest.tar.gz

tar -xvf latest.tar.gz

cp -r wordpress/* /var/www/html/

vim /var/www/html/info.php

<?php

phpinfo();

?>

cp /var/www/html/wp-config-sample.php /var/www/html/wp-config.php

chown -R apache:apache /var/www/html/*

vim /var/www/html/wp-config.php

define( 'DB_NAME', 'wordpress' );

/** Database username */
define( 'DB_USER', 'wordpress' );

/** Database password */
define( 'DB_PASSWORD', 'wordpress' );

/** Database hostname */
define( 'DB_HOST', 'localhost' );

systemctl restart httpd

systemctl restart php-fpm

## Application Load Balancer

#### Createing Target Group

![alt text](https://github.com/SuryakiranSubramaniam/LAMP-S3-ApplicationLoadBalencer-GitHub/blob/main/image/Target%20groups.png)

![alt text](https://github.com/SuryakiranSubramaniam/LAMP-S3-ApplicationLoadBalencer-GitHub/blob/main/image/tg2.png)

![alt text](https://github.com/SuryakiranSubramaniam/LAMP-S3-ApplicationLoadBalencer-GitHub/blob/main/image/tg3.png)

![alt text](https://github.com/SuryakiranSubramaniam/LAMP-S3-ApplicationLoadBalencer-GitHub/blob/main/image/tg4.png)

![alt text](https://github.com/SuryakiranSubramaniam/LAMP-S3-ApplicationLoadBalencer-GitHub/blob/main/image/tg5.png)

#### Createing Application Load Balancer

![alt text](https://github.com/SuryakiranSubramaniam/LAMP-S3-ApplicationLoadBalencer-GitHub/blob/main/image/al1.png)

![alt text](https://github.com/SuryakiranSubramaniam/LAMP-S3-ApplicationLoadBalencer-GitHub/blob/main/image/al3.png)

![alt text](https://github.com/SuryakiranSubramaniam/LAMP-S3-ApplicationLoadBalencer-GitHub/blob/main/image/al4.png)

![alt text](https://github.com/SuryakiranSubramaniam/LAMP-S3-ApplicationLoadBalencer-GitHub/blob/main/image/al5.png)

![alt text](https://github.com/SuryakiranSubramaniam/LAMP-S3-ApplicationLoadBalencer-GitHub/blob/main/image/al6.png)

![alt text](https://github.com/SuryakiranSubramaniam/LAMP-S3-ApplicationLoadBalencer-GitHub/blob/main/image/al7.png)

## Creating S3 Bucket

![alt text](https://github.com/SuryakiranSubramaniam/LAMP-S3-ApplicationLoadBalencer-GitHub/blob/main/image/s31.png)

![alt text](https://github.com/SuryakiranSubramaniam/LAMP-S3-ApplicationLoadBalencer-GitHub/blob/main/image/s32.png)

![alt text](https://github.com/SuryakiranSubramaniam/LAMP-S3-ApplicationLoadBalencer-GitHub/blob/main/image/s33.png)

![alt text](https://github.com/SuryakiranSubramaniam/LAMP-S3-ApplicationLoadBalencer-GitHub/blob/main/image/s34.png)

## Adding Records to Route53

![alt text](https://github.com/SuryakiranSubramaniam/LAMP-S3-ApplicationLoadBalencer-GitHub/blob/main/image/r53.png)

## Installing Wordpress

![alt text](https://github.com/SuryakiranSubramaniam/LAMP-S3-ApplicationLoadBalencer-GitHub/blob/main/image/wp1.png)

![alt text](https://github.com/SuryakiranSubramaniam/LAMP-S3-ApplicationLoadBalencer-GitHub/blob/main/image/wphttps.png)

![alt text](https://github.com/SuryakiranSubramaniam/LAMP-S3-ApplicationLoadBalencer-GitHub/blob/main/image/wp2.png)

![alt text](https://github.com/SuryakiranSubramaniam/LAMP-S3-ApplicationLoadBalencer-GitHub/blob/main/image/wp3.png)

![alt text](https://github.com/SuryakiranSubramaniam/LAMP-S3-ApplicationLoadBalencer-GitHub/blob/main/image/wp4.png)

![alt text](https://github.com/SuryakiranSubramaniam/LAMP-S3-ApplicationLoadBalencer-GitHub/blob/main/image/wp5.png)

![alt text](https://github.com/SuryakiranSubramaniam/LAMP-S3-ApplicationLoadBalencer-GitHub/blob/main/image/wp6.png)

![alt text](https://github.com/SuryakiranSubramaniam/LAMP-S3-ApplicationLoadBalencer-GitHub/blob/main/image/wp7.png)

![alt text](https://github.com/SuryakiranSubramaniam/LAMP-S3-ApplicationLoadBalencer-GitHub/blob/main/image/wp8.png)

![alt text](https://github.com/SuryakiranSubramaniam/LAMP-S3-ApplicationLoadBalencer-GitHub/blob/main/image/wp9.png)

![alt text](https://github.com/SuryakiranSubramaniam/LAMP-S3-ApplicationLoadBalencer-GitHub/blob/main/image/wp10.png)

![alt text](https://github.com/SuryakiranSubramaniam/LAMP-S3-ApplicationLoadBalencer-GitHub/blob/main/image/wp11.png)

![alt text](https://github.com/SuryakiranSubramaniam/LAMP-S3-ApplicationLoadBalencer-GitHub/blob/main/image/wp12.png)

![alt text](https://github.com/SuryakiranSubramaniam/LAMP-S3-ApplicationLoadBalencer-GitHub/blob/main/image/wp13.png)

![alt text](https://github.com/SuryakiranSubramaniam/LAMP-S3-ApplicationLoadBalencer-GitHub/blob/main/image/wp14.png)

![alt text](https://github.com/SuryakiranSubramaniam/LAMP-S3-ApplicationLoadBalencer-GitHub/blob/main/image/wp15.png)

![alt text](https://github.com/SuryakiranSubramaniam/LAMP-S3-ApplicationLoadBalencer-GitHub/blob/main/image/16.png)


## Generating Key for GitHub

ssh-keygen
ls
cat new.pub 
eval $('ssh-agent')
ssh-add -k /root/new
ssh-add -l
chmod 400 new

## Pushing to GitHub

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
 
 
 
