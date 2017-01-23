# docker-wp-nginx-mysql-php7-ssh
Wordpress latest (4.7.1) alap telepítése nginx (multisite config is!), php7.0, mysql, ssh és supervisor csomagokkal

Letöltés: docker pull adalon/adalonwp
Indítás: docker run -d -p 3307:3306 -p 80:80 -p 2222:22 -p 9011:9011 adalonwp

ssh és winscp: 127.0.0.1:2222-es porton (wordpress/wordpress)
mysql: 127.0.0.1:3307 (jelszó generált, kiolvasható innen /var/www/wp-config.php)
