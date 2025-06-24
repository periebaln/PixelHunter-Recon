# 🕵️‍♂️ Dijital Görüntü Dedektiflik Araç Seti: Süper Güçlerle Dolu Bir Öğrenci Macerası! 🖼️🌍

Bu yol haritası, bir öğrenci olarak dijital görüntü analiziyle (OSINT) tanışman için tasarlanmış, eğlenceli ve uygulanabilir bir proje planıdır. Görüntülerden meta veri çıkarmaktan ters görüntü aramasına, yüz tanımadan coğrafi konumlandırmaya kadar bir dedektif gibi sırları açığa çıkaracaksın! 🚀 Karmaşık yapay zeka modellerine dalmadan, Python ve erişilebilir kütüphanelerle havalı bir araç seti oluşturacağız. Hazır mısın? Hadi başlayalım!



https://github.com/user-attachments/assets/cc8a04be-04c0-46cb-b3f2-f01e35637364 



## ✨ Projenin Amacı ve Neden Bu Kadar Havalı?

Bu proje, bir fotoğrafın hikayesini çözmek için dijital dedektiflik yapmanı sağlayacak. Çekim tarihi, cihaz bilgisi, GPS konumu gibi meta verileri çıkarabilir, internette benzer kopyalarını bulabilir, hatta yüzleri veya manzaraları analiz edebilirsin! Öğrenci olarak bu proje:

- Python becerilerini roket hızında geliştirir 🚀
- Açık Kaynak İstihbaratı (OSINT) dünyasına eğlenceli bir giriş sunar 🕵️‍♂️
- Portföyüne ekleyebileceğin etkileyici bir proje olur 📊
- Etik ve sorumlu veri kullanımıyla gerçek dünya sorunlarına dokunur 🌐

**Örnek Senaryo:** Bir arkadaşın sana bir tatil fotoğrafı gönderiyor, ama nerede çekildiğini bilmiyorsun. Bu araç setiyle fotoğrafın meta verilerini, çekildiği olası konumu ve internetteki benzer görüntülerini saniyeler içinde bulabilirsin!

## 🛠️ Süper Güçlerimiz: Kullanacağımız Teknolojiler

