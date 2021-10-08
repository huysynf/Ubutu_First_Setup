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

```
# php 
``` bash 
sudo apt install php -y

sudo apt install composer nodejs -y

sudo apt install php-mysql php-gd openssl php-common php-curl php-json php-mbstring php-mysql php-xml php-zip

```

# install conky
