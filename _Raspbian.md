### Raspbian
```sh
sudo apt-get update       # 패키지 인덱스 정보 갱신
sudo apt-get upgrade      # 설치된 패키지 업그레이드
sudo apt-get dist-upgrade # 자동 업그레이드 수행 못한 패키지 업그레이드
```
  
###### output directory list
```sh
ls [-al]
#OR
dir [-al]
```
  
###### set-up ftp
```sh
# install vsftpd
[sudo] apt-get install vsftpd

# edit vsftpd.conf file
vi /etc/vsftpd.conf

anonymous_enable=NO
local_enable=YES
write_enable=YES
local_umask=022
chroot_local_user=YES
chroot_list_enable=YES
chroot_list_file=/etc/vsftpd.chroot_list

# create vsftpd.chroot_list file and edit
sudo vi /etc/vsftpd.chroot_list

# type "pi" and then :wq

# restart vsftpd
sudo service vsftpd restart
# OR
sudo systemctl restart vsftpd

# check vsftpd status
sudo systemctl status vsftpd
```
  
###### access server by ssh
```sh
# before using ssh protocal private IP is set only port Number "22"!!!
# ssh -p [port] [username]@[hostname]

ssh -p 9999 pi@111.222.33.44
```

###### access server by (s)ftp
```sh
# before we access server using ftp
# please check protocal whether "SFTP" or not
# we must use "SFTP"
