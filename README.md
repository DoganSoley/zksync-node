# Zksync Full Node Sistem Gereksinimleri
32GB RAM 

500GB SSD 

300-350GB SSD'de de çalışıyor ama kurabiliyorsanız 500GB'a kurun

Ben sunucu olarak hetzner'den ax42'ye kurdum ücreti saatlik olarak kestiği için 2-3 günlük bi kullanımda 3-5$ gibi birşeye denk gelecek işim bittiğinde sunucuyu sileceğim.

kullandığım sunucu link : https://www.hetzner.com/dedicated-rootserver/ax42/

Sunucuya terminalden bağlandıktan sonra sırasıyla :

Docker Kurulumu
```
sudo apt update
```
```
sudo apt install docker.io
```
```
sudo systemctl status docker
```
```
docker --version
```

Docker Compose Kurulumu
```
sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
```
```
sudo chmod +x /usr/local/bin/docker-compose
```
```
docker-compose --version
```
