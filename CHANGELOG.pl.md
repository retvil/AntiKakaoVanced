# Dziennik zmian

Wszystkie istotne zmiany w tym projekcie są dokumentowane w tym pliku.

Format oparty jest na [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
a projekt stosuje [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

> Źródłem prawdy jest angielski [CHANGELOG.md](CHANGELOG.md); to tłumaczenie może lekko odstawać.

## [2.8.0] - 2026-10-22

### Dodano
- **Skan mapy stref IE (zone map)** — wykrywa wpisy zone-map dla domen
  Kakao (pozostałości „zaufanych witryn”); usunięcie kasuje poddrzewo
  domeny (najpierw eksport)
- **Skan RegisteredApplications** — wykrywa wpisy Kakao w metadanych
  aplikacji domyślnych; usunięcie kasuje wartość (najpierw eksport)
- **Skan MUICache** — wykrywa ślady uruchamiania plików wykonywalnych
  Kakao; usunięcie kasuje wartość cache (najpierw eksport)
- **Ślady instalatorów w %TEMP%** — scan_traces zgłasza teraz także
  instalatory Kakao pozostawione w folderze tymczasowym użytkownika
- **Katalogi produktów per-user** — scan_product_dirs obejmuje teraz także
  `%LOCALAPPDATA%\Programs\Kakao*` (instalacje legacy Kakao Music /
  Messenger / Translate), folder przeglądarki wykluczony
- **Kill procesów po ścieżce (Vanced)** — kill przeglądarki dopasowuje
  teraz także procesy, których exe leży pod ścieżką KakaoBrowser
  (crashpad, updater), nie tylko wąską listę nazw browser.exe/kakao.exe
- **Skan przejęcia adresów startowych** — wykrywa URL Kakao w politykach
  enterprise `RestoreOnStartupURLs` (Edge, Chrome, Chromium, Brave,
  Vivaldi, Opera, Kakao Browser); usunięcie czyści wartości Kakao
- **Skan przejęcia strony domowej Firefox** — wykrywa
  `browser.startup.homepage` wskazujące na Kakao w `prefs.js`
  Firefox/Waterfox; usunięcie przepisuje plik (najpierw kopia zapasowa)

## [2.7.0] - 2026-10-21

### Dodano
- **Skan Kakao.DNS** (Extended) — wykrywa adaptery sieciowe skonfigurowane
  z serwerami DNS Kakao (77.88.8.x basic/safe/family); usunięcie przywraca
  adapterowi automatyczny DNS; z potwierdzeniem
- **Skan przejęcia strony startowej** — wykrywa legacy stronę startową IE
  (`HKCU\...\Internet Explorer\Main\Start Page`) wskazującą na
  Kakao/kakao.com; usunięcie przywraca domyślną (oba wydania)

## [2.6.0] - 2026-10-21

### Dodano
- **Wydanie Extended**: skan aplikacji Store (Appx) — wykrywa Kakao Music,
  Messenger, Messenger i inne aplikacje Store Kakao, usuwa je przez
  `Remove-AppxPackage`
- **Wydanie Extended**: skan katalogów produktów nieprzeglądarkowych pod
  `Program Files\Kakao\` (Kakao Disk, Kakao IME Switcher, IME, ...) z kopią
  zapasową przed usunięciem
- **Wydanie Extended**: skan lokalnych danych nieprzeglądarkowych pod
  `%LOCALAPPDATA%\Kakao\` (lokalne dane Kakao IME Switcher, updater Kakao
  Disk, buildy Beta) — z potwierdzeniem, kopia zapasowa przed usunięciem
- **Wydanie Extended**: „Kill Processes” kończy teraz procesy wszystkich
  produktów Kakao (Kakao Disk, Kakao IME Switcher, aplikacje Store), nie
  tylko przeglądarki

## [2.5.0] - 2026-10-21

### Dodano
- Dwa wydania z jednej bazy kodu: **AntiKakaoVanced** (usunięcie Kakao
  Browser + Kakao Search) i **AntiKakaoExtended** (wszystkie produkty
  Kakao) — profile produktów w `profiles.py` wybierają zakres skanu,
  wspólny GUI w `app.py`, cienkie punkty wejścia `main.py` /
  `main_extended.py`
- `build.bat` buduje teraz oba EXE

## [2.4.0] - 2026-10-21

### Dodano
- Wektory przejęcia 16–30: integracja powłoki Kakao Disk (nakładki ikon +
  handlery menu kontekstowego), wyłączony autostart (`StartupApproved`),
  `App Paths`, skróty (Pulpit / Menu Start / pasek zadań), katalogi
  pozostałości (ProgramData, Roaming, dane Kakao Disk i zsynchronizowane
  pliki), wpisy `hosts`, reguły zapory Windows, handlery protokołów URI,
  rozszerzenia przeglądarek (manifesty Chromium + `.xpi` Firefox),
  ciasteczka kakao.ru (Chromium + Firefox), asocjacje
  `OpenWithProgids`/`OpenWithList`, ślady Prefetch / CrashDumps / WER,
  wyjątki Windows Defender, niestandardowe układy klawiatury (Kakao IME)
- Potwierdzenie zgody: znaleziska dotykające danych użytkownika (pliki
  Kakao Disk, historia Kakao IME Switcher, rozszerzenia, ciasteczka, wyjątki
  Defender) wymagają jawnego dodatkowego potwierdzenia przed usunięciem
- Testy jednostkowe dla detekcji bajtów `.lnk`, filtrowania linii hosts,
  parsowania wyjścia zapory i pokrycia prefiksów zgody

## [2.3.0] - 2026-10-20

### Dodano
- Wektory przejęcia 13–15: usługi Windows (skan po rejestrze, usuwanie
  przez `sc stop` + `sc delete`), Kakao IME Switcher (detekcja po markerze
  `ime`), skojarzenia plików (skan + usunięcie ProgId w
  `FileExts\<ext>\UserChoice`)
- Dialog wyboru po skanie: wybór dokładnie, które znaleziska usunąć,
  zamiast „wszystko albo nic”
- Wykluczenia: odznaczone znaleziska można zapisać do
  `%APPDATA%\AntiKakaoVanced\exclusions.json` — przyszłe skany automatycznie
  je odznaczają, ale pozostają wybieralne w dialogu; wykluczenia można
  zresetować z dialogu
- Testy jednostkowe persystencji wykluczeń i markera Kakao IME Switcher

## [2.2.0] - 2026-10-20

### Dodano
- Kopia zapasowa przed usunięciem: każdy dotknięty klucz rejestru / plik
  profilu jest eksportowany do
  `%APPDATA%\AntiKakaoVanced\backup\<timestamp>\` przed usunięciem
- Dziennik operacji: `%APPDATA%\AntiKakaoVanced\antikakao.log`
- Wektor przejęcia 12: wpisy Harmonogramu zadań Windows (zadania updateera
  Kakao)
- Skan/czyszczenie polityk Chromium HKCU (polityki per-user, wcześniej
  tylko HKLM)
- Sprawdzenie praw administratora przy starcie z ostrzeżeniem na pasku
  statusu
- Podpowiedź zamknięcia uruchomionych przeglądarek przed usunięciem
  przejęć (zapobiega „database locked”)
- Propozycja „otwórz folder raportu”, gdy część elementów przejęcia nie
  dała się usunąć
- Testy jednostkowe czystej logiki (wyszukiwanie silnika, Firefox
  policies.json, dekompresor LZ4)

### Naprawiono
- Wszystkie aktualizacje UI z wątków w tle są teraz marshlowane do wątku
  głównego przez `root.after` (tkinter nie jest thread-safe)
- Gołe klauzule `except:` zastąpione przez `except OSError`
- Czyszczenie Web Data usuwa teraz dokładnie wykryte wiersze (po `rowid`),
  a nie po podciągu URL — detekcja i usuwanie są spójne
- Połączenia SQLite zamykane na ścieżkach błędów (`finally`)
- Firefox `policies.json` nie zawiera już `null` `SuggestURLTemplate`
- Polityki Firefox nie są już zapisywane do nieistniejących folderów
  instalacji
- Zakodowany na sztywno rosyjski komunikat błędu admina zastąpiony
  tłumaczalnym kluczem we wszystkich 10 językach UI
- `shutil.rmtree` zgłasza teraz, które pliki są zablokowane, zamiast
  ogólnego błędu
- Uszkodzone bloki LZ4 z nieprawidłowymi offsetami dopasowań rzucają
  wyjątek zamiast zwracać śmieci

## [2.1.2] - 2026-10-20

### Zmieniono
- Tytuł aplikacji skrócony do „Удаление Kakao” / „Remove Kakao”
  (ru/en/uk)
- Stopka przypięta do prawego dolnego rogu: autor, wersja i klikalny link
  do GitHub
- Link repozytorium ustawiony na `https://github.com/retvil/AntiKakaoVanced`

## [2.1.0] - 2026-10-20

### Dodano
- Pionowy układ okna (560×700): wyśrodkowany stos akcji, karty sekcji na
  pełną szerokość
- Jasny motyw UI na **ttkbootstrap** (motyw `flatly`) — CustomTkinter
  zastąpiony lżejszym stosem ttk
- Stopka z autorem, wersją i klikalnym linkiem do repozytorium GitHub

### Zmieniono
- Migracja biblioteki UI: tkinter → CustomTkinter → ttkbootstrap
- Selektor języka przeniesiony do prawego górnego rogu

## [2.0.0] - 2026-10-20

Fork [TheCawa/AntiKakao](https://github.com/TheCawa/AntiKakao) 1.3.

### Dodano
- **Skaner przejęć wyszukiwania** — wykrywa 11 wektorów, którymi Kakao
  instaluje się jako domyślna wyszukiwarka/przeglądarka:
  - katalogi instalacji na dysku
  - wpisy Uninstall w rejestrze (HKLM, WOW6432Node, HKCU)
  - asocjacja domyślnej przeglądarki Windows (ProgId `UserChoice` dla
    http/https)
  - rejestracje klientów przeglądarek `StartMenuInternet`
  - samodzielne drzewa kluczy `Software\Kakao` (HKCU/HKLM/WOW6432Node)
  - przejęcie przez polityki enterprise `DefaultSearchProvider*` (twardy
    sposób, w jaki Kakao się narzuca)
  - JSON `Preferences` profili Chromium (Chrome, Edge, Brave, Vivaldi,
    Kakao Browser)
  - wiersze słów kluczowych wyszukiwarek w bazach SQLite `Web Data`
    Chromium
  - Firefox/Waterfox `search.json.mozlz4` (z wbudowanym dekompresorem
    bloków LZ4 w czystym Pythonie)
  - legacy wpisy `SearchScopes` IE/Windows
  - wpisy autostartu (`Run`/`RunOnce`)
- **Usuwanie przejęć** — usuwanie wszystkich wykrytych wektorów jednym
  kliknięciem, każdy wektor ma własny remover: rekurencyjne usuwanie kluczy
  rejestru, reset `UserChoice`, czyszczenie `Preferences`,
  `DELETE FROM keywords` w Web Data, reset `search.json.mozlz4` (Firefox
  odbudowuje domyślne), usuwanie wartości autostartu. Zablokowane
  bazy/pliki (przeglądarka uruchomiona) są raportowane, bez crashy.
- **Twarda polityka domyślnej wyszukiwarki** — wymusza jedną z 10
  wyszukiwarek (Google, Bing, DuckDuckGo, Brave Search, Startpage, Mojeek,
  Qwant, Ecosia, Yahoo, SearXNG):
  - rodzina Chromium przez wartości HKLM `SOFTWARE\Policies\...`
    `DefaultSearchProvider*` (Chrome, Edge, Brave, Vivaldi, Opera,
    Kakao Browser)
  - Firefox/Waterfox przez `distribution\policies.json` (`SearchEngines` +
    `LockDefaultSearchEngine` + `PreventSearchEngineInstall`)
- Przycisk **„Usuń polityki Kakao”** — czyści wartości polityk
  `DefaultSearchProvider*` Kakao z rejestru
- **10 języków UI** (ru, en, uk, kk, de, fr, es, pl, tr, zh) w dedykowanym
  module `translations.py`; język systemu wykrywany automatycznie przez
  Windows UI language API (`GetUserDefaultUILanguage`), fallback na
  angielski
- Rozwijana lista zmiany języka w UI

### Zmieniono
- Kod podzielony na moduły: `engines.py`, `kakao_detect.py`,
  `policies.py`, `translations.py`, `main.py`

## [1.3.0] - upstream

Baza [TheCawa/AntiKakao](https://github.com/TheCawa/AntiKakao):
- Zakończenie procesów Kakao Browser (`browser.exe`, `kakao.exe`)
- Wyszukiwanie ścieżek instalacji
- Czyszczenie wpisów Uninstall w rejestrze
- Usuwanie folderu przeglądarki
- Przełącznik interfejsu RU/EN

[Unreleased]: https://github.com/retvil/AntiKakaoVanced/compare/v2.1.2...HEAD
[2.1.2]: https://github.com/retvil/AntiKakaoVanced/compare/v2.1.0...v2.1.2
[2.1.0]: https://github.com/retvil/AntiKakaoVanced/compare/v2.0.0...v2.1.0
[2.0.0]: https://github.com/retvil/AntiKakaoVanced/compare/v1.3.0...v2.0.0
