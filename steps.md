# Environment 
* dibain10
# Set ssh
* `vi /etc/ssh/sshd_config `  
* change `#PermitRootLogin prohibit-password` to `PermitRootLogin yes`  
* `passwd root`
* `systemctl restart sshd`
# Install docker
*  https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-debian-10

# Install docker-compose
* https://docs.docker.com/compose/install/


# upload 2M size problem
```
docker exec -it b9eae89777e6   /bin/bash
apt-get update
apt-get install -y vim
apt-get update && apt-get install -y procps  #ps
```
```
root@b9eae89777e6:/var/www/html# find  /usr/local/etc/  -type f |xargs grep "upload_max_filesize"
/usr/local/etc/php/php.ini-production:upload_max_filesize = 2M
/usr/local/etc/php/php.ini-development:upload_max_filesize = 2M
```
以下两个要一起修改才有作用
* /usr/local/etc/php/php.ini-production:post_buffer_size 
* /usr/local/etc/php/php.ini-production:upload_max_filesize

# php-pfm settings
* /usr/local/etc/php/  (php.ini要手动通过2个模版copy)

## add cdn 
* https://navi.onamae.com/domain/setting/ns/22186144  mapreduce.lz@gmail.com  Zl_666888
