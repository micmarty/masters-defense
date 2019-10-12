# Świadczenia usług w modelu cloud computing dla urządzeń mobilnych (STM)

Pasują do mobilnych przez swoją ideę "cienkiego" klienta.

### 1. IaaS - Infrastructure as a Service
Najprostszy model usługi w chmurze, po prostu udostępnia się dostęp do maszyn wirtualnych + narzędzia do ich zarządzania, używania zdalnie. User dostaje moc obliczeniową, jakąś przestrzeń dyskową, pamięć, moc CPU - przekłada się to na cenę usługi. Można rozliczać czasowo, albo w zależności od obciążenia, albo sztywna kwota.

**Przykłady: DigitalOcean, AWS, Azure, Google Cloud Platform**

### 2. PaaS - Platform
Zawiera zarówno sprzęt, system operacyjny, aplikację. Użytkownik nie instaluje niczego sam, dostaje gotowy produkt, wystarczy mu internet.

**Przykłady: Heroku, Magento Commerce Cloud, Google App Engine, Amazon Web Services, PythonAnywhere**

### 3. SaaS - Software
Użytkownik dostaje tylko dostęp do aplikacji, która działa sobie w chmurze z dostępem na żądanie. 
W zależności od wybranego "planu" ma więcej/mniej funkcji. User nie martwi się na jakim sprzęcie, środowisku to działa - czyli martwi się tym dostawca. Zazwyczaj płaci się w modelu abonamentowym. 

**Przykłady: Slack, Basecamp, Google Apps, Travis CI**

---
### Pomniejsze pojęcia
4. **Storage** - przestrzeń dyskowa (Dropbox, Google Cloud Storage, Google Drive, iCloud)
5. **Security** - autoryzacja, uwierzytelnianie, szyfrowanie, firewalle, ochrona antywirusowa (np. CloudFlare, ProtonMail, NordVPN)
6. **Data** - dostęp do zbiorów danych, płatne datasety (np. OpenWeatherMap)
7. **Desktop** - zdalny dostęp do pulpitu komputera w chmurze/wirtualnej maszynie (podobne do IaaS) (np. Desktone Cloud VDI, TeamViewer)
8. **API** - dostęp do interfejsów obsługujących REST, XML


### Wymogi urządzeń/platform mobilnych
- responsywność, wsparcie dla low resolutions
- multi-touch, emulacja przewijania, zoomowania, typowych gestów (np. ściąganie w doł żeby przeładować) + obsługa również standardowej myszy
- przechowywanie nie tylko lokalnie na urządzeniu, ale też synchronizowanie ustawień z cloud storage
- współpraca z innymi aplikacjami (intenty)



