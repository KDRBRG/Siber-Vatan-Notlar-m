# Siber-Vatan-Notlar-m
# 🛡️ Siber Vatan Teknik Eğitim ve Sızma Testi Laboratuvar Notları

Bu depo (repository), Siber Vatan programı kapsamında gerçekleştirilen yüz yüze eğitimleri, sistem ve ağ tarama pratiklerini, web uygulama güvenliği çalışmalarını, Metasploitable2 ve Windows XP sızma testi laboratuvar raporlarını ve kamp seçme sınavı/CTF hazırlık notlarını tek bir çatı altında toplamaktadır.

---

## 📂 Depo İçeriği ve Hiyerarşisi

### 🐧 Bölüm 1: Linux Temelleri ve İşletim Sistemi Güvenliği
* **Linux Felsefesi ve Mimarisi:** Açık kaynak dünyası, kararlılık, şeffaflık ve güvenlik altyapısı.
* **Ağ Servisleri Yapılandırması:** `ssh-keygen` ile parolasız güvenli bağlantı mimarisi, SSH port manipülasyonu ve `/etc/ssh/sshd_config` sıkılaştırma adımları.

### 🔍 Bölüm 2: Bilgi Toplama ve OSINT (Açık Kaynak İstihbaratı)
* **Gelişmiş Arama:** Google Dorking yöntemleri, Google Hacking Database (GHDB) entegrasyonu ve sızdırılmış veri tabanı analizleri.
* **Altyapı ve Alan Adı Keşfi:** `subfinder`, `web-check.xyz`, `urlscan.io`, `Wappalyzer` ve `SecurityTrails` ile pasif/aktif keşif.
* **IoT ve İstihbarat Arama Motorları:** `Shodan`, `Censys` ve `Insecam` kullanarak internete açık zafiyetli cihazların (kamera, yazıcı vb.) tespiti.
* **DNS ve Ağ Sorguları:** `nslookup`, `whois`, `traceroute`, `dnschecker.org` ve `viewdns.info` araçları.

### ⚡ Bölüm 3: Ağ Tarama ve Güvenlik Duvarı Atlatma (Nmap)
* **Canlı Cihaz Tespiti:** `netdiscover` ve `Fing` ile yerel ağ (LAN) analizi.
* **Nmap Parametreleri:** Agresif (`-A`), Hızlı (`-F`), Versiyon (`-sV`), OS Tespiti (`-O`) ve Tüm Port (`-p-`) taramaları.
* **IDS/Firewall Bypass:** Paket parçalama (`-f`), Sahte IP ile yemleme (`-D`), Tarama hızı (`-T0-5`) optimizasyonu ve Tor entegrasyonu.

### 💥 Bölüm 4: Sistem Sızma Testleri (Metasploit Framework)
* **Metasploit Konsol Yönetimi:** Modül arama (`search`), hedef tespiti (`check`), parametre yönetimi (`options`) ve sömürü (`exploit`/`run`).
* **Meterpreter Oturumu ve Post-Exploitation:**
  * Süreç taşıma (`migrate`), ayrıcalık kontrolü (`getprivs`), arka plana alma (`background`).
  * Dosya arama (`search -f`), sisteme dosya aktarımı (`upload`/`download`), süreç sonlandırma (`kill`).
* **Zararlı Yazılım Dağıtımı:** `msfvenom` ile reverse_tcp payload üretimi ve Python HTTP sunucusu üzerinden kurbana servis edilmesi.

### 🌐 Bölüm 5: Web Uygulama Güvenliği (OWASP Top 10)
* **SQL Injection (SQLi):** Giriş formları üzerinde `' OR 1=1#` mantıksal sorgusu ile kimlik doğrulama bypass (Auth Bypass) tekniği.
* **Path Traversal & LFI:** Web parametreleri üzerinden dizin atlatma yapılarak `/etc/passwd` gibi hassas sistem dosyalarının okunması.
* **Cross-Site Scripting (XSS):** `<script>alert(1)</script>` ile zafiyet tespiti, HTML olay tetikleyicileri (`" onmouseover="...`) ile filtre atlatma (Bypass) ve **BeEF-XSS** (Browser Exploitation Framework) tarayıcı sömürü süreçleri.

### 🚩 Bölüm 6: CTF (Capture The Flag) & Kamp Seçme Sınavı Hazırlığı
* **Forensics (Adli Bilişim):** `StegOnline` ile görsel steganografi analizi, `apackets.com` üzerinden online PCAP/paket incelemesi, `VirusTotal` topluluk analizleri ve `OpenTheFile` ile bilinmeyen uzantı tespiti.
* **Kriptoloji & Şifre Çözme:** `CyberChef` akış şemaları, `dcode.fr` antik/modern algoritma çözücüleri, `JWT.io` token analizi ve ses dosyalarından *Mors Kodu* çözümü.
* **Parola Kırma:** `CUPP` ile kişiselleştirilmiş kelime listesi (wordlist) oluşturma, `1337` (Leet) alfabesi dönüşümleri ve `CrackStation` rainbow table sorgulamaları.

---

## 📊 Örnek Laboratuvar Raporları Özetleri

Depo içerisinde yer alan gerçek zamanlı sızma testi laboratuvarlarına ait teknik adımlar:

### 1. Metasploitable 2 Laboratuvar Raporu
* **Bulgu:** Hedef makinedeki Port 21 (vsFTPd 2.3.4) servisinin zafiyet barındırdığı Nmap ve Metasploit adımlarıyla doğrulanmıştır.
* **Sömürü:** `exploit/unix/ftp/vsftpd_234_backdoor` modülü konfigüre edilerek `root` yetkisinde arka kapı (backdoor) tetiklenmiş ve tam erişim sağlanmıştır.

### 2. Windows XP Sızma Testi Raporu
* **Keşif:** `netdiscover` ile yerel ağda canlı olan kurban IP adresi saptanmış, ardından Nmap ile Port 445 (SMB) servisinin açık olduğu doğrulanmıştır.
* **Sömürü:** `exploit/windows/smb/ms08_067_netapi` modülü kullanılarak hedef sistem üzerinde `NT AUTHORITY\SYSTEM` (en yüksek yetki) seviyesinde Meterpreter oturumu elde edilmiştir.

---

## 🛠️ Kullanılan Teknolojiler ve Araçlar

* **İşletim Sistemleri:** Kali Linux, Lubuntu, Windows XP, Metasploitable 2
* **Sanallaştırma:** Oracle VM VirtualBox
* **Güvenlik Araçları:** Nmap, Metasploit Framework, MSFVenom, Nessus Vulnerability Scanner, BeEF

---

## 🔐 Güvenlik ve Gizlilik Hakkında Önemli Not

Siber güvenlik prensipleri gereğince, laboratuvar çalışmaları veya CTF çözümleri sırasında analiz edilen **hiçbir hassas veri, kurumsal bilgi veya kişisel anahtar bu depoda açık bir şekilde paylaşılmamıştır.** Paylaşılan tüm çıktılar ve raporlar anonimleştirilmiş laboratuvar verilerinden oluşmaktadır.

---

## ⚠️ Yasal Uyarı / Disclaimer

Bu depoda yer alan tüm komutlar, teknikler, araçlar ve raporlar **Siber Vatan** eğitimi kapsamında tamamen **yasal, izole ve laboratuvar ortamlarında** test edilmiştir. Bu bilgilerin yetkisiz veya izinsiz sistemler üzerinde kullanılması yasal sorumluluk doğurur ve suç teşkil eder. Eğitim ve savunma odaklı (White Hat) geliştirilmiştir.
