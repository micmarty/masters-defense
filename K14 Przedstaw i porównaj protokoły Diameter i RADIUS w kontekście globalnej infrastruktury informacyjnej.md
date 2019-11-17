# K14 Przedstaw i porównaj protokoły Diameter i RADIUS w kontekście globalnej infrastruktury informacyjnej.md
https://sekurak.pl/bezpieczenstwo-sieci-wi-fi-czesc-8-wpawpa2-enterprise-radius/
https://pg.edu.pl/documents/1112617/28513726/Uwierzytelnianie.pdf

Zarówno RADIUS i DIAMETER to **protokoły sieciowe** do uwierzytelniania, autoryzacji i rozliczalności użytkowników czyli tzw. **AAA - Authentication, Authorization, Accountability**.

Oba są wykorzystywane np. przez **ISP, uczelnie, firmy w celu kontroli dostępu do Internetu**, albo podliczania transferów i czasu.

Dają możliwość realizacji zarządzania i kontroli dostępu użytkowników, w zależności od wielu parametrów, np. pory dnia, dzia tygodnia, zarządzanie użytkownikiem w sieci przez przypisane do konkretnego VLAN-u itp.


Oba przetrzymują wiadomości konieczne do działania, metadane, informacje o kliencie, dane od aplikacji w tzw. AVP. 

## RADIUS
* RADIUS powstał w roku ~1991. 

* Działa w architekturze klient-serwer, na wykorzystuje UDP do komunikacji - co bywa zaletą ale częściejchyba jego wadą.
Protokół ten pozwala na realizację funkcjonalności proxy dającej możliwość komunikacji pomiędzy wieloma systemami.

* Sam protokół RADIUS nie posiada dedykowanych mechanizmów zabezpieczania transmisji, poza jedynym polegającym na tym, że transmituje hasło zakodowanie MD5 - dziś nie zapewnia to wymaganego poziomu ochrony.

* Z tego powodu opracowano protokół określany jako RadSec, którego celem jest naprawienie dwóch najpoważniejszych niedociągnięć RADIUSa. RadSec tłumaczone jest jako RADIUS over TLS. RadSec eliminuje zawodność transmisji przez użycie TCP zamiast UDP oraz zapewnia poufność wszystkich atrybutów protokołu RADIUS dzięki transmisji danych w tunelu TLS.

* RADIUS, jak każde rozwiązanie, posiada pewne mankamenty, które uwidoczniły się w ciągu ponad 20 lat jego funkcjonowania. **Jest w stanie zrealizować większość obecnych wymagań i jest do dzisiaj używany**, ale jego główne wady to:
  - brak obsługi TCP,
  - brak obsługi szyfrowania komunikacji
  - zbyt mała przestrzeń dostępnych AVP czyli atrybutów (8-bit => 256)


## Diameter
* Okolice lat 2000
* jest kompatybilny wstecznie i jest rozwinięciem/udoskolaneniem RADIUSa. 
* Implementacja to np. OpenDiameter na licencji GNU.

* Protokół Diameter nosi cechy protokołu peer-to-peer – każdy z elementów może zainicjować komunikację
w odróżnieniu od protokołu RADIUS, gdzie możliwość tę posiadał wyłącznie klient.

Cechy:
  - Bazuje na TCP (lub SCTP)
  - ma większą przestrzeń adresową "atrybut-warość" -> 4B zamiast 1Bajta
  - wykorzystuje TLS
  - wbudowane wsparcie obsługi sesji użytkownika (do działań rozliczeniowych)
  - Peer Discovery - węzeł Diameter może rozgłaszać informacje o swojej obecności, adresie, obsługiwanych realmach i aplikacjach, metodach zabezpieczeń
  - Obsługa błędów: protokołu i aplikacji, wrzucane do AVP

## Dodatki, tabele
![image](https://user-images.githubusercontent.com/12485656/69012271-3f3c6380-0974-11ea-88be-f13e66a9ccdb.png)
![image](https://user-images.githubusercontent.com/12485656/69012368-53349500-0975-11ea-8f7f-64e9385b25e7.png)

