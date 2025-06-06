Tabii ki! Kullanıcı sorgusuna dayanarak, sağlanan README dosyasını daha mantıklı, düzenli ve GitHub README formatına uygun bir şekilde yeniden düzenleyeceğim. Gereksiz bağlantılar ve şüpheli kısımlar kaldırılacak, yer tutucular netleştirilecek ve Markdown kullanımıyla okunabilirlik artırılacak. İşte güncellenmiş hali:

---

# PixelHunter Recon

<p align="center">
  <img src="https://img.shields.io/badge/License-MIT-yellow.svg" alt="Lisans: MIT">
  <img src="https://img.shields.io/badge/Python-3.8%2B-blue.svg" alt="Python Sürümü">
  <img src="https://img.shields.io/badge/Status-In%20Development-green.svg" alt="Proje Durumu">
</p>

**PixelHunter Recon**, yüklenen fotoğrafların EXIF verilerini analiz ederek GPS konumlarını (varsa) interaktif bir haritada görselleştiren ve popüler arama motorları üzerinden ters görsel arama yaparak benzer veya aynı fotoğrafları bulan açık kaynaklı bir OSINT (Açık Kaynak İstihbaratı) aracıdır. Araştırmacılar, gazeteciler ve meraklı kullanıcılar için bir görselin kökenini, bağlamını ve olası manipülasyonlarını keşfetmeyi kolaylaştırmayı hedefler.

## İçindekiler

