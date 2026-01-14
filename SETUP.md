# APK Oluşturma Adımları

## Gereksinimler

- Node.js 16+ (npm veya yarn)
- Android Studio (en son sürüm)
- JDK 11+ (Java Development Kit)
- Android SDK (Android Studio ile birlikte gelir)

## Kurulum Adımları

### 1. Bağımlılıkları Yükle

```bash
npm install
```

Bu komut tüm npm paketlerini ve Capacitor bağımlılıklarını yükler.

### 2. React Uygulamasını Build Et

```bash
npm run build
```

Bu komut React uygulamasını `dist` klasörüne build eder. Vite kullanıldığı için build çıktısı `dist` klasöründe olacaktır.

### 3. Capacitor'ı İlk Kez Başlatma

Eğer ilk kez Capacitor kurulumu yapıyorsanız:

```bash
npx cap init
```

Bu komut zaten çalıştırılmışsa atlayabilirsiniz.

### 4. Android Platformunu Ekle

```bash
npx cap add android
```

### 5. Capacitor'ı Senkronize Et

```bash
npx cap sync android
```

Bu komut:
- Web build dosyalarını Android projesine kopyalar
- Capacitor plugin'lerini yükler
- Android proje yapısını günceller

### 6. Android Studio'yu Aç

```bash
npx cap open android
```

Bu komut Android Studio'yu açar ve projeyi yükler.

## Android Studio'da APK Oluşturma

### Yöntem 1: GUI ile (Önerilen)

1. Android Studio açıldıktan sonra, üst menüden:
   - **Build** > **Build Bundle(s) / APK(s)** > **Build APK(s)**

2. Build tamamlandıktan sonra:
   - **locate** linkine tıklayın veya
   - Dosya yoluna gidin: `android/app/build/outputs/apk/debug/app-debug.apk`

### Yöntem 2: Komut Satırından

Terminal'de (PowerShell veya CMD):

```bash
cd android
.\gradlew assembleDebug
```

Windows'ta `gradlew.bat` kullanılır. APK dosyası şu konumda oluşur:
`android/app/build/outputs/apk/debug/app-debug.apk`

## Release APK Oluşturma

### 1. Keystore Oluştur (İlk kez)

```bash
keytool -genkey -v -keystore tarihtebugun-release.keystore -alias tarihtebugun -keyalg RSA -keysize 2048 -validity 10000
```

### 2. android/app/build.gradle'a Keystore Bilgilerini Ekle

```gradle
android {
    ...
    signingConfigs {
        release {
            storeFile file('../tarihtebugun-release.keystore')
            storePassword 'your-password'
            keyAlias 'tarihtebugun'
            keyPassword 'your-password'
        }
    }
    buildTypes {
        release {
            signingConfig signingConfigs.release
            minifyEnabled false
            proguardFiles getDefaultProguardFile('proguard-android-optimize.txt'), 'proguard-rules.pro'
        }
    }
}
```

### 3. Release APK Build Et

```bash
cd android
.\gradlew assembleRelease
```

Release APK: `android/app/build/outputs/apk/release/app-release.apk`

## Sorun Giderme

### "SDK location not found" Hatası

`android/local.properties` dosyası oluşturun:

```properties
sdk.dir=C\:\\Users\\KullaniciAdi\\AppData\\Local\\Android\\Sdk
```

Windows'ta SDK konumu genellikle: `%LOCALAPPDATA%\Android\Sdk`

### "Gradle sync failed" Hatası

1. Android Studio'da: **File** > **Invalidate Caches / Restart**
2. `android/.gradle` klasörünü silin
3. Tekrar sync edin

### Capacitor Sync Hatası

```bash
npx cap sync android --force
```

### Build Hatası: "Could not find or load main class"

Gradle wrapper'ı yeniden indirin:

```bash
cd android
.\gradlew wrapper --gradle-version 8.0
```

## APK'yı Test Etme

### Emülatörde Test

1. Android Studio'da bir emülatör oluşturun
2. **Run** > **Run 'app'** veya yeşil play butonuna tıklayın

### Fiziksel Cihazda Test

1. Android cihazınızda **Geliştirici Seçenekleri**'ni açın
2. **USB Hata Ayıklama**'yı etkinleştirin
3. Cihazı USB ile bilgisayara bağlayın
4. Android Studio'da cihazınızı seçip **Run** butonuna tıklayın

### APK'yı Doğrudan Yükleme

1. APK dosyasını Android cihazınıza kopyalayın
2. Cihazda **Bilinmeyen Kaynaklardan Uygulama Yükleme**'yi etkinleştirin
3. APK dosyasına dokunup yükleyin

## Notlar

- İlk build biraz uzun sürebilir (Gradle bağımlılıklarını indirir)
- Her kod değişikliğinden sonra `npm run build` ve `npx cap sync android` çalıştırın
- Android Studio'da yapılan değişiklikler `npx cap sync` ile üzerine yazılabilir, dikkatli olun
- `capacitor.config.json` dosyasındaki `webDir` değeri Vite için `dist` olmalı

## Hızlı Komutlar Özeti

```bash
# Geliştirme döngüsü
npm run build
npx cap sync android
npx cap open android

# Sadece APK build (Android Studio olmadan)
cd android
.\gradlew assembleDebug
```

## İkon ve Splash Screen

İkonlar ve splash screen görselleri şu klasörlerde olmalı:

- **İkonlar**: `android/app/src/main/res/mipmap-*/ic_launcher.png`
- **Splash**: `android/app/src/main/res/drawable/splash.xml` (zaten oluşturuldu)

Logo URL'sinden farklı boyutlarda ikonlar oluşturmanız gerekiyor:
- mipmap-mdpi: 48x48
- mipmap-hdpi: 72x72
- mipmap-xhdpi: 96x96
- mipmap-xxhdpi: 144x144
- mipmap-xxxhdpi: 192x192

Online araçlar kullanabilirsiniz:
- https://www.appicon.co/
- https://icon.kitchen/

