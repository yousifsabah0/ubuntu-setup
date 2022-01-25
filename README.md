# Ubuntu setup

My setup for backend development in Ubuntu.

## System configuration

1. Patching.

```bash
sudo apt-get update -y
sudo apt-get upgrade -y
# Remove packages that not needed
sudo apt-get autoremove -y
sudo apt-get autoclean -y
```

2. Build tools and languages

```bash
sudo apt-get install build-essential checkinstall libreadline-gplv2-dev libncursesw5-dev libssl-dev libsqlite3-dev tk-dev libgdbm-dev libc6-dev libbz2-dev libssl-dev libcurl4-gnutls-dev libexpat1-dev curl gettext cmake gcc -y
```

3. Enable minimize on click.

```bash
gsettings set org.gnome.shell.extensions.dash-to-dock click-action 'minimize'
```

4. Install media codecs and gnome tweaks.

```bash
sudo apt-get install ubuntu-restricted-extras gnome-tweaks -y
```

5. Install Git.

```bash
- cd /tmp
- curl -o git.tar.gz https://mirrors.edge.kernel.org/pub/software/scm/git/git-2.34.1.tar.xz
- cd git-2.33.1/
- sudo make prefix=/usr/local all && sudo make prefix=/usr/local install

# Configure git
- git config --global user.name "Your name"
- git config --global user.email "Your email"
- git config credential.helper store
```

6. Install Node.js

```bash
curl -fsSL https://deb.nodesource.com/setup_17.x | sudo -E bash -
```

Optional install global packages and update npm.

```bash
npm i -g npm@latest pm2 nodemon license gitignore dockerignore typescript commitizen
```

7. Install Nginx:

```bash
- sudo apt-get update -y
- sudo apt-get install nginx -y
- sudo systemctl enable nginx
```

8. Install Docker and Docker Compose.

- Docker:

```bash
# Remove old version if found
- sudo apt-get remove docker docker-engine docker.io containerd runc

- sudo apt-get update -y
- sudo apt-get install \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
- curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
- echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
- sudo apt-get update -y && sudo apt-get install docker-ce docker-ce-cli containerd.io

- docker version
```

- Docker compose

```bash
- sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
- sudo chmod +x /usr/local/bin/docker-compose
- docker-compose --version
```

9. Install MySQL
```bash
- sudo apt-get update -y
- sudo apt-get install mysql-server -y
- sudo mysql_secure_installation
```

10. Install MongoDB

```bash
- wget -qO - https://www.mongodb.org/static/pgp/server-5.0.asc | sudo apt-key add -
- echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu focal/mongodb-org/5.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-5.0.list
- sudo apt-get update -y && sudo apt-get install -y mongodb-org

# Enable mongodb service
- sudo systemctl enable mongod

# To run mongodb
- `mongod` or `mongosh`

```

11. Install PostgreSQL

```bash
- sudo sh -c 'echo "deb http://apt.postgresql.org/pub/repos/apt $(lsb_release -cs)-pgdg main" > /etc/apt/sources.list.d/pgdg.list'

- wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add -

- sudo apt-get update -y && sudo apt-get -y install postgresql

```

12. Install Go:
- Download: [GoLang](https://go.dev/dl/go1.17.6.linux-amd64.tar.gz)
- After installation:
```bash
- rm -rf /usr/local/go && tar -C /usr/local -xzf go1.17.6.linux-amd64.tar.gz
- export PATH=$PATH:/usr/local/go/bin
- go version
```

13. Install softwares:

- [vscode](https://snapcraft.io/code)
- [Postman](https://snapcraft.io/postman)
- [Brave](https://snapcraft.io/brave)
- [Telegram](https://snapcraft.io/telegram-desktop)
- [Slack](https://snapcraft.io/slack)
- [MySQL Workbeanch](https://dev.mysql.com/downloads/workbench/)
- [Robo3t](https://snapcraft.io/robo3t-snap)
- [Spotify](https://snapcraft.io/spotify)
- [Sublime Text](https://snapcraft.io/sublime-text)
- [LibreOffice](https://snapcraft.io/libreoffice)

Additional:

```bash
sudo apt-get install vlc gparted filezilla -y
```
