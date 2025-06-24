# PixelHunter-Recon

PixelHunter-Recon, bir fotoğrafın sırlarını çözmek için tasarlanmış büyüleyici bir OSINT aracıdır! Meta veri analiziyle gizli detayları ortaya çıkarın, ters görüntü aramasıyla hikayeleri keşfedin ve konum haritalama ile dünyayı avucunuzun içine getirin.

---

## Özellikler

- **EXIF Analizi**: Fotoğraflardan tarih, cihaz ve GPS koordinatları gibi meta verileri çıkarın.
- **Ters Görüntü Araması**: Benzer görüntüleri çevrimiçi olarak bulun ve fotoğraf hakkında daha fazla bilgi edinin.
- **Konum Haritalama**: GPS koordinatlarını haritada görselleştirin.
- **Yüz ve Manzara Analizi**: Yapay zeka kullanarak fotoğraftaki yüzleri veya manzaraları tespit edin ve analiz edin.
- Geliştikçe daha fazla ekleyin.

---

## Ekip

- **24******05 - BEGÜM AKYÜZ: Ana Geliştirici


---

## Kurulum

1. **Depoyu Klonlayın**:  
   ```bash
   git clone https://github.com/periebaln/PixelHunter-Recon.git
   cd PixelHunter-Recon
   ```

2. **Sanal Ortam Kurulumu** (Önerilir):  
   ```bash
   python -m venv venv
   source venv/bin/activate  # Windows için: venv\Scripts\activate
   ```

3. **Bağımlılıkları Yükleyin**:  
   ```bash
   pip install -r requirements.txt
   ```

---

## Kullanım

Projeyi çalıştırın:

```bash
python main.py --photo yol/ile/fotograf.jpg
```

**Adımlar**:  
1. Giriş fotoğrafını hazırlayın (örneğin, bir JPG veya PNG dosyası).  
2. Betiği argümanlarla çalıştırın (`--photo` ile dosya yolunu belirtin).  
3. Çıktıyı kontrol edin (sonuçlar genellikle bir metin dosyasında veya konsolda görünür).

---

## Katkıda Bulunma

Katkılarınızı memnuniyetle karşılıyoruz! Katkıda bulunmak için:  
1. Depoyu fork edin.  
2. Fork’unuzu klonlayın (`git clone https://github.com/periebaln/PixelHunter-Recon.git`).  
3. Bir dal oluşturun (`git checkout -b ozellik/yeni-ozellik`).  
4. Değişikliklerinizi açık mesajlarla commit edin.  
5. Fork’unuza push yapın (`git push origin ozellik/yeni-ozellik`).  
6. Bir Pull Request açın.  

Kodlama standartlarımıza uyun (bkz. [CONTRIBUTING.md](CONTRIBUTING.md)).

---

## Lisans

[MIT Lisansı](LICENSE.md) altında lisanslanmıştır.

---

