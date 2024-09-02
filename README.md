Honeypot Uygulaması
Bu proje, siber güvenlik amacıyla geliştirilmiş bir honeypot uygulamasıdır. Honeypot'lar, siber saldırganları yanıltmak, davranışlarını analiz etmek ve potansiyel tehditleri tespit etmek için kullanılan etkili araçlardır. Bu uygulama, sahte veriler sunarak saldırganları kandırır, rastgele hata mesajları gösterir ve bilinçli olarak erişim hızını yavaşlatarak saldırganların dikkatini çeker. Ayrıca, tüm bu işlemler sırasında saldırganların hareketlerini kaydeder ve bu kayıtları analiz ederek güvenlik stratejilerinizi güçlendirmenize yardımcı olur.

📋 Özellikler
Sahte Dosyalar Üretme

Veeam Yedekleme Dosyaları: Sahte yedekleme dosyaları (.vbk).
PDF Şirket Raporları: Sahte şirket raporlarını içeren PDF dosyaları.
Excel Çalışan Verileri: Sahte çalışan bilgilerini içeren Excel dosyaları.
Word Şirket Bilgileri: Sahte şirket bilgilerini içeren Word belgeleri.
Rastgele Hata Mesajları

Saldırganları gerçek bir sistemdeymiş gibi hissettirmek için rastgele hata mesajları.
Yavaşlatma Mekanizması

Saldırganın dikkatini dağıtmak ve onları daha uzun süre sistemde tutmak için bilinçli olarak erişimlerin yavaşlatılması.
Loglama ve İzleme

Saldırganların hareketlerini kaydederek analiz edilebilir veriler sağlar.
🚀 Kurulum
Honeypot uygulamasını kurmak ve çalıştırmak için aşağıdaki adımları izleyin.

git clone https://github.com/username/honeypot-application.git
cd honeypot-application

Adım 2: Gerekli Paketleri Yükleyin
Gerekli Python paketlerini yüklemek için:

pip install flask faker pandas fpdf python-docx

Adım 3: Uygulamayı Çalıştırın
Aşağıdaki komutla uygulamayı başlatın:
python honeypot.py

Uygulama, varsayılan olarak http://127.0.0.1:5000/ adresinde çalışacaktır. Tarayıcınızda bu adresi açarak uygulamanın ana sayfasına erişebilir ve sahte dosyalarla etkileşime geçebilirsiniz.
-------------------------------------------------------------------------------------------------

💻 Kullanım
Bu honeypot uygulaması, saldırganların ilgisini çekmek için çeşitli sahte veriler sunar. Saldırganlar bu dosyalara erişmeye çalıştıklarında, sistemdeki gerçek verileri bulduklarına inandırılırlar. Ancak, tüm bu işlemler sırasında saldırganların hareketleri kaydedilir.

Sahte Dosyalar
Aşağıdaki URL'ler üzerinden sahte dosyalara erişebilirsiniz:

Ana Sayfa: http://127.0.0.1:5000/

Veeam Yedekleme Dosyaları: http://127.0.0.1:5000/veeam

Şirket Raporu (PDF): http://127.0.0.1:5000/pdf

Çalışan Verileri (Excel): http://127.0.0.1:5000/excel

Şirket Bilgileri (Word): http://127.0.0.1:5000/word

Rastgele Hata Mesajları ve Yavaşlatma
Bu honeypot, saldırganları daha fazla yanıltmak ve onların sistemde daha uzun süre kalmasını sağlamak için rastgele hata mesajları gösterir ve bilinçli olarak dosya erişimlerini yavaşlatır. Bu sayede, saldırganın sistemdeki hareketlerini daha detaylı bir şekilde izleyebilir ve analiz edebilirsiniz.

-----------
# Rastgele olarak sahte hata mesajı gönderme
if random.choice([True, False]):
    logging.warning(f"Sahte hata mesajı gösterildi: {request.remote_addr}")
    abort(500, description="Sunucu Hatası: Erişim sırasında bir sorun oluştu.")

# Rastgele dosya erişimini yavaşlatma
if random.choice([True, False]):
    logging.info(f"Erişim yavaşlatıldı: {request.remote_addr}")
    time.sleep(random.uniform(2, 5))  # 2 ile 5 saniye arasında bekleme
-----------

Loglama ve İzleme
Uygulama, saldırganların sistem üzerindeki tüm hareketlerini loglar. Bu loglar, saldırganların hangi dosyalara erişmeye çalıştığını, hangi hata mesajlarını gördüğünü ve hangi yavaşlatma işlemlerine maruz kaldığını içerir. Tüm bu veriler honeypot.log dosyasında saklanır ve analiz için kullanılabilir.

-----------
logging.info(f"Erişim kaydedildi: {request.remote_addr} tarafından")
------------

🔒 Güvenlik ve İzolasyon
Honeypot'unuzu kurarken ve çalıştırırken aşağıdaki güvenlik önlemlerini almanız önerilir:

Ağ İzolasyonu
VLAN veya Ayrı Fiziksel Ağ: Honeypot'u şirket ağınızdan izole etmek için ayrı bir VLAN veya tamamen ayrı bir fiziksel ağ kullanabilirsiniz. Bu, honeypot'un diğer kritik sistemlerle iletişime geçmesini engeller ve olası riskleri minimize eder.

DMZ (Demilitarized Zone): Honeypot'u bir DMZ içinde çalıştırarak, şirketin iç ağından tamamen izole edebilir ve dış dünyadan gelen saldırıları daha güvenli bir şekilde yönetebilirsiniz.

Güvenlik Duvarı Kuralları
Erişim Kısıtlamaları: Honeypot'a yalnızca belirli IP adreslerinden erişime izin verin ve diğer trafiği engelleyin. Bu, sadece yetkili kişilerin honeypot'a erişmesini sağlar.

Giden Trafik Kontrolü: Honeypot'un giden trafiğini kısıtlayarak, saldırganların iç ağdaki diğer sistemlere erişimini engelleyebilirsiniz.

Sanallaştırma ve DMZ Kullanımı
VMware ESXi: VMware ESXi gibi bir sanallaştırma platformu üzerinde sanal ağlar (vSwitch) kullanarak honeypot'u izole edebilir ve fiziksel ağdan bağımsız olarak güvenli bir sanal ortam oluşturabilirsiniz.

DMZ: Honeypot'u bir DMZ'de konuşlandırarak, güvenlik duvarı kuralları ile iç ağdan izole edebilir ve dış saldırılara karşı koruma sağlayabilirsiniz.

📄 Lisans
Bu proje MIT Lisansı altında lisanslanmıştır. Bu lisans, yazılımın özgürce kullanılmasını, değiştirilmesini ve dağıtılmasını sağlar.


