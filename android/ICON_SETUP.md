# İkon ve Splash Screen Kurulumu

## İkon Oluşturma

Logo URL'sinden farklı boyutlarda ikonlar oluşturmanız gerekiyor:

**Logo URL**: https://yt3.googleusercontent.com/06KV70YTXoPlR1zIEKHm85jVuFoRK7-tFBARwwlpTPqyB_mjI-5H5ty1OqjnOJUZ_6_22Hj-5Q=s120-c-k-c0x00ffffff-no-rj

### Gerekli İkon Boyutları

Aşağıdaki klasörlere uygun boyutlarda `ic_launcher.png` ve `ic_launcher_round.png` dosyalarını yerleştirin:

1. **mipmap-mdpi** (48x48 px)
   - `android/app/src/main/res/mipmap-mdpi/ic_launcher.png`
   - `android/app/src/main/res/mipmap-mdpi/ic_launcher_round.png`

2. **mipmap-hdpi** (72x72 px)
   - `android/app/src/main/res/mipmap-hdpi/ic_launcher.png`
   - `android/app/src/main/res/mipmap-hdpi/ic_launcher_round.png`

3. **mipmap-xhdpi** (96x96 px)
   - `android/app/src/main/res/mipmap-xhdpi/ic_launcher.png`
   - `android/app/src/main/res/mipmap-xhdpi/ic_launcher_round.png`

4. **mipmap-xxhdpi** (144x144 px)
   - `android/app/src/main/res/mipmap-xxhdpi/ic_launcher.png`
   - `android/app/src/main/res/mipmap-xxhdpi/ic_launcher_round.png`

5. **mipmap-xxxhdpi** (192x192 px)
   - `android/app/src/main/res/mipmap-xxxhdpi/ic_launcher.png`
   - `android/app/src/main/res/mipmap-xxxhdpi/ic_launcher_round.png`

## Online Araçlar

İkonları oluşturmak için şu online araçları kullanabilirsiniz:

1. **AppIcon.co**: https://www.appicon.co/
   - Logo URL'sini yapıştırın
   - Android seçeneğini seçin
   - Tüm boyutları otomatik oluşturur

2. **Icon Kitchen**: https://icon.kitchen/
   - Logo yükleyin
   - Android Adaptive Icon oluşturun

3. **Android Asset Studio**: https://romannurik.github.io/AndroidAssetStudio/icons-launcher.html
   - Logo yükleyin
   - Tüm boyutları oluşturun

## Manuel Oluşturma

Eğer manuel oluşturmak isterseniz:

1. Logo görselini indirin
2. Her boyut için görseli yeniden boyutlandırın (Photoshop, GIMP, veya online araçlar)
3. Dosyaları ilgili klasörlere kopyalayın

## Splash Screen

Splash screen zaten yapılandırılmış durumda:
- Arka plan rengi: `#1a2f23` (yeşil)
- Logo ortada gösterilecek
- Dosya: `android/app/src/main/res/drawable/splash.xml`

Eğer özel bir splash görseli istiyorsanız:
1. 1080x1920 boyutunda bir splash görseli oluşturun
2. `android/app/src/main/res/drawable/splash.png` olarak kaydedin
3. `splash.xml` dosyasını güncelleyin

## Notlar

- İkonlar PNG formatında olmalı
- Şeffaf arka plan kullanabilirsiniz
- Round ikonlar için köşeler yuvarlatılmış olmalı
- İkonlar yüklenmeden APK build edilebilir, ancak varsayılan Android ikonu gösterilir

