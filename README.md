## Shadowsocks/r web manager

English |[中文](https://github.com/moeik/ssr-web/blob/master/readme_zh_cn.md)

#### Description

This project is used to manage users of shadowsocks/r working with another excellent shell writen by doubi, aiming to make it easier for you to share your shadowsocks/r with you firends
Please be aware that there was no security tests on this project

#### Functions

##### Admin user:

- [x] 1、add user

- [x] 2、delete user

- [x] 3、change settings

##### Visitor: (with a suffix)(/visitor)

- [x] see infos

#### System supported

Debian 9 only

#### Language

Python3.6 required

#### Web Framework

web.py==0.40.dev1


#### Usage

Before you start this web, make sure you have installed another awesome shell 'ssrmu.sh'. 
If not, please  install ssemu.
```
wget -N --no-check-certificate https://raw.githubusercontent.com/ToyoDAdoubi/doubi/master/ssrmu.sh
chmod +x ssrmu.sh
bash ssrmu.sh
```

Switch to super user root using `sudo su`

##### Method 1

Git is also required, using `apt install git`

And surely python3 `apt install python3`

Clone this project to `/usr/local`  using `git clone https://github.com/moeik/ssr-web.git /usr/local/ssr-web` 
and `cd` into it `cd /usr/local/ssr-web`

Then

1. install nginx using `apt install nginx` 
2. change the server_name in file 'nginx' to your domain 
3. install apache2-utils using `apt install apache2-utils`
4. generate password using `htpasswd -c /etc/nginx/passwd.db username`
5. change the website in line 3 of file 'ssr.py' to your domain        
6. copy file `nginx` in to `/etc/nginx/sites-enabled/` using `cp nginx /etc/nginx/sites-enabled/`                
7. restart nginx with `nginx -s reload`                    
8. install venv and pip using `apt install python3-venv python3-pip`   
9. create virtual-env for web.py using `python3 -m venv venv`          
10.start it `bash run.sh` 

##### Or Method 2

1. 
```
apt install python3 python3-pip python3-venv git nginx apache2-utils -y;
git clone https://github.com/moeik/ssr-web.git /usr/local/ssr-web;
cd /usr/local/ssr-web;
```
2. change the server_name in line 3 of file 'nginx' to your domain
3. change the website in line 3 of file 'ssr.py' to your domain
4. `cp nginx /etc/nginx/sites-enabled/;`
5. change the username to anything you like and generate your password `htpasswd -c /etc/nginx/passwd.db username`
6.

```
nginx -s reload;
python3 -m venv venv;
bash run.sh;

```
#### Previews

homepage: user_infos

![](https://i.loli.net/2019/02/14/5c652c78795e0.png)

user_configs:

![](https://i.loli.net/2019/02/14/5c652c7860e24.png)

edit user_config:

![](https://i.loli.net/2019/02/14/5c652c784084c.png)
