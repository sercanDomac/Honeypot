Honeypot Uygulaması
Bu proje, siber güvenlik amaçlı bir honeypot uygulamasıdır. Honeypot, saldırganların ilgisini çekmek, onları analiz etmek ve siber saldırıları tespit etmek amacıyla tasarlanmış sahte bir sistemdir. Bu uygulama, sahte dosyalar sunarak saldırganları yanıltır, rastgele hata mesajları gösterir ve erişimlerini yavaşlatarak daha fazla zaman harcamalarını sağlar.

Özellikler
Sahte Dosyalar Üretme:

Uygulama, saldırganların ilgisini çekmek için çeşitli sahte dosyalar oluşturur:
Veeam Yedekleme Dosyaları (.vbk): Sahte yedekleme dosyaları.
PDF Şirket Raporları: Sahte şirket raporları içeren PDF dosyaları.
Excel Çalışan Verileri: Sahte çalışan bilgilerini içeren Excel dosyaları.
Word Şirket Bilgileri: Şirket bilgilerini içeren sahte Word belgeleri.
Rastgele Hata Mesajları:

Saldırganları yanıltmak için erişim sırasında rastgele hata mesajları gösterir. Bu, saldırganın gerçek bir sistemde hatalarla karşılaştığını düşünmesine neden olur.
Bilerek Yavaşlatma:

Uygulama, saldırganın erişimlerini yavaşlatmak için belirli durumlarda gecikme ekler. Bu, saldırganın sistemde daha fazla zaman harcamasını sağlar ve güvenlik ekibine saldırıyı analiz etmek için daha fazla zaman tanır.
Loglama ve İzleme:

Uygulama, saldırganın tüm hareketlerini kaydeder. Bu loglar, saldırganın hangi dosyalara erişmeye çalıştığını, hangi hata mesajlarını gördüğünü ve hangi yavaşlatma işlemlerine maruz kaldığını içerir. Bu bilgiler, saldırganların davranışlarını analiz etmek ve güvenlik stratejilerini geliştirmek için kullanılır.

Kurulum
1. Gereksinimleri Yükleyin
Proje Python 3.x ile geliştirilmiştir. Aşağıdaki komutlarla gerekli Python paketlerini yükleyebilirsiniz:

bash
Kodu kopyala
pip install flask faker pandas fpdf python-docx
2. Uygulamayı Çalıştırın
Aşağıdaki komut ile uygulamayı başlatabilirsiniz:

bash
Kodu kopyala
python honeypot.py
Uygulama, varsayılan olarak http://127.0.0.1:5000/ adresinde çalışacaktır.

Kullanım
Uygulama, saldırganların dikkatini çekmek ve onları yanıltmak amacıyla sahte veriler sunar. Aşağıdaki URL'ler üzerinden bu sahte verilere erişebilirsiniz:

Ana Sayfa: http://127.0.0.1:5000/ - Uygulamanın ana sayfası, mevcut sahte dosyalara bağlantılar sunar.
Veeam Yedekleme Dosyaları: http://127.0.0.1:5000/veeam - Sahte Veeam yedekleme dosyalarına erişim.
Şirket Raporu (PDF): http://127.0.0.1:5000/pdf - Sahte şirket raporunu içeren PDF dosyasına erişim.
Çalışan Verileri (Excel): http://127.0.0.1:5000/excel - Sahte çalışan verilerini içeren Excel dosyasına erişim.
Şirket Bilgileri (Word): http://127.0.0.1:5000/word - Sahte şirket bilgilerini içeren Word belgesine erişim.
Güvenlik Önerileri
Honeypot uygulamanızın güvenli bir şekilde çalışmasını sağlamak için şu adımları uygulayın:

1. İzolasyon
Honeypot'u şirket ağınızdan izole etmek, saldırganların gerçek sistemlere erişmesini engellemek için kritiktir. Honeypot'u izole etmek için şu yöntemleri kullanabilirsiniz:

VLAN veya Ayrı Fiziksel Ağ: Honeypot'u ayrı bir VLAN veya tamamen ayrı bir fiziksel ağ üzerinde yapılandırarak şirket ağından izole edebilirsiniz.
DMZ (Demilitarized Zone): Honeypot'u bir DMZ içinde çalıştırarak, şirketin iç ağından izole edebilirsiniz.
2. Güvenlik Duvarı
Erişim Kısıtlamaları: Honeypot'a sadece belirli IP adreslerinden erişime izin verin ve diğer trafiği engelleyin.
Giden Trafik Kontrolü: Honeypot'un giden trafiğini kısıtlayarak, saldırganların iç ağa erişimini engelleyin.
3. Sanallaştırma
VMware ESXi: VMware ESXi üzerinde sanal ağlar (vSwitch) kullanarak honeypot'u izole edebilirsiniz. Bu, fiziksel ağdan bağımsız olarak sanal bir ağ içinde çalışmasını sağlar.
