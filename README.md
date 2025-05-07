# zabbix-tele
using nginx + postgres

# Install Docker
sudo dnf install -y dnf-plugins-core
sudo dnf config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
sudo dnf install -y docker-ce docker-ce-cli containerd.io

# Enable dan jalankan Docker
sudo systemctl enable --now docker

# Install Docker Compose
sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose

# Cek versi
docker-compose --version

#Buat folder di centos 9
mkdir ~/zabbix-docker
cd ~/zabbix-docker

#Jalankan Zabbix
docker-compose up -d
