## Konu  
docker mongo imajini kullanarak local makinede mondodb'ye baglanmak.

## Adimlar
1. mongo imajini dockerhub'dan cekiyoruz.
```bash
$ docker pull mongo
Using default tag: latest
latest: Pulling from library/mongo
693502eb7dfb: Pull complete
5a29f630b22e: Pull complete
328ac2c79d69: Pull complete
d628f74e0e97: Pull complete
50753de132e0: Pull complete
14fee098631b: Pull complete
7a4c3bdc1525: Pull complete
afe0970b86ae: Pull complete
b3fbca93d344: Pull complete
Digest: sha256:3d4537f996bc28a6c6b694e22f46316c0629703420de60e8f46285ce1fe69260
Status: Downloaded newer image for mongo:latest
```

2. docker run komutu ile bir tane konteynir calistiriyoruz. 
```bash
$ docker run -d  --name mongo_1 -p 27017:27017 mongo
```
### parametrelerin aciklamalari  
* -d               : calistirdigimiz konteynir daemon olarak calisacak. bu opsiyonu girmezsek koytenirimiz calistiginda, otomatik olarak mongo loglarini gorecegiz.  
* --name mongo_1   : calistiracagimiz konteynira kullanici dostu bir isim vermek icin.  
* -p 27017:27017   : mongo_1 ismini verdigimiz konteynir default olarak 27017 portunu dinleyecek sekilde ayarlanmis. bu komut ile lokal makinemizdeki 27017 portuna gelen istekleri calistirdigimiz konteynira yonlendirmis oluyoruz.  

3. robomongo kullanarak mongodb'ye baglanabilirsiniz. baglanmak icin adres kismina 127.0.0.1:27017 yazmaniz yeterli.  

4. (opsiyonel) calistirdigimiz mongo konteynirindaki log'lari takip etmek icin:  
```bash
$ docker logs --follow mongo_1
```
    