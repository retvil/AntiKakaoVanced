# AntiKakao Vanced

**🇬🇧 English** | [🇷🇺 Русский](README.ru.md) | [🇺🇦 Українська](README.uk.md) | [🇰🇿 Қазақша](README.kk.md) | [🇩🇪 Deutsch](README.de.md) | [🇫🇷 Français](README.fr.md) | [🇪🇸 Español](README.es.md) | [🇵🇱 Polski](README.pl.md) | [🇹🇷 Türkçe](README.tr.md) | [🇨🇳 中文](README.zh.md)

## 🌐 Forks

<a href="https://github.com/retvil/AntiBaiduVanced"><img src="https://raw.githubusercontent.com/retvil/AntiBaiduVanced/main/logo.png" alt="AntiBaiduVanced" width="16" height="16" style="vertical-align:middle"> AntiBaiduVanced</a>  |  <a href="https://github.com/retvil/AntiSogouVanced"><img src="https://raw.githubusercontent.com/retvil/AntiSogouVanced/main/logo.png" alt="AntiSogouVanced" width="16" height="16" style="vertical-align:middle"> AntiSogouVanced</a>  |  <a href="https://github.com/retvil/Anti2345Vanced"><img src="https://raw.githubusercontent.com/retvil/Anti2345Vanced/main/logo.png" alt="Anti2345Vanced" width="16" height="16" style="vertical-align:middle"> Anti2345Vanced</a>  |  <a href="https://github.com/retvil/AntiUCWebVanced"><img src="https://raw.githubusercontent.com/retvil/AntiUCWebVanced/main/logo.png" alt="AntiUCWebVanced" width="16" height="16" style="vertical-align:middle"> AntiUCWebVanced</a>  |  <a href="https://github.com/retvil/AntiNaverVanced"><img src="https://raw.githubusercontent.com/retvil/AntiNaverVanced/main/logo.png" alt="AntiNaverVanced" width="16" height="16" style="vertical-align:middle"> AntiNaverVanced</a>  |  **AntiKakaoVanced**  |  <a href="https://github.com/retvil/AntiQQVanced"><img src="https://raw.githubusercontent.com/retvil/AntiQQVanced/main/logo.png" alt="AntiQQVanced" width="16" height="16" style="vertical-align:middle"> AntiQQVanced</a>  |  <a href="https://github.com/retvil/AntiWeChatVanced"><img src="https://raw.githubusercontent.com/retvil/AntiWeChatVanced/main/logo.png" alt="AntiWeChatVanced" width="16" height="16" style="vertical-align:middle"> AntiWeChatVanced</a>  |  <a href="https://github.com/retvil/AntiTencentVideoVanced"><img src="https://raw.githubusercontent.com/retvil/AntiTencentVideoVanced/main/logo.png" alt="AntiTencentVideoVanced" width="16" height="16" style="vertical-align:middle"> AntiTencentVideoVanced</a>  |  <a href="https://github.com/retvil/AntiVKGroupVanced"><img src="https://raw.githubusercontent.com/retvil/AntiVKGroupVanced/main/logo.png" alt="AntiVKGroupVanced" width="16" height="16" style="vertical-align:middle"> AntiVKGroupVanced</a>  |  <a href="https://github.com/retvil/AntiYandexVanced"><img src="https://raw.githubusercontent.com/retvil/AntiYandexVanced/main/logo.png" alt="AntiYandexVanced" width="16" height="16" style="vertical-align:middle"> AntiYandexVanced</a>

## Bu nedir?

Kakao yalnızca bir tarayıcı kurmaz — kırk farklı sistem mekanizmasıyla sessizce varsayılan arama ve tarayıcı olarak kaydolur: kayıt defteri ilişkilendirmeleri, enterprise ilkeleri, tarayıcı profil ayarları, hatta Chromium profillerinin içindeki arama motoru veritabanları. Tarayıcıyı tek başına kaldırmak bunların hepsini geri almaz.

