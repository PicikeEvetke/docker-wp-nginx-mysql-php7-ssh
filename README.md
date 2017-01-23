# Wordpress 4.7.1 alap telepítése
### nginx, php7.0, mysql, ssh és supervisor csomagokkal
## /// Install Docker.io ///
```
apt-get update
apt-get upgrade
apt-get install docker.io
systemctl start docker
systemctl enable docker
docker version
```

## /// AdalonWP Docker build indítása ///
```
docker build -t adalonwp .
```

## /// AdalonWP Docker futtatása ///
```
docker run -d -p 3307:3306 -p 80:80 -p 2222:22 -p 9011:9011 adalonwp
```

## /// AdalonWP Docker leállítása ///
```
docker ps
docker stop [CONTAINER_ID]
```

### Útmutató a Docker containerhez
- Letöltés: docker pull adalon/adalonwp
- Indítás: docker run -d -p 3307:3306 -p 80:80 -p 2222:22 -p 9011:9011 adalonwp
- web: http://localhost *(vagy vedd fel a domain címét a host fileba, pl. 127.0.0.1 adalon.hu www.adalon.hu)*
- ssh és winscp: 127.0.0.1:2222-es porton *(wordpress/wordpress)*
- mysql: 127.0.0.1:3307 *(jelszó generált, kiolvasható innen /var/www/wp-config.php)*

### Docker kipucolása
```
docker rm $(docker ps -a -q)
docker rmi $(docker images -q)
docker volume rm $(docker volume ls -qf dangling=true)
```
