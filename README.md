# Tarihte Bugün - Mobil Uygulama

İslami temalı, modern ve responsive bir "Tarihte Bugün" React uygulaması.

## Özellikler

- 📅 Son 30 günün tarihi olaylarını görüntüleme
- 🕌 İslami tema (kum beji - koyu yeşil renk paleti)
- 📱 Tam responsive mobil uyumlu tasarım
- 🗓️ Hicri ve Rumi takvim bilgileri
- 🎬 YouTube entegrasyonu
- 🎨 Smooth animasyonlar ve geçişler

## Kurulum

```bash
# Bağımlılıkları yükle
npm install

# Geliştirme sunucusunu başlat
npm run dev

# Production build
npm run build
```

## Teknolojiler

- React 18
- Vite
- Tailwind CSS
- Lucide React (İkonlar)

## Kullanım

1. Sol üstteki hamburger menüye tıklayarak son 30 günü görüntüleyin
2. İstediğiniz tarihe tıklayarak o günün tarihi olayını görüntüleyin
3. "YouTube'da İzle" butonuna tıklayarak ilgili videoları izleyin

## Tasarım

Uygulama, İslami temaya uygun renk paleti kullanır:
- Koyu yeşil (#1a3a2a, #2d5f3f)
- Kum beji tonları (#8b7355, #d4c4a8, #f5f0e8)

## 📱 APK İndirme ve Kurulum

### GitHub'dan APK İndirme

Bu uygulamanın APK dosyasını GitHub'dan indirebilirsiniz:

#### Yöntem 1: GitHub Releases (Önerilen)

1. **GitHub Repository'nize gidin**
   - Projenizin GitHub sayfasına gidin (örn: `https://github.com/kullaniciadi/tarih4`)

2. **Releases sayfasına gidin**
   - Sağ tarafta "Releases" bölümüne tıklayın
   - Veya URL'ye direkt `/releases` ekleyin

3. **APK'yı indirin**
   - En son release'in altında "Assets" bölümünü açın
   - `app-release-unsigned.apk` dosyasını telefonunuza indirin

4. **APK'yı telefonunuza yükleyin**
   - Android telefonunuzda "Bilinmeyen kaynaklardan uygulama yükleme" iznini aktif edin
   - İndirdiğiniz APK dosyasına tıklayarak kurulumu başlatın

#### Yöntem 2: GitHub Actions Artifacts

1. **GitHub Actions sayfasına gidin**
   - Repository'de "Actions" sekmesine tıklayın

2. **Son build'i bulun**
   - "Build APK" workflow'unu bulun ve en son çalışanı açın

3. **Artifact'ı indirin**
   - Sayfanın altında "Artifacts" bölümünde "app-release" linkine tıklayın
   - ZIP dosyasını indirip içinden APK'yı çıkarın

### Yeni APK Oluşturma (Geliştiriciler için)

Yeni bir APK oluşturmak için:

1. **Tag oluşturun:**
   ```bash
   git tag v1.0.0
   git push origin v1.0.0
   ```

2. **Veya manuel olarak çalıştırın:**
   - GitHub'da "Actions" sekmesine gidin
   - "Build APK" workflow'unu seçin
   - "Run workflow" butonuna tıklayın

3. **APK otomatik olarak oluşturulacak:**
   - Tag ile tetiklenirse otomatik olarak Release oluşturulur
   - Manuel çalıştırılırsa Artifacts bölümünden indirebilirsiniz

### Notlar

- ⚠️ APK dosyası unsigned (imzasız) olarak oluşturulur
- 📱 Android 5.0 (API 22) ve üzeri cihazlarda çalışır
- 🔒 İlk yüklemede Android güvenlik uyarısı verebilir, bu normaldir

## Lisans

MIT

