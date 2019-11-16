S14 Technologie komunikacji bezprzewodowej w urządzeniach mobilnych

# GSM
## 2G
### GPRS
### EDGE
## 3G
### UMTS
### HSDPA
### HSPA+

## Wi-Fi
## Bluetooth
sieć typu PAN (Personal Area Network), początki ok. 1994
Wykorzystuje pasmo 2.4GHz, opiera się na architekturze master-slave: jedno urządzenie nadrzędne kontroluje kilka urządzeń podrzędnych. Dane przesyłane sa pakietowo wg zegara mastera.

Przy pierwszym połączeniu z nowym urzadzeniem trzeba je **sparować**.
Jak urządzenia są w trybie **widoczności** to można pozyskać info o jego:
nazwie, typie, udostępnianych usługach (np. transfer, słuchawki, whatever), szczegoly techniczne np. producent.

Urządzenia podczas parowania wymieniają się kluczem przy pomocy ktorego szyfrują swoje połączenie. Usunięcie klucza wymaga ponownego parowania.

Od wersji 2.1 jest **Secure Simple Pairing** ktore nie wymaga podawania PINu podczas parowania - z myślą o słuchawkach, gamepadach, ktore nie mają klawiatury - wystarcz proste potwierdzenie.


Nasluchiwanie (Sniffing) - okresowo urządzenie podrzędne nasłuchuje czy przyszły nowe informacje od mastera np. co 30ms

Wstrzymanie (Hold) - urz. przestaje komunikować się na pewien czas (np. 500ms) - pozwala oszczędzić dodatkowo baterię

Parkowanie (Parking) - urządzenie tymaczasowo opuszcza sieć (max 40s). Adres zostaje zwolniony i może zostać użyty przez inne urz. Takie zaparkowane dostają adres z osobnej specjalnej przeznaczonej do tego puli - wtedy master może przywrócić je do sieci.

Przepustowość:

| wersja        | teoretycznie           | praktycznie  |
| ------------- |:-------------:| -----:|
| 1.1/1.2      | 1 Mbps | 0.7 Mbps |
| 2.0/2.1      | 3 Mbps (EDR)      |   2.1 Mbps |
| 3.0 | 24 Mbps (High Speed, 802.11)      |    |
| 4.0/1/2 |       |    |
| 5.0/1 |       |    |
| Low Energy | 1 Mbps | 0.26 Kbps |

Implementacja EDR i High Speed są częścią standardu ale sa opcjonalne

Low Energy - nowy protokół dla urządzeń o bardzo małej mocy (np. zegarka)
Urządzenia z 4.0 mogą wybierać spośród: Classic, High Speed, BLE.
Też wykorzystuje pasmo 2.5 GHz, rożni się jednak szerokością kanału i typem modulacji. Max zasięg powyżej **100m**. BLE w wersjach 4.1, 4.2 wspiera połączenia IPv6 oraz szyfrowanie protokołem AES 128-bit. Prekursor koncepcji IoT

5.0 - 4x szybszy, 4x wiekszy zasieg od 4-tej generacji. Usunięto tryb parkowania, dodano wysyłanie danych do 2 urządzeń na raz (np. głośników)

Bluetooth i Wi-Fi dzielą to samo pasmo, dlatego żeby sie nie zagłuszały to Bluetooth korzusta z **metody rozpraszania widma** (Frequency Hopping Spread Spectrum). Kanały zmieniane są ok. 800 razy w ciągu sekundy

## iBeacons
Applowe, oparte na Bluetooth LE

## NFC (Near Field Communication)

Standard komunikacji krótkiego zasięgu. Opiera się na technologii RFID - pasywne znaczniki elektroniczne aktywowane falami radiowymi. Są rózne rodzaje tagów, więc to tez bywa różnie - są też aktywne.

Działa na zasadzie indukcji magnetycznej, korzysta z pasma 13.56 MHz
Max zasięg (zależy od standardu) to np. 20m
Prędkości przesyłu max 0.8 Mbps

![image](https://user-images.githubusercontent.com/12485656/68997726-c40e7b00-08a9-11ea-92f1-38f46f2f17a8.png)


## Push notification, strumieniowanie, Websockets
Wysyłanie info z **serwera do klienta**
Komunikacja zachodzi tylko wtedy gdy jest potrzeba wysłania czegoś. Oszczędza to energie i zasoby. Połączenie jest zestawiane raz (permanentnie) - żeby nie musiało być w kółko wznawiane. Przeznaczone raczej do krótkich informacji (np. powiadomień, chatu). 

Mobilne architektury pusha:
- Apple Push Notification Service (APN) - max 4 kB
- Firebase Cloud Messaging (FCM)
- Openmarket Push Notifications - jednolite API dla obu platform


Beacons vs. NFC
* Obie technologie wspierają płatności mobilne w sklepach. 
* Beacons to małe bezprzewodowe czujniki, które komunikują się ze smartfnem za pomocą Bluetooth Low Energy (BLE), a NFC używa fali radiowych o krótkim zakresie, co pozwala na wymianę informacji pomiędzy dwoma urządzeniami w bliskiej odległości. 
* iBeacons mają zakres 50 m, optymalny zakres dla NFC to 4cm. 
* Beacons mogą wysyłać powiadomienia push, z informacją o ofertach, położeniu czy też ze spersonalizowanymi oferta na podstawie historii zakupów/preferencji klienta. W przypadku NFC to klient musi zainicjować interakcję z NFC.  
* Nie wszystkie telefony posiadają NFC, za to większość posiada Bluetooth.  
* NFC wspiera szyfrowanie, ponadto ryzyko shakowania jest niewielkie ze względu na niewielką odległość pomiędzy urządzeniami.