- **Programlama Dili:** Python (kolay, güçlü, öğrenci dostu)
- **Kütüphaneler:**
  - [Pillow](https://python-pillow.org/): Görüntü meta verisi (EXIF) çıkarmak için
  - [reverse-image-search](https://pypi.org/project/reverse-image-search/): Yerel dosyalarda ters görüntü araması
  - [face_recognition](https://github.com/ageitgey/face_recognition): Yüz tespiti (etik şekilde, test verileriyle)
  - [Folium](https://python-visualization.github.io/folium/): Konumları harita üzerinde görselleştirme
  - [torchvision](https://pytorch.org/vision/stable/index.html): ResNet ile basit manzara analizi (opsiyonel)
- **Dış API:** [Google Cloud Vision API](https://cloud.google.com/vision) (ücretsiz deneme sürümüyle nesne tanıma ve çevrimiçi arama)
- **Araçlar:** VS Code, Jupyter Notebook, GitHub (kodunu paylaşmak için)

## 🚀 Yol Haritası: Sırları Açığa Çıkarma Planı

Bu plan, projeyi **2.5-4 haftada** tamamlaman için tasarlandı. Her adım, öğrenci temposuna uygun süreler ve net talimatlarla düzenlendi. Kod blokları ve görseller, bozulmadan kopyalanabilir şekilde formatlandı.

### 1. Geliştirme Ortamını Kur

**Açıklama:** Python ve kütüphaneleri kurarak projeye start veriyoruz.

- **Görevler:**
  - Python 3.8+’i kur: [Python resmi sitesi](https://www.python.org/)
  - Gerekli kütüphaneleri yükle:
    ```bash
    pip install pillow reverse-image-search folium face_recognition torchvision
    ```
  - Google Cloud Vision API için ücretsiz deneme hesabı aç: [Kılavuz](https://cloud.google.com/vision/docs/setup)
  - VS Code veya Jupyter Notebook kur
- **Tahmini Süre:** 1-2 gün
- **Öncelik:** Yüksek
- **Bağımlılıklar:** Yok
- **Riskler ve Çözümler:**
  - **Risk:** Kütüphane kurulumunda hata
    - **Çözüm:** Python sürümünü kontrol et (3.8+ önerilir), [Stack Overflow](https://stackoverflow.com/)’dan yardım al
  - **Risk:** Google Cloud API kurulumu karmaşık gelebilir
    - **Çözüm:** Resmi dokümantasyonu takip et, sadece “Image Analysis” API’sini aktif et
- **Görsel Örnek:**  
  ![VS Code Ortamı](https://via.placeholder.com/400x200.png?text=VS+Code+Kurulum+Ekran+Görüntüsü)  
  *Yakında: VS Code’da çalışan Python ortamının ekran görüntüsü*

### 2. Meta Veri Çıkarma Modülü

**Açıklama:** Görüntülerin EXIF verilerini (tarih, cihaz, GPS) Pillow ile çıkaracağız.

- **Görevler:**
  - Pillow ile EXIF verilerini okuyan bir fonksiyon yaz
  - Çıktıyı kullanıcı dostu şekilde göster (örneğin, tarih, GPS koordinatları)
- **Örnek Kod:**
  ```python
  from PIL import Image
  from PIL.ExifTags import TAGS

  def extract_metadata(image_path):
      try:
          img = Image.open(image_path)
          exif_data = img._getexif()
          if exif_data:
              metadata = {}
              for tag, value in exif_data.items():
                  tag_name = TAGS.get(tag, tag)
                  metadata[tag_name] = value
              print("Meta Veriler:")
              for key, value in metadata.items():
                  print(f"  {key}: {value}")
              return metadata
          else:
              print("EXIF verisi bulunamadı.")
              return {}
      except Exception as e:
          print(f"Hata: {e}")
          return {}

  # Kullanım
  extract_metadata("tatil_fotografi.jpg")
  ```
- **Tahmini Süre:** 1-2 gün
- **Öncelik:** Yüksek
- **Bağımlılıklar:** Adım 1
- **Riskler ve Çözümler:**
  - **Risk:** EXIF verisi olmayan görüntüler
    - **Çözüm:** Akıllı telefonla çekilmiş test fotoğrafları kullan ([Pixabay](https://pixabay.com/))
- **Görsel Örnek:**  
  ![Meta Veri Çıktısı](https://via.placeholder.com/400x200.png?text=Meta+Veri+Çıktısı)  
  *Yakında: EXIF verilerinin terminalde göründüğü bir ekran görüntüsü*

### 3. Ters Görüntü Araması Modülü

**Açıklama:** Yerel dosyalarda benzer görüntüleri bulacağız ve Google Cloud Vision API ile çevrimiçi arama yapacağız.

- **Görevler:**
  - `reverse-image-search` ile yerel dizinde benzer görüntüleri ara
  - Google Cloud Vision API ile nesne tanıma ve web’de benzer görüntü bul
- **Örnek Kod (Yerel Arama):**
  ```python
  from reverse_image_search import ReverseImageSearch

  def reverse_search_local(image_path, search_dir):
      try:
          ris = ReverseImageSearch()
          results = ris.search(image_path, search_dir, threshold=0.9)
          if results:
              print("Benzer Görüntüler:")
              for result in results:
                  print(f"  Dosya: {result['filepath']}, Benzerlik: {result['similarity']}%")
          else:
              print("Benzer görüntü bulunamadı.")
      except Exception as e:
          print(f"Hata: {e}")

  # Kullanım
  reverse_search_local("sorgu_fotograf.jpg", "fotograf_klasoru/")
  ```
- **Örnek Kod (Google Vision API):**
  ```python
  from google.cloud import vision

  def reverse_search_online(image_path):
      client = vision.ImageAnnotatorClient()
      with open(image_path, "rb") as image_file:
          content = image_file.read()
      image = vision.Image(content=content)
      response = client.web_detection(image=image)
      web_entities = response.web_detection.web_entities
      if web_entities:
          print("Web’de Bulunan Benzer İçerikler:")
          for entity in web_entities:
              if entity.description:
                  print(f"  Açıklama: {entity.description}, Skor: {entity.score}")
      else:
          print("Web’de benzer içerik bulunamadı.")

  # Kullanım
  reverse_search_online("sorgu_fotograf.jpg")
  ```
- **Tahmini Süre:** 3-4 gün
- **Öncelik:** Yüksek
- **Bağımlılıklar:** Adım 1
- **Riskler ve Çözümler:**
  - **Risk:** Google Vision API ücretsiz kotası dolabilir
    - **Çözüm:** Testleri küçük tut, ücretsiz deneme limitini takip et
  - **Risk:** Yerel aramada performans düşüklüğü
    - **Çözüm:** 10-20 görüntülük küçük bir dizinle test yap
- **Görsel Örnek:**  
  ![Google Vision Sonuçları](https://via.placeholder.com/400x200.png?text=Google+Vision+API+Sonuçları)  
  *Yakında: Web’de bulunan benzer görüntülerin çıktısı*

### 4. Yüz Tanıma Modülü

**Açıklama:** Etik şekilde, test verileriyle yüz tespiti yapacağız.

- **Görevler:**
  - `face_recognition` ile bir görüntüde yüzleri tespit et
  - Test amaçlı bir veri setiyle (örneğin, anonim test görüntüleri) yüz eşleştirme yap
- **Örnek Kod:**
  ```python
  import face_recognition

  def detect_faces(image_path):
      try:
          image = face_recognition.load_image_file(image_path)
          face_locations = face_recognition.face_locations(image)
          if face_locations:
              print(f"{len(face_locations)} yüz tespit edildi.")
              for i, loc in enumerate(face_locations):
                  top, right, bottom, left = loc
                  print(f"  Yüz {i+1}: Konum ({left},{top})-({right},{bottom})")
          else:
              print("Yüz bulunamadı.")
      except Exception as e:
          print(f"Hata: {e}")

  # Kullanım
  detect_faces("test_fotograf.jpg")
  ```
- **Not:** Yüz tanıma, sadece test verileriyle ([Labeled Faces in the Wild](http://vis-www.cs.umass.edu/lfw/)) kullanılmalı. Gerçek kişilerle kullanmak etik sorunlar doğurabilir.
- **Tahmini Süre:** 2-3 gün
- **Öncelik:** Orta
- **Bağımlılıklar:** Adım 1
- **Riskler ve Çözümler:**
  - **Risk:** Etik veya gizlilik sorunları
    - **Çözüm:** Sadece açık lisanslı test verileri kullan, gerçek kişilerden izin al
  - **Risk:** Kütüphane yavaş çalışabilir
    - **Çözüm:** Küçük görüntülerle test yap
- **Görsel Örnek:**  
  ![Yüz Tespiti](https://via.placeholder.com/400x200.png?text=Yüz+Tespiti+Sonuçları)  
  *Yakında: Tespit edilen yüzlerin işaretlendiği bir görüntü*

### 5. Coğrafi Konumlandırma ve Görselleştirme Modülü

**Açıklama:** EXIF’teki GPS verilerini haritada göstereceğiz ve opsiyonel olarak manzara analiziyle konum tahmini yapacağız.

- **Görevler:**
  - GPS koordinatlarını EXIF’ten çıkar ve Folium ile haritada göster
  - Opsiyonel: ResNet ile manzara analizi yaparak konum tahmini öner (örneğin, “bu bir plaj”)
- **Örnek Kod (GPS ve Harita):**
  ```python
  from PIL import Image
  from PIL.ExifTags import TAGS, GPSTAGS
  import folium

  def get_gps_coordinates(image_path):
      try:
          img = Image.open(image_path)
          exif_data = img._getexif()
          if exif_data and "GPSInfo" in exif_data:
              gps_info = {}
              for tag, value in exif_data.items():
                  tag_name = TAGS.get(tag, tag)
                  if tag_name == "GPSInfo":
                      for gps_tag, gps_value in value.items():
                          gps_tag_name = GPSTAGS.get(gps_tag, gps_tag)
                          gps_info[gps_tag_name] = gps_value
              if "GPSLatitude" in gps_info and "GPSLongitude" in gps_info:
                  lat = gps_info["GPSLatitude"]
                  lon = gps_info["GPSLongitude"]
                  lat_ref = gps_info.get("GPSLatitudeRef", "N")
                  lon_ref = gps_info.get("GPSLongitudeRef", "E")
                  latitude = (lat[0] + lat[1]/60.0 + lat[2]/3600.0) * (1 if lat_ref == "N" else -1)
                  longitude = (lon[0] + lon[1]/60.0 + lon[2]/3600.0) * (1 if lon_ref == "E" else -1)
                  return latitude, longitude
          return None, None
      except Exception as e:
          print(f"Hata: {e}")
          return None, None

  def plot_location(latitude, longitude):
      if latitude and longitude:
          map = folium.Map(location=[latitude, longitude], zoom_start=15)
          folium.Marker([latitude, longitude], popup="Çekim Konumu").add_to(map)
          map.save("konum_haritasi.html")
          print("Harita 'konum_haritasi.html' dosyasına kaydedildi.")
      else:
          print("GPS verisi bulunamadı.")

  # Kullanım
  lat, lon = get_gps_coordinates("tatil_fotografi.jpg")
  plot_location(lat, lon)
  ```
- **Örnek Kod (Manzara Analizi - Opsiyonel):**
  ```python
  from torchvision import models, transforms
  from PIL import Image
  import torch

  def analyze_scene(image_path):
      model = models.resnet50(pretrained=True)
      model.eval()
      transform = transforms.Compose([
          transforms.Resize(256),
          transforms.CenterCrop(224),
          transforms.ToTensor(),
          transforms.Normalize(mean=[0.485, 0.456, 0.406], std=[0.229, 0.224, 0.225])
      ])
      img = Image.open(image_path)
      img_t = transform(img)
      batch_t = torch.unsqueeze(img_t, 0)
      with torch.no_grad():
          out = model(batch_t)
      # ImageNet sınıflarıyla eşleştir (örneğin, "plaj", "dağ")
      print("Manzara tahmini: [Örnek - Plaj, Dağ vb.]")
      # Not: Gerçek sınıflandırma için ImageNet etiketleri gerekir

  # Kullanım
  analyze_scene("tatil_fotografi.jpg")
  ```
- **Tahmini Süre:** 3-4 gün (manzara analizi hariç 2 gün)
- **Öncelik:** Yüksek
- **Bağımlılıklar:** Adım 2
- **Riskler ve Çözümler:**
  - **Risk:** GPS verisi eksik
    - **Çözüm:** Manzara analiziyle destekle veya kullanıcıya net mesaj göster
  - **Risk:** ResNet yavaş veya karmaşık
    - **Çözüm:** Opsiyonel tut, küçük görüntülerle test yap
- **Görsel Örnek:**  
  ![Folium Haritası](https://via.placeholder.com/400x200.png?text=Folium+Harita+Örneği)  
  *Yakında: GPS koordinatlarının işaretlendiği bir harita ekran görüntüsü*

### 6. Modülleri Entegre Etme

**Açıklama:** Tüm modülleri birleştirip kullanıcı dostu bir arayüz yapacağız.

- **Görevler:**
  - Komut satırı arayüzü yaz (tüm modülleri çağıran bir script)
  - Opsiyonel: [Streamlit](https://streamlit.io/) ile basit bir web arayüzü oluştur
- **Örnek Kod (Komut Satırı):**
  ```python
  def analyze_image(image_path, search_dir):
      print("🕵️‍♂️ Görüntü Analizi Başlıyor...")
      print("\n1. Meta Veri Analizi:")
      metadata = extract_metadata(image_path)
      print("\n2. Ters Görüntü Araması (Yerel):")
      reverse_search_local(image_path, search_dir)
      print("\n3. Ters Görüntü Araması (Çevrimiçi):")
      reverse_search_online(image_path)
      print("\n4. Yüz Tespiti:")
      detect_faces(image_path)
      print("\n5. Coğrafi Konumlandırma:")
      lat, lon = get_gps_coordinates(image_path)
      plot_location(lat, lon)
      print("\n6. Manzara Analizi (Opsiyonel):")
      analyze_scene(image_path)

  # Kullanım
  image_path = input("Görüntü dosyasının yolunu gir: ")
  search_dir = input("Ters arama için dizin yolunu gir: ")
  analyze_image(image_path, search_dir)
  ```
- **Örnek Kod (Streamlit - Opsiyonel):**
  ```python
  import streamlit as st

  st.title("🕵️‍♂️ Dijital Görüntü Dedektifi")
  uploaded_file = st.file_uploader("Bir görüntü yükle", type=["jpg", "png"])
  if uploaded_file:
      with open("temp.jpg", "wb") as f:
          f.write(uploaded_file.getbuffer())
      st.write("Analiz Sonuçları:")
      st.write("Meta Veriler:", extract_metadata("temp.jpg"))
      # Diğer modülleri benzer şekilde çağır
  ```
- **Tahmini Süre:** 4-5 gün (Streamlit hariç 3 gün)
- **Öncelik:** Yüksek
- **Bağımlılıklar:** Adımlar 2-5
- **Riskler ve Çözümler:**
  - **Risk:** Modüller arasında uyumsuzluk
    - **Çözüm:** Her modülü ayrı test et, hata ayıklama için print kullan
  - **Risk:** Streamlit öğrenmesi zaman alabilir
    - **Çözüm:** Önce komut satırını tamamla, Streamlit’i bonus yap

### 7. Test ve Dokümantasyon

**Açıklama:** Araç setini test edip kullanım kılavuzu yazacağız.

- **Görevler:**
  - Farklı görüntülerle test yap (EXIF’li/EXIF’siz, GPS’li/GPS’siz)
  - README dosyası yaz (kurulum, kullanım, sınırlamalar)
- **Örnek README:**
  ```markdown
  # Dijital Görüntü Dedektiflik Araç Seti

  Bu proje, görüntülerden meta veri, yüz, konum ve benzer içerikler çıkaran bir Python araç setidir.

  ## Kurulum
  1. Python 3.8+ kurun: [python.org](https://www.python.org/)
  2. Kütüphaneleri yükleyin:
     ```bash
     pip install pillow reverse-image-search folium face_recognition torchvision
     ```
  3. Google Cloud Vision API’yi kurun: [Kılavuz](https://cloud.google.com/vision/docs/setup)

  ## Kullanım
  1. `main.py`’yi çalıştırın
  2. Görüntü dosyasını ve ters arama dizinini belirtin
  3. Sonuçları terminalde ve `konum_haritasi.html`’de görün

  ## Sınırlamalar
  - Çevrimiçi arama Google Vision API kotasına bağlı
  - Yüz tanıma sadece test verileriyle kullanılmalı

  ## Yol Haritası
  Daha fazla detay için [ROADMAP.md](ROADMAP.md)’yi okuyun

  ## Lisans
  MIT Lisansı
  ```
- **Tahmini Süre:** 2-3 gün
- **Öncelik:** Orta
- **Bağımlılıklar:** Adım 6
- **Riskler ve Çözümler:**
  - **Risk:** Testlerde hata çıkması
    - **Çözüm:** Hataları logla, küçük veri setleriyle test yap

### 8. Sunum ve Paylaşım

**Açıklama:** Projeni bir raporla veya GitHub’da paylaşarak dünyaya sun!

- **Görevler:**
  - Projenin ne yaptığını, nasıl çalıştığını anlatan bir rapor yaz
  - Kodu [GitHub](https://github.com/)’a yükle, README’yi cilala
- **Tahmini Süre:** 1-2 gün
- **Öncelik:** Düşük
- **Bağımlılıklar:** Adım 7

## ⏰ Toplam Süre ve Planlama

| Adım | Tahmini Süre | Öncelik |
|------|--------------|---------|
| Ortam Kurma | 1-2 gün | Yüksek |
| Meta Veri Çıkarma | 1-2 gün | Yüksek |
| Ters Görüntü Araması | 3-4 gün | Yüksek |
| Yüz Tanıma | 2-3 gün | Orta |
| Coğrafi Konumlandırma | 3-4 gün | Yüksek |
| Entegrasyon | 4-5 gün | Yüksek |
| Test ve Dokümantasyon | 2-3 gün | Orta |
| Sunum | 1-2 gün | Düşük |

**Toplam Süre:** 18-25 gün (2.5-4 hafta)

## ⚠️ Potansiyel Riskler ve Çözümler

| Risk | Çözüm |
|------|-------|
| Kütüphane kurulum hataları | Python sürümünü kontrol et, [Stack Overflow](https://stackoverflow.com/)’dan destek al |
| Google Vision API kota sorunu | Ücretsiz kotayı takip et, testleri sınırla |
| Etik/gizlilik sorunları | Yüz tanıma için sadece test verileri kullan, izin al |
| Performans düşüklüğü | Küçük veri setleriyle çalış (10-20 görüntü) |
| Streamlit öğrenme süresi | Önce komut satırını tamamla, Streamlit’i bonus yap |

## 📚 Gerekli Kaynaklar

- **İnsan Kaynakları:** Sadece sen! (Öğrenci olarak kendi başınasın)
- **Teknoloji:** Bilgisayar, Python, internet, Google Cloud hesabı (ücretsiz deneme)
- **Veri:** [Pixabay](https://pixabay.com/), [Labeled Faces in the Wild](http://vis-www.cs.umass.edu/lfw/) veya kendi test fotoğrafların

## 🎯 Sonuç ve Bonus Fikirler

Bu yol haritası, dijital dedektiflik dünyasına adım atman için eksiksiz bir plan sunuyor! Projen bittiğinde, bir görüntüyü yükleyip meta verilerini, benzer görüntüleri, yüzleri ve çekim konumunu analiz edebileceksin. Portföyüne eklemek için harika bir iş olacak! 😎

**Bonus Fikirler:**
- **GeoSpy Benzeri AI:** ResNet’i geliştirip [Places365](http://places2.csail.mit.edu/) ile eğiterek daha iyi konum tahmini yap
- **Mobil Uygulama:** Streamlit arayüzünü mobil dostu bir versiyona çevir
- **Deepfake Tespiti:** Basit bir deepfake dedektörü için [DeepFace](https://github.com/serengil/deepface) araştır

Başarılar dilerim, dedektif! Soruların olursa, yaz bana! 🕵️‍♂️



---

### README ile Bağlantı Önerisi

`README.md` dosyana yol haritasını bağlamak için şu bölümü ekleyebilirsin:

```markdown
# Dijital Görüntü Dedektiflik Araç Seti

## Proje Hakkında
Bu proje, görüntülerden meta veri, yüz, konum ve benzer içerikler çıkaran bir Python araç setidir. Dijital dedektiflik dünyasına giriş yapmak isteyen öğrenciler için tasarlandı! 🕵️‍♂️

## Kurulum
1. Python 3.8+ kurun: [python.org](https://www.python.org/)
2. Kütüphaneleri yükleyin:
   ```bash
   pip install pillow reverse-image-search folium face_recognition torchvision
   ```
3. Google Cloud Vision API’yi kurun: [Kılavuz](https://cloud.google.com/vision/docs/setup)

## Kullanım
1. `main.py`’yi çalıştırın
2. Görüntü dosyasını ve ters arama dizinini belirtin
3. Sonuçları terminalde ve `konum_haritasi.html`’de görün


## Lisans
MIT Lisansı
```
