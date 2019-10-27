# https_wordpress_docker

## generate pem for https
* cd renewcer/  #/home/https_wordpress_docker/renewcer/
* docker system prune
* docker system prune --volumes
* docker-compose up #console1

在/docker-volumes里面生成pem文件(另一个控制台console2)
* rm -rf /docker-volumes 
* sudo docker run -it --rm \
-v /docker-volumes/etc/letsencrypt:/etc/letsencrypt \
-v /docker-volumes/var/lib/letsencrypt:/var/lib/letsencrypt \
-v /home/https_wordpress_docker/renewcer/my-site:/data/letsencrypt \
-v "/docker-volumes/var/log/letsencrypt:/var/log/letsencrypt" \
certbot/certbot \
certonly --webroot \
--email youremail@domain.com --agree-tos --no-eff-email \
--webroot-path=/data/letsencrypt \
-d yongzhu.work -d www.yongzhu.work


* docker-compose down #console1
* cd nginx_mysql_wordpress #console2
* chown -R www-data:www-data  ./wordpress  #console2
* docker-compose up #console2



## debain10 docker install
* https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-debian-10

## debug

### mysql cannot start
df命令查看系统硬盘，可能因为已经100%用光了