- [Özellikler](#özellikler)
- [Demo](#demo)
- [Önkoşullar](#önkoşullar)
- [Kurulum](#kurulum)
- [Yapılandırma](#yapılandırma)
  - [Google Maps API Anahtarı](#google-maps-api-anahtarı)
  - [Ters Görsel Arama API Anahtarları](#ters-görsel-arama-api-anahtarları)
- [Kullanım](#kullanım)
- [Kullanılan Teknolojiler](#kullanılan-teknolojiler)
- [Yol Haritası](#yol-haritası)
- [Katkıda Bulunma](#katkıda-bulunma)
- [Etik Kullanım](#etik-kullanım)
- [Lisans](#lisans)
- [Geliştirici](#geliştirici)

## Özellikler

- **EXIF Veri Analizi:** Fotoğraflardan kamera modeli, çekim tarihi/saati, pozlama ayarları ve GPS koordinatları gibi EXIF meta verilerini çıkarır ve görüntüler.
- **GPS Görselleştirme:** GPS verisi bulunan fotoğrafların konumlarını Google Maps veya OpenStreetMap üzerinde interaktif bir haritada gösterir.
- **Ters Görsel Arama:** Google, Bing, Yandex gibi arama motorlarıyla ters görsel arama yaparak benzer içerikleri bulur.
- **Birleşik Arayüz:** EXIF verileri, harita ve ters arama sonuçlarını tek bir kullanıcı dostu ekranda birleştirir.

## Demo

*(Buraya projenin çalışan bir örneğini gösteren bir GIF veya demo videosu bağlantısı ekleyebilirsiniz.)*

## Önkoşullar

Projeyi çalıştırmak için aşağıdaki yazılımlara ihtiyacınız var:

- **Python 3.8+**
- **Pip** (Python paket yöneticisi)
- **Git** (Versiyon kontrol sistemi)
- *(Opsiyonel)* `Pillow` kütüphanesi için ek bağımlılıklar (Linux’ta `libjpeg-dev`, `zlib1g-dev` gibi). Detaylar için [Pillow Dokümantasyonu](https://pillow.readthedocs.io/en/stable/installation.html).

## Kurulum

1. **Projeyi Klonlayın:**
   ```bash
   git clone https://github.com/[KullanıcıAdınız]/PixelHunterRecon.git
   cd PixelHunterRecon
   ```

2. **Sanal Ortam Oluşturun ve Etkinleştirin:**
   ```bash
   # Sanal ortam oluştur
   python -m venv venv

   # Etkinleştir (Windows):
   # venv\Scripts\activate
   # Etkinleştir (macOS/Linux):
   source venv/bin/activate
   ```

3. **Bağımlılıkları Yükleyin:**
   ```bash
   pip install -r requirements.txt
   ```

## Yapılandırma

Bazı özellikler için harici API anahtarları gereklidir. Bunları bir `.env` dosyasında saklamak önerilir.

1. `.env.example` dosyasını kopyalayın:
   ```bash
   cp .env.example .env
   ```

2. `.env` dosyasını düzenleyerek API anahtarlarınızı ekleyin.

### Google Maps API Anahtarı

GPS verilerini haritada göstermek için:

1. [Google Cloud Console](https://console.cloud.google.com/)'a gidin.
2. Yeni bir proje oluşturun veya mevcut birini seçin.
3. **Maps JavaScript API** ve **Geocoding API**’yi etkinleştirin.
4. "Kimlik Bilgileri" sekmesinden bir API anahtarı oluşturun ve kısıtlayın (örn. `http://127.0.0.1:*`).
5. Anahtarı `.env` dosyasına ekleyin:
   ```env
   Maps_API_KEY="YOUR_API_KEY_HERE"
   ```

### Ters Görsel Arama API Anahtarları

- **SerpApi** ([serpapi.com](https://serpapi.com/)): Google, Bing gibi motorlar için.
  ```env
  SERPAPI_API_KEY="YOUR_SERPAPI_KEY_HERE"
  ```
- **TinEye API** ([tineye.com](https://services.tineye.com/TinEyeAPI)): Ters görsel arama için.
  ```env
  TINEYE_API_KEY="YOUR_TINEYE_KEY_HERE"
  ```

## Kullanım

Sanal ortam aktifken:

- **Flask ile:**
  ```bash
  flask run
  ```
  Tarayıcıda: `http://127.0.0.1:5000`

- **Streamlit ile:**
  ```bash
  streamlit run app.py
  ```
  Tarayıcıda: `http://localhost:8501`

## Kullanılan Teknolojiler

- **Backend:** Python
- **Web Framework:** Flask / Streamlit
- **EXIF İşleme:** `exifread`, `Pillow`
- **Haritalama:** Google Maps API, OpenStreetMap (`folium`)
- **Ters Görsel Arama:** `requests`, API istemcileri
- **Frontend:** HTML, CSS, JavaScript

## Yol Haritası

### Mevcut Özellikler
- [x] EXIF verilerini çıkarma
- [x] GPS koordinatlarını tespit etme

### Planlanan Özellikler
- [ ] Harita entegrasyonu
- [ ] Ters coğrafi kodlama (adres çıkarma)
- [ ] Tam ters görsel arama entegrasyonu
- [ ] Mobil uyumlu arayüz
- [ ] Docker desteği
- [ ] İleri OSINT metotları (manipülasyon tespiti, OCR, nesne tanıma vb.)

## Katkıda Bulunma

1. Depoyu fork’layın.
2. Yeni bir dal oluşturun: `git checkout -b ozellik/yeni-ozellik`
3. Değişikliklerinizi commit edin: `git commit -m "Açıklama"`
4. Dalınızı itin: `git push origin ozellik/yeni-ozellik`
5. Bir Pull Request açın.

Hata bildirimleri için GitHub Issues’u kullanabilirsiniz.

## Etik Kullanım

- **Gizlilik:** Kişisel verileri ifşa etmeyin.
- **Yasallık:** Yerel yasalara uyun.
- **Doğruluk:** Bilgileri teyit edin.
- **Kötüye Kullanım:** Taciz veya zararlı amaçlarla kullanmayın.

Geliştiriciler, aracın kötüye kullanımından sorumlu değildir.

## Lisans

Bu proje [MIT Lisansı](LICENSE) ile lisanslanmıştır.

## Geliştirici

- **Begüm Akyüz** - [GitHub Profilim](https://github.com/[KullanıcıAdınız])

---

Bu versiyon, daha temiz, profesyonel ve README dosyasına uygun bir yapı sunuyor. `[KullanıcıAdınız]` gibi yer tutucuları kendi bilgilerinizle değiştirmeyi unutmayın!
