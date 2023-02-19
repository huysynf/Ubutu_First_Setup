# ubutu-setup

```bash 

sudo apt-get update && sudo apt-get upgrate -y

sudo apt install wget git curl snapd zsh -y

```

# chorme

``` bash
wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb

sudo dpkg -i google-chrome-stable_current_amd64.deb

```

# ohmyzsh

 ```bash 
  sh -c "$(wget https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh -O -)"

 ```
## set default zsh 
```bash 

sudo chsh -s $(which zsh)
# or 

chsh -s $(which zsh)

```
## custom zsh theme 

```bash 
# down load theme 
git clone https://github.com/zsh-users/zsh-autosuggestions.git $ZSH_CUSTOM/plugins/zsh-autosuggestions && 
 git clone https://github.com/zsh-users/zsh-syntax-highlighting.git $ZSH_CUSTOM/plugins/zsh-syntax-highlighting

git clone https://github.com/denysdovhan/spaceship-prompt.git "$ZSH_CUSTOM/themes/spaceship-prompt" --depth=1


ln -s "$ZSH_CUSTOM/themes/spaceship-prompt/spaceship.zsh-theme" "$ZSH_CUSTOM/themes/spaceship.zsh-theme" 

#set theme

 nano ~/.zshrc

 # in the file search and  write:  zsh-autosuggestions zsh-syntax-highlighting => to plugin , spaceship => to theme name

  source ~/.zshrc

```
 

  ## docker
```bash 


  sudo apt update
sudo apt install apt-transport-https ca-certificates curl software-properties-common -y

curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -



sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu bionic stable"

sudo apt update
sudo apt install docker-ce -y
sudo usermod -aG docker ${USER}
su - ${USER}
```

## docker compose


```bash 
sudo curl -L "https://github.com/docker/compose/releases/download/1.29.1/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

sudo chmod +x /usr/local/bin/docker-compose

```


## install php storm and web storm with snapd


```bash 
sudo snap install phpstorm --classic
sudo snap install webstorm --classic

``` 

## generate ssh key git
```bash 

ssh-keygen -t rsa -b 2048 -C "email@example.com"
# or 
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```
# php 
``` bash 
sudo apt install php -y

sudo apt install composer nodejs -y

sudo apt install php-mysql php-gd openssl php-common php-curl php-json php-mbstring php-mysql php-xml php-zip

```

# install conky

# install d-config
```bash 
sudo apt-get install -y dconf-editor


```

# install ibus bamboo
```bash 
    sudo add-apt-repository ppa:bamboo-engine/ibus-bamboo
    sudo apt-get update
    sudo apt-get install ibus-bamboo
    ibus restart

```
# install php 8
```bash 
sudo apt update && sudo apt -y upgrade
sudo apt install lsb-release ca-certificates apt-transport-https software-properties-common -y
sudo add-apt-repository ppa:ondrej/php
sudo apt install php8.1 -y
sudo apt install php8.1-{bcmath,xml,fpm,mysql,zip,intl,ldap,gd,cli,bz2,curl,mbstring,pgsql,opcache,soap,cgi} -y


```
# uninstall apache 2 


```bash 
 sudo service apache2 stop
 sudo apt-get purge apache2 apache2-utils
 sudo apt-get autoremove
$whereis apache2

sudo rm -rf /etc/apache2
```
# install composer
```bash 
curl -sS https://getcomposer.org/installer -o composer-setup.php
sudo php composer-setup.php --install-dir=/usr/bin --filename=composer

```

# install nginx
```bash 

sudo apt install nginx -y
sudo ufw app list 
sudo ufw allow 'Nginx HTTP'
sudo ufw status
systemctl status nginx
```
# install nginx laravel

```bash 
sudo chown -R www-data.www-data /var/www/html/laravel/storage
sudo chown -R www-data.www-data /var/www/html/laravel/bootstrap/cache
sudo nano /etc/nginx/sites-available/ <file nginx>

```
### nginx file example
```text 
server {
    listen 80;
    server_name server_domain_or_IP;
    root /var/www/travellist/public;

    add_header X-Frame-Options "SAMEORIGIN";
    add_header X-XSS-Protection "1; mode=block";
    add_header X-Content-Type-Options "nosniff";

    index index.html index.htm index.php;

    charset utf-8;

    location / {
        try_files $uri $uri/ /index.php?$query_string;
    }

    location = /favicon.ico { access_log off; log_not_found off; }
    location = /robots.txt  { access_log off; log_not_found off; }

    error_page 404 /index.php;

    location ~ \.php$ {
        fastcgi_pass unix:/var/run/php/php7.4-fpm.sock;
        fastcgi_index index.php;
        fastcgi_param SCRIPT_FILENAME $realpath_root$fastcgi_script_name;
        include fastcgi_params;
    }

    location ~ /\.(?!well-known).* {
        deny all;
    }
}
```
```bash 

sudo ln -s /etc/nginx/sites-available/default /etc/nginx/sites-enabled/
sudo nginx -t
sudo systemctl reload nginx
```

# ssl nginx cerbot
```bash 
sudo snap install --classic certbot
sudo ln -s /snap/bin/certbot /usr/bin/certbot
sudo nano /etc/nginx/sites-available/your_domain
 in your config nginx /etc/nginx/sites-available/your_domain add: 
...
server_name your_domain www.your_domain;
...
sudo nginx -t
sudo systemctl reload nginx
sudo ufw status
sudo ufw allow 'Nginx Full'
sudo ufw delete allow 'Nginx HTTP'
sudo ufw status

sudo certbot --nginx -d your_domain -d your_domain
sudo certbot renew --dry-run
```


## install php
```bash
sudo apt install software-properties-common
sudo add-apt-repository ppa:ondrej/php -y
sudo apt install php7.4
sudo apt install php7.4-{cli,common,curl,zip,gd,mysql,xml,mbstring,json,intl}

```


