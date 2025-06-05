# PixelHunter Recon

## Takım Üyeleri
- Begüm Akyüz 24******05

## Proje Açıklaması
PixelHunter Recon, yüklenen fotoğrafların EXIF verilerini analiz ederek varsa GPS konumlarını haritada gösteren ve ters görsel arama yaparak benzer fotoğrafları bulan bir OSINT aracıdır.

## Hedefler
- Fotoğrafların EXIF bilgilerini çıkarmak.
- GPS bilgisi varsa harita üzerinde konum göstermek.
- Ters görsel arama ile fotoğrafın diğer versiyonlarını bulmak.

## Kullanılan Teknolojiler (Başlangıç)
- Python
- exifread / Pillow
- Flask / Streamlit
- Google Maps API / OpenStreetMap
- Reverse image search API (araştırma aşamasında)

 Roadmap
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
