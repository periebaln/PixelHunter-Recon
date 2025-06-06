# PixelHunter Recon

## Takım Üyeleri
- Begüm Akyüz 24**05

## Proje Açıklaması
PixelHunter Recon, yüklenen fotoğrafların EXIF verilerini analiz ederek varsa GPS konumlarını haritada gösteren ve ters görsel arama yaparak benzer fotoğrafları bulan bir OSINT aracıdır.

## Hedefler
- Fotoğrafların EXIF bilgilerini çıkarmak.
- GPS bilgisi varsa harita üzerinde konum göstermek.
- Ters görsel arama ile fotoğrafın diğer versiyonlarını bulmak.

## Projede Kullanılan Temel Teknoloji ve Araçlar

    EXIF Veri Çıkarma ve Analizi:
        ExifTool: Görüntülerdeki kamera ayarları, çekim tarihi/saati ve GPS koordinatları gibi detaylı meta verileri çıkarmak ve düzenlemek için kullanılan komut satırı tabanlı güçlü bir araç.
        Pillow (Python Kütüphanesi): Genel görüntü işleme ve EXIF verilerine erişim için kullanılan bir Python kütüphanesi.
        exifread (Python Kütüphanesi): Özellikle GPS verilerini daha kolay bir şekilde çıkarmak ve ondalık dereceye dönüştürmek için tasarlanmış hafif bir Python kütüphanesi.
        Çevrimiçi EXIF Görüntüleyiciler (ExifEditor.io, FotoForensics): Hızlı kontrol ve manipülasyon tespiti için kullanılan web tabanlı araçlar.

    Ters Görüntü Arama:
        Genel Arama Motorları (Google Görseller, TinEye, Yandex Görseller, Bing Görsel Arama): Görüntünün kökenini, kopyalarını ve benzer içerikleri bulmak için kullanılan yaygın web tabanlı arama motorları.
        PimEyes: Gelişmiş yüz tanıma teknolojisiyle internette belirli bir kişinin yüzünü bulmaya odaklanmış uzmanlaşmış bir araç.
        GeoSpy: Özellikle GPS verisi olmayan fotoğraflardan görüntü desenleri ve çevresel ipuçları sayesinde konum tespiti yapabilen yapay zeka destekli bir araç.
        Programatik API'ler (SerpApi, Bing Görüntü Arama API'si): Büyük ölçekli ve otomatik ters görüntü arama sorguları için güvenilir ve yapılandırılmış sonuçlar sağlayan ticari API hizmetleri.
        Görüntü Gömme ve Benzerlik Arama (Python, FAISS): Derin öğrenme modelleri (örn. VGG16) kullanarak görüntüleri sayısal vektörlere dönüştürüp, bu vektörler arasında hızlı benzerlik araması yapmak için kullanılan ileri düzey teknik ve kütüphaneler (FAISS).

    Coğrafi Veri Görselleştirme:
        Folium (Python Kütüphanesi): Çıkarılan GPS verilerini etkileşimli web haritaları üzerinde görselleştirmek için kullanılan bir Python kütüphanesi.
        Kepler.gl: Büyük ölçekli coğrafi veri kümelerini (milyonlarca nokta) yüksek performansla (WebGL destekli) 2D ve 3D olarak görselleştirmek için kullanılan bir platform.
        Datashader: Çok büyük coğrafi veri kümelerini (milyarlarca nokta) daha hızlı görselleştirme için raster görüntülere dönüştüren bir veri işleme kütüphanesi.
        ipyleaflet (Python Kütüphanesi): Jupyter Notebook ortamında dinamik ve etkileşimli haritalama için kullanılan bir Python kütüphanesi.

 ## Roadmap
1. EXIF Verisi Analizi

    Fotoğraftan EXIF metadata’sını çıkarma

    Tarih, kamera bilgisi, pozlama gibi temel verileri işleme

    GPS koordinatlarını tespit etme

2. Konum Verisinin Haritada Görselleştirilmesi

    GPS verisi varsa harita üzerinde işaretleme

    Kullanıcıya konum hakkında özet bilgi sunma

3. Ters Görsel Arama Entegrasyonu

    Fotoğrafı Google/Bing/Yandex gibi ters görsel arama servislerine gönderme

    Benzer veya aynı görsellerin URL ve önizlemelerini toplama

4. Sonuçların Kullanıcı Arayüzünde Sunulması

    EXIF bilgileri, harita ve ters görsel sonuçlarının tek bir sayfada toplanması

    Kullanıcı deneyimini kolaylaştıracak sade ve anlaşılır arayüz

5. Geliştirme ve İyileştirme

    Hataların giderilmesi ve performans optimizasyonu

    Gizlilik ve güvenlik önlemlerinin uygulanması

    İleri OSINT metotları ve veri kaynakları eklenmesi
