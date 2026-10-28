# Değişiklik Günlüğü

Bu projedeki tüm önemli değişiklikler bu dosyada belgelenir.

Format [Keep a Changelog](https://keepachangelog.com/en/1.1.0/) temel alınarak
hazırlanmıştır ve bu proje [Semantic Versioning](https://semver.org/spec/v2.0.0.html) ilkelerine uyar.

> Asıl kaynak İngilizce [CHANGELOG.md](CHANGELOG.md) dosyasıdır; bu çeviri biraz geride kalabilir.

## [2.8.0] - 2026-10-22

### Eklendi
- **IE bölge haritası taraması (zone map)** — Kakao alan adlarına ait
  zone-map girdilerini tespit eder («güvenilen siteler» kalıntıları);
  kaldırma, alan adının alt ağacını siler (önce dışa aktarım)
- **RegisteredApplications taraması** — varsayılan uygulama meta
  verilerindeki Kakao girdilerini tespit eder; kaldırma değeri siler
  (önce dışa aktarım)
- **MUICache taraması** — Kakao yürütülebilir dosyalarının çalıştırma
  izlerini tespit eder; kaldırma önbellek değerini siler (önce dışa
  aktarım)
- **%TEMP% içindeki yükleyici izleri** — scan_traces artık kullanıcının
  geçici klasöründe kalan Kakao yükleyicilerini de raporlar
- **Kullanıcı başına ürün dizinleri** — scan_product_dirs artık
  `%LOCALAPPDATA%\Programs\Kakao*` yolunu da kapsar (Kakao Music /
  Messenger / Translate legacy kurulumları), tarayıcı klasörü hariç
  tutulur
- **Yola göre süreç sonlandırma (Vanced)** — tarayıcıya özel kill artık
  yürütülebilir dosyası bir KakaoBrowser yolu altında bulunan süreçleri
  de eşleştirir (crashpad, updater), yalnızca dar browser.exe/kakao.exe
  ad listesini değil
- **Başlangıç URL ele geçirme taraması** — `RestoreOnStartupURLs`
  enterprise ilkelerindeki Kakao URL'lerini tespit eder (Edge, Chrome,
  Chromium, Brave, Vivaldi, Opera, Kakao Browser); kaldırma Kakao
  değerlerini temizler
- **Firefox ana sayfası ele geçirme taraması** — Firefox/Waterfox
  `prefs.js` içinde Kakao'e işaret eden `browser.startup.homepage`
  değerini tespit eder; kaldırma dosyayı yeniden yazar (önce yedek)

## [2.7.0] - 2026-10-21

### Eklendi
- **Kakao.DNS taraması** (Extended) — Kakao DNS sunucularıyla
  (77.88.8.x basic/safe/family) yapılandırılmış ağ bağdaştırıcılarını
  tespit eder; kaldırma bağdaştırıcıyı otomatik DNS'e döndürür; onaylı
- **Başlangıç sayfası ele geçirme taraması** — Kakao/kakao.com'yu işaret eden
  legacy IE başlangıç sayfasını (`HKCU\...\Internet Explorer\Main\Start
  Page`) tespit eder; kaldırma varsayılanı geri yükler (her iki sürüm)

## [2.6.0] - 2026-10-21

### Eklendi
- **Extended sürümü**: Store (Appx) uygulama taraması — Kakao Music,
  Messenger, Messenger ve diğer Kakao Store uygulamalarını tespit eder,
  `Remove-AppxPackage` ile kaldırır
- **Extended sürümü**: `Program Files\Kakao\` altındaki tarayıcı dışı
  ürün dizinleri taraması (Kakao Disk, Kakao IME Switcher, IME, ...) —
  kaldırmadan önce yedek
- **Extended sürümü**: `%LOCALAPPDATA%\Kakao\` altındaki tarayıcı dışı
  yerel veri taraması (Kakao IME Switcher yerel verileri, Kakao Disk
  güncelleyicisi, Beta derlemeleri) — onaylı, kaldırmadan önce yedek
- **Extended sürümü**: «Kill Processes» artık yalnızca tarayıcıyı değil,
  tüm Kakao ürün süreçlerini (Kakao Disk, Kakao IME Switcher, Store
  uygulamaları) sonlandırır

## [2.5.0] - 2026-10-21

### Eklendi
- Tek kod tabanından iki sürüm: **AntiKakaoVanced** (Kakao Browser +
  Kakao Arama kaldırma) ve **AntiKakaoExtended** (tüm Kakao ürünleri) —
  `profiles.py` içindeki ürün profilleri tarama kapsamını seçer, ortak GUI
  `app.py` içinde, ince giriş noktaları `main.py` / `main_extended.py`
- `build.bat` artık her iki EXE'yi de derler

## [2.4.0] - 2026-10-21

### Eklendi
- 16.–30. ele geçirme vektörleri: Kakao Disk kabuk entegrasyonu (simge
  kaplamaları + bağlam menüsü işleyicileri), devre dışı otostart
  (`StartupApproved`), `App Paths`, kısayollar (Masaüstü / Başlat Menüsü /
  görev çubuğu), kalıntı dizinleri (ProgramData, Roaming, Kakao Disk
  verileri ve senkronize dosyalar), `hosts` girdileri, Windows güvenlik
  duvarı kuralları, URI protokol işleyicileri, tarayıcı eklentileri
  (Chromium manifestleri + Firefox `.xpi`), kakao.ru çerezleri (Chromium
  + Firefox), `OpenWithProgids`/`OpenWithList` ilişkilendirmeleri,
  Prefetch / CrashDumps / WER izleri, Windows Defender istisnaları,
  özel klavye düzenleri (Kakao IME)
- Onay mekanizması: kullanıcı verilerine dokunan bulgular (Kakao Disk
  dosyaları, Kakao IME Switcher geçmişi, eklentiler, çerezler, Defender
  istisnaları) kaldırmadan önce açık ek onay gerektirir
- `.lnk` bayt tespiti, hosts satır filtreleme, güvenlik duvarı çıktısı
  ayrıştırma ve onay öneki kapsamı için birim testler

## [2.3.0] - 2026-10-20

### Eklendi
- 13.–15. ele geçirme vektörleri: Windows hizmetleri (kayıt defteri
  tabanlı tarama, `sc stop` + `sc delete` ile kaldırma), Kakao IME Switcher
  (`ime` işaretiyle tespit), dosya ilişkilendirmeleri
  (`FileExts\<ext>\UserChoice` ProgId taraması + kaldırma)
- Tarama sonrası seçim diyaloğu: «hepsi ya da hiçbiri» yerine tam olarak
  hangi bulguların kaldırılacağını seçme
- Hariç tutmalar: işareti kaldırılan bulgular
  `%APPDATA%\AntiKakaoVanced\exclusions.json` içine kaydedilebilir —
  gelecekteki taramalar bunları otomatik olarak seçmez, ancak diyalogda
  seçilebilir kalırlar; hariç tutmalar diyalogdan sıfırlanabilir
- Hariç tutma kalıcılığı ve Kakao IME Switcher işareti için birim testler

## [2.2.0] - 2026-10-20

### Eklendi
- Kaldırmadan önce yedek: dokunulan her kayıt defteri anahtarı / profil
  dosyası silmeden önce
  `%APPDATA%\AntiKakaoVanced\backup\<timestamp>\` içine dışa aktarılır
- İşlem günlüğü: `%APPDATA%\AntiKakaoVanced\antikakao.log`
- 12. ele geçirme vektörü: Windows Görev Zamanlayıcı girdileri (Kakao
  güncelleyici görevleri)
- HKCU Chromium ilke taraması/temizliği (kullanıcı başına ilkeler, daha
  önce yalnızca HKLM)
- Başlangıçta yönetici hakları kontrolü, durum çubuğunda uyarıyla
- Ele geçirme kaldırmadan önce çalışan tarayıcıları kapatma istemi
  («database locked» engeller)
- Bazı ele geçirme öğeleri kaldırılamadığında «rapor klasörünü aç» önerisi
- Saf mantık için birim testler (motor arama, Firefox policies.json,
  LZ4 açıcı)

### Düzeltildi
- Arka plan iş parçacıklarından gelen tüm UI güncellemeleri artık
  `root.after` aracılığıyla ana iş parçacığına yönlendirilir (tkinter iş
  parçacığı güvenli değildir)
- Çıplak `except:` blokları `except OSError` ile değiştirildi
- Web Data temizliği artık tam olarak tespit edilen satırları siler
  (`rowid` ile), URL alt dizesine göre değil — tespit ve silme tutarlıdır
- SQLite bağlantıları hata yollarında kapatılır (`finally`)
- Firefox `policies.json` artık `null` `SuggestURLTemplate` içermiyor
- Firefox ilkeleri artık var olmayan kurulum klasörlerine yazılmıyor
- Sert kodlanmış Rusça yönetici hata metni, 10 UI dilinde çevrilebilir
  bir anahtarla değiştirildi
- `shutil.rmtree` artık genel bir hata yerine hangi dosyaların kilitli
  olduğunu raporlar
- Geçersiz eşleşme ofsetleri olan bozuk LZ4 blokları çöp döndürmek yerine
  istisna fırlatır

## [2.1.2] - 2026-10-20

### Değiştirildi
- Uygulama başlığı «Удаление Kakao» / «Remove Kakao» (ru/en/uk) olarak
  kısaltıldı
- Alt bilgi sağ alt köşeye sabitlendi: yazar, sürüm ve tıklanabilir
  GitHub bağlantısı
- Depo bağlantısı `https://github.com/retvil/AntiKakaoVanced` olarak
  ayarlandı

## [2.1.0] - 2026-10-20

### Eklendi
- Dikey pencere düzeni (560×700): ortalanmış eylem yığını, tam genişlikte
  bölüm kartları
- **ttkbootstrap** üzerinde açık tema (`flatly`) — CustomTkinter yerine
  daha hafif bir ttk yığını
- Yazar, sürüm ve tıklanabilir GitHub deposu bağlantısı içeren alt bilgi

### Değiştirildi
- UI kitaplığı göçü: tkinter → CustomTkinter → ttkbootstrap
- Dil seçici sağ üst köşeye taşındı

## [2.0.0] - 2026-10-20

[TheCawa/AntiKakao](https://github.com/TheCawa/AntiKakao) 1.3 çatalı.

### Eklendi
- **Arama ele geçirme tarayıcısı** — Kakao'in varsayılan
  arama/tarayıcı olarak kurulmasını sağlayan 11 vektörü tespit eder:
  - diskteki kurulum dizinleri
  - kayıt defterindeki Uninstall girdileri (HKLM, WOW6432Node, HKCU)
  - Windows varsayılan tarayıcı ilişkilendirmesi (http/https için
    `UserChoice` ProgId)
  - `StartMenuInternet` tarayıcı istemci kayıtları
  - bağımsız `Software\Kakao` anahtar ağaçları (HKCU/HKLM/WOW6432Node)
  - `DefaultSearchProvider*` enterprise ilkeleri üzerinden ele geçirme
    (Kakao'in kendini dayattığı «sert» yol)
  - Chromium profillerinin profil başına `Preferences` JSON'u (Chrome,
    Edge, Brave, Vivaldi, Kakao Browser)
  - Chromium `Web Data` SQLite veritabanlarındaki arama motoru anahtar
    kelime satırları
  - Firefox/Waterfox `search.json.mozlz4` (yerleşik pure-Python LZ4 blok
    açıcı ile)
  - legacy IE/Windows `SearchScopes` girdileri
  - otostart girdileri (`Run`/`RunOnce`)
- **Ele geçirme kaldırma** — tespit edilen her vektörün tek tıkla
  kaldırılması, her vektörün kendi remover'ı vardır: kayıt defteri
  anahtarlarının özyinelemeli silinmesi, `UserChoice` sıfırlama,
  `Preferences` temizliği, Web Data içinde `DELETE FROM keywords`,
  `search.json.mozlz4` sıfırlama (Firefox varsayılanları yeniden
  oluşturur), otostart değerlerinin silinmesi. Kilitli
  veritabanları/dosyalar (tarayıcı çalışıyor) raporlanır, çökme yok.
- **Sert varsayılan arama politikası** — 10 arama motorundan birini
  zorunlu kılar (Google, Bing, DuckDuckGo, Brave Search, Startpage,
  Mojeek, Qwant, Ecosia, Yahoo, SearXNG):
  - Chromium ailesi HKLM `SOFTWARE\Policies\...` `DefaultSearchProvider*`
    değerleriyle (Chrome, Edge, Brave, Vivaldi, Opera, Kakao Browser)
  - Firefox/Waterfox `distribution\policies.json` ile (`SearchEngines` +
    `LockDefaultSearchEngine` + `PreventSearchEngineInstall`)
- **«Kakao ilkelerini kaldır»** düğmesi — Kakao `DefaultSearchProvider*`
  ilke değerlerini kayıt defterinden temizler
- **10 UI dili** (ru, en, uk, kk, de, fr, es, pl, tr, zh) ayrılmış
  `translations.py` modülünde; sistem dili Windows UI language API
  aracılığıyla otomatik algılanır (`GetUserDefaultUILanguage`), eşleşme
  yoksa İngilizceye düşer
- UI'da dil değiştirme açılır listesi

### Değiştirildi
- Kod modüllere bölündü: `engines.py`, `kakao_detect.py`, `policies.py`,
  `translations.py`, `main.py`

## [1.3.0] - upstream

[TheCawa/AntiKakao](https://github.com/TheCawa/AntiKakao) tabanı:
- Kakao Browser süreçlerinin sonlandırılması (`browser.exe`, `kakao.exe`)
- Kurulum yollarının aranması
- Kayıt defterindeki Uninstall girdilerinin temizlenmesi
- Tarayıcı klasörünün silinmesi
- RU/EN arayüz anahtarı

[Unreleased]: https://github.com/retvil/AntiKakaoVanced/compare/v2.1.2...HEAD
[2.1.2]: https://github.com/retvil/AntiKakaoVanced/compare/v2.1.0...v2.1.2
[2.1.0]: https://github.com/retvil/AntiKakaoVanced/compare/v2.0.0...v2.1.0
[2.0.0]: https://github.com/retvil/AntiKakaoVanced/compare/v1.3.0...v2.0.0
