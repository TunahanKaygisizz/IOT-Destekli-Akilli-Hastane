# 🏥 IoT Destekli Akıllı Hastane Bilgisayar Ağı Projesi

Marmara Üniversitesi Teknoloji Fakültesi, Bilgisayar Mühendisliği bölümü **Bilgisayar Ağlarına Giriş** dersi kapsamında geliştirilmiş, kapsamlı bir akıllı hastane ağı simülasyonudur. Proje, Cisco Packet Tracer kullanılarak tasarlanmış olup; ağ güvenliği, yüksek performans, IoT (Nesnelerin İnterneti) entegrasyonu ve VLAN tabanlı izolasyon prensiplerine dayanmaktadır.

## 📌 Proje Özeti
Bu proje, modern bir hastane ortamı için tasarlanmış IoT destekli ve segmentlere ayrılmış bir ağ altyapısını simüle eder. Ağın merkezinde yer alan Layer-3 Switch, bölümler arası trafiği yönetirken, dış dünya ile iletişim bir Router ve Firewall (Güvenlik Duvarı) üzerinden sağlanmaktadır. Proje, hem kablolu (fiber/bakır) hem de kablosuz bağlantı modellerini bir arada sunarak esnek ve güvenli bir sağlık bilişim altyapısı modeli oluşturur.

## 🚀 Öne Çıkan Özellikler
* **VLAN İzolasyonu:** Hastane birimleri (Ameliyathane, Acil Servis, Hasta Odaları vb.) mantıksal olarak birbirinden ayrılarak ağ performansı ve güvenlik artırılmıştır.
* **Inter-VLAN Routing:** Farklı ağların birbiriyle iletişimi merkezi bir Layer-3 Switch üzerinden sağlanmaktadır.
* **IoT Entegrasyonu:** Hasta odaları ve ameliyathanedeki akıllı lamba, fan ve termostat gibi IoT cihazları ağa entegre edilmiş ve merkezi/otomatik kontrol edilebilir hale getirilmiştir.
* **Kablosuz Ağ (WLAN):** Misafirler ve mobil sağlık personelleri için WPA2 şifrelemeli kablosuz erişim noktaları (Access Point) konumlandırılmıştır.
* **Güvenlik (Firewall):** Dış ağdan (İnternet) gelebilecek tehditlere karşı Router arkasında Firewall yapılandırması kullanılmıştır.
* **Merkezi Veri Yönetimi:** DNS ve HTTP sunucularını barındıran izole bir sunucu tarlası mevcuttur.

## 🏗️ Ağ Topolojisi ve IP Planlaması

Projede gelişmiş bir yıldız (star) topolojisi kullanılmış olup, IP adreslemesi aşağıdaki gibi yapılandırılmıştır:

| VLAN ID | Bölüm Adı | Ağ Adresi | Ağ Geçidi (Gateway) | Alt Ağ Maskesi |
| :---: | :--- | :--- | :--- | :--- |
| **VLAN 10** | 💻 Sunucu Tarlası | `192.168.10.0` | `192.168.10.1` | `255.255.255.0` |
| **VLAN 20** | 🩺 Doktorlar | `192.168.20.0` | `192.168.20.1` | `255.255.255.0` |
| **VLAN 30** | 🛏️ Hasta Odası | `192.168.30.0` | `192.168.30.1` | `255.255.255.0` |
| **VLAN 40** | ⚕️ Ameliyathane | `192.168.40.0` | `192.168.40.1` | `255.255.255.0` |
| **VLAN 1** | 📱 Misafir Ağı | `192.168.1.0` | `192.168.1.1` | `255.255.255.0` |
| **VLAN 70** | 🚑 Acil Servis | `192.168.70.0` | `192.168.70.1` | `255.255.255.0` |
| **VLAN 80** | 🎥 Güvenlik Odası| `192.168.80.0` | `192.168.80.1` | `255.255.255.0` |

### 🛠️ Kullanılan Teknolojiler ve Donanımlar
* **Araç:** Cisco Packet Tracer
* **Cihazlar:** Cisco 3560 (Layer-3 Switch), Cisco 2960 (Access Switches), Core Router, ASA Firewall, Wireless Access Points, Sunucular (HTTP, DNS).
* **Fiziksel Bağlantılar:** Ana omurga iletişiminde **Fiber Optik**, uç cihaz bağlantılarında **Bakır (Copper)** kablolar kullanılmıştır.

## 📂 Kurulum ve Kullanım
1. Bu depoyu yerel bilgisayarınıza klonlayın:
   ```bash
   git clone [https://github.com/KULLANICI_ADINIZ/hastane-agi-projesi.git](https://github.com/KULLANICI_ADINIZ/hastane-agi-projesi.git)
