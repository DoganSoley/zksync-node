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

Git Kurulumu
```
sudo apt install git
```
```
git clone https://github.com/matter-labs/zksync-era.git
```
Kurulum bittikten sonra dosya dizinine gidiyoruz
```
cd zksync-era/docs/guides/external-node
```
```
cd docker-compose-examples
```

Daha sonra nodeyi başlatıyoruz
```
docker-compose -f mainnet-external-node-docker-compose.yml up -d
```
Bu ekranda biraz bekletebilir.

daha sonra 

```
cd
```
yazıp ana dizine dönüyoruz 
```
nano zksync-era/docs/guides/external-node/docker-compose-examples/mainnet-external-node-docker-compose.yml
```
Bu kodu yazıktan sonra karşısına çıkan ekranda klavyenin yön tuşlarıyla aşağıya inip fotoğrafta görünen ports : kısmını bu şekilde düzenleyin
sizde başında 127.0.0.1 yazıyordur onları silip fotoğrafdaki gibi yapın.

![nodezksync](https://github.com/DoganSoley/zksync-node/assets/110679236/67b9cfd7-fb37-43de-88c3-a310a993d9f3)

kaydedip çıkmak için ise CTRL + X daha sonra Y yazıp ENTER yapın.

Daha sonra tekrar zksync dosya dizinine gidip nodeyi durdurup tekrar çalıştırın sırasıyla :

```
cd zksync-era/docs/guides/external-node
```
```
cd docker-compose-examples
```
```
docker-compose -f mainnet-external-node-docker-compose.yml down
```
```
docker-compose -f mainnet-external-node-docker-compose.yml up -d
```
Eğerki bunu yaparken "Unhealty" gibi bir hata alırsanız sonu "down" ile biten kodu tekrar yazıp durdurun "up -d" ile biten kod ile tekrar çalıştırın.
hata vermeyene kadar durdur başlat yaparak deneyin.

En son bittikten sonra bu kod ile logları kontrol edebilirsiniz :
```
docker logs -f --tail 100 docker-compose-examples_external-node_1
```

Sync olması ortalama 10-15 saat sürüyor loglar aktığı sürece bir problem yok demektir en son sync olduktan sonra bu şekilde görünecek :

![image](https://github.com/DoganSoley/zksync-node/assets/110679236/1968088f-2079-44a4-a129-087e12949db6)

