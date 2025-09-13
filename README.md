#  Docker compose hazır Redis Sentinel ve Insight kurmak 
---
Projeyi bilgisayarınıza indirip, bir dizine çıkarıp, docker compose up komutu ile 1 master, 1 Replica, 3 Redis Sentinel ve Redis Insight web arayüzü (Hazelcast'in Management Center'ı ile benzer işlevdeki web yönetim arayüzü) ayağa kaldırabilirsiniz.

```
$ tree .
.
├── docker-compose.yml
├── redis-master.conf
├── redis-replica.conf
├── sentinel1.conf
├── sentinel2.conf
└── sentinel3.conf
 
0 directories, 6 files
```
http://localhost:5540/ adresinden Redis Insight uygulamasına erişebilirsiniz.
<img width="1910" height="1021" alt="image2025-9-13_23-16-35" src="https://github.com/user-attachments/assets/c060bf66-c738-4a2f-b974-01f849790514" />

İlk giriş ekranından sonra, aşağıdaki şekilde direk olarak redis'e bağlanabilirsiniz.
<img width="1840" height="879" alt="image2025-9-13_23-26-18" src="https://github.com/user-attachments/assets/75a83d69-52c4-4ff6-b7f6-5fd842289c73" />
<img width="1422" height="289" alt="image2025-9-13_23-26-52" src="https://github.com/user-attachments/assets/16f578b9-4ddb-4048-8a8c-73feaa78f025" />
<img width="1917" height="919" alt="image2025-9-13_23-27-16" src="https://github.com/user-attachments/assets/37cd3167-b680-4350-b58e-5140adbf23a9" />


Direk bağlantı haricinde aynı docker compose içerisinde yer aldığı için servis adıyla Redis Sentinel'e de bağlantı sağlanabilir. (Şu linkte yazan durumlardan ötürü dışarıdan direk Sentinel'e bağlantıyı başaramadım https://redis.io/docs/latest/operate/oss_and_stack/management/sentinel/#sentinel-docker-nat-and-possible-issues).
<img width="1379" height="800" alt="image2025-9-13_23-18-38" src="https://github.com/user-attachments/assets/66f962cd-dbb4-4ea6-bf83-e76a1cd659ec" />

Dikkat edilmesi gereken, bağlanılacak host bilgisini sentinel1 (docker servis adı) olarak vermektir.
<img width="842" height="641" alt="image2025-9-13_23-18-57" src="https://github.com/user-attachments/assets/1c79ff21-9bb6-4057-a4c1-8bc09227e724" />

Daha sonra gelecek ekrandan seçimi yapıp Add Primary Group butonuna basarak bağlantıyı tamamlayabilirsiniz.
<img width="1428" height="891" alt="image2025-9-13_23-20-3" src="https://github.com/user-attachments/assets/a46e61d6-19fa-41d6-baf1-7ab78ce24e4a" />



Linkler:
 - https://redis.io/docs/latest/operate/oss_and_stack/install/install-stack/docker/
 - https://redis.io/docs/latest/operate/oss_and_stack/management/sentinel/#sentinel-docker-nat-and-possible-issues