**AntiKakao Vanced** ([retvil/AntiYandexVanced](https://github.com/retvil/AntiYandexVanced) çatalı) **40 ele geçirme vektörünün tamamını** bulur, tek tıkla kaldırır ve ardından varsayılan aramanızı seçtiğiniz arama motoruna Windows enterprise ilkeleriyle **sabit şekilde kilitler** — hiçbir şey sessizce geri alamasın diye.

## Özellikler

- **Ele geçirme tarayıcısı** — 28/39 vektörü tespit eder: kurulum yolları, kayıt defterindeki Uninstall girdileri, `UserChoice` ilişkilendirmesi, `StartMenuInternet` kayıtları, `Software\Kakao` anahtar ağaçları, `DefaultSearchProvider*` ilkeleri üzerinden ele geçirme, Chromium profillerinin `Preferences` ayarları, `Web Data` (SQLite) anahtar kelimeleri, Firefox `search.json.mozlz4`, legacy `SearchScopes`, autostart girdileri, zamanlanmış görevler, Windows hizmetleri, IME Switcher, dosya ilişkilendirmeleri, Kakao Disk kabuk entegrasyonu, devre dışı otostart, App Paths, kısayollar, ProgramData/Roaming kalıntıları, hosts girdileri, güvenlik duvarı kuralları, URI protokolleri, tarayıcı eklentileri, kakao.ru çerezleri, „birlikte aç“ ilişkilendirmeleri, Prefetch/WER izleri, Defender istisnaları, klavye düzenleri, IE başlangıç sayfası ele geçirmesi, başlangıç URL ilkeleri (`RestoreOnStartupURLs`), Firefox ana sayfası, IE bölge haritası, RegisteredApplications girdileri, MUICache izleri, %TEMP% yükleyicileri, Store uygulamaları (Kakao Music), ürün dizinleri, yerel veri dizinleri, Kakao.DNS
- **Tek tıkla kaldırma** — her vektörün kendi remover'ı vardır; kilitli veritabanları dürüstçe raporlanır, çökme yok
- **Sabit arama politikası** — varsayılan aramayı 10 arama motorundan birine (Google, Bing, DuckDuckGo, Brave Search, Startpage, Mojeek, Qwant, Ecosia, Yahoo, SearXNG) kilitler: Chrome, Edge, Brave, Vivaldi, Opera ve Kakao Browser için HKLM ilkeleri + Firefox/Waterfox için `policies.json`
- **Politika temizliği** — Kakao `DefaultSearchProvider*` değerlerini kayıt defterinden temizler
- **10 arayüz dili** — ru, en, uk, kk, de, fr, es, pl, tr, zh; sistem dili otomatik algılanır
- **Hafif arayüz** — ttkbootstrap, dikey düzen, sabitlenmiş durum çubuğu ve alt bilgi

## Ekran görüntüsü

<details>
<summary>Ana pencere</summary>

![AntiKakaoVanced ana penceresi](docs/screenshot.png)

</details>

## Hazır derlemeler

[Releases](https://github.com/retvil/AntiKakaoVanced/releases) sayfasından indirin:

- **Windows** — `AntiKakaoVanced.exe` (taşınabilir, tek dosya, ~35 MB) — Kakao Browser ve Kakao Arama kaldırma
- **Windows** — `AntiKakaoExtended.exe` (taşınabilir, tek dosya, ~35 MB) — tüm Kakao ürünlerinin kaldırılması (Kakao Disk, IME Switcher geçmişi, sistem genelinde izler, Store uygulamaları, Kakao.DNS)

**Yönetici olarak** çalıştırın — HKLM ilkeleri ve kayıt defteri temizliği yükseltilmiş haklar gerektirir.

## Kaynak koddan kurulum

Python 3.10+ gerekli ([python.org](https://python.org)).

```bash
git clone https://github.com/retvil/AntiKakaoVanced.git
cd AntiKakaoVanced
pip install psutil ttkbootstrap
python main.py
```

Kendi EXE'nizi derlemek için: `build.bat` çalıştırın (PyInstaller, çıktı `dist/` içinde).

## Kullanım

1. **İşlemleri sonlandır** → **Kakao'i ara** → **Kakao'i sil** — tarayıcının kendisini kaldırıyoruz.
2. **Arama ele geçirmelerini tara** — Kakao'in sisteme nasıl kök saldığının tüm yollarını gösterir.
3. **Ele geçirmeleri kaldır** — önce tüm tarayıcıları kapatın, sonra bulunan her şeyi kaldırın.
4. Bir motor seçin → **Politikayı uygula** — varsayılan arama sistem düzeyinde kilitlendi.

## SSS

- **Neden yönetici?** Arama politikaları HKLM'de yaşar, temizlik sistem kayıt defterine dokunur — yükseltilmiş haklar gerekir.
- **Sonuçlarda «Database locked»?** Temizlik sırasında bir Chromium tarayıcısı çalışıyordu. Tüm tarayıcıları kapatın ve kaldırmayı tekrarlayın.
- **Arama politikasını nasıl kaldırırım?** **Kakao politikalarını kaldır** düğmesi politika değerlerini temizler; Firefox'ta ayrıca `distribution\policies.json` dosyasını silebilirsiniz.

## Yazar ve destek

Изначальная идея: [TheCawa/AntiYandex](https://github.com/TheCawa/AntiYandex)

Araç sizi Kakao'ten kurtardıysa, geliştirmeyi destekleyebilirsiniz:

**Kripto:**

- BTC: `bc1qunld3rsp37qf5gg69aune50y0qqkd0eugg7j97`
- TON: `UQDmvr4SKOxSION3Yky6aOgzAnCDXySPuAbG4EKJa5JUT7tC`
- USDT (TRC20): `TBPJSSLu1mUcX54g9UyxUohYGf2fuRvbwd`
- USDT (ERC20): `0x25CAED3776Ef5b18E03392bC5b254Bbd78E8180C`
- USDT (SOL): `3qgN5z291CEcj2FUi2Zza5DioxKgNw72kC7P52pCcTrG`

## Lisans

MIT — bkz. [LICENSE](LICENSE).



