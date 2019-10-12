# Implementacja standardu komunikacji bezprzewodowej 802.11ac na urządzeniach mobilnych

Następnik 802.11n (b, g, n - które należą do Wi-Fi 4)
- piąta generacjia Wi-Fi, rok 2013
- bardziej ewolucja niż rewolucja
- wstecznie kompatybilny z poprzednimi standardami
- operuje wyłącznie w paśmie 5 GHz (zamiast 2.4 jak wcześniejsze)
- Multiple Input, Multiple Output (MIMO) - wiele anten jednocześnie wysyłających i odbierających dane
- teoretycznie 1.3 Gbps (gdy 3+ anten!!!) - dlatego zwany "Gigabit Wi-Fi" = 1331 Mbps = 166 MBps (gdzie `n` dawało max. 0.45 Gbps = 450 Mbps)
- liczba anten:
	- w smartfonach zwykle jedna antena
	- w tabletach od dwóch nawet do czterech
	- laptopach cztery do ośmiu
	- iPhne XR - 2 anteny (2x2 MIMO), iPhone XS, XS Max - 4 anteny (4x4 MIMO)
	- analogia do autostrady - liczba anten/MIMO to tak jakby dołożyć pas ruchu
- pierwszy ze wsparciem dla `ac` smartfon to Samsung Galaxy S4, HTC One

![](https://ksassets.timeincuk.net/wp/uploads/sites/54/2013/06/1-1.jpg)
![](https://ksassets.timeincuk.net/wp/uploads/sites/54/2013/06/beamDiagrams-3.png)

### Udoskonalenia

#### 1. 5 GHz (mimo iż było już w 802.11n)
Zaletą przejścia na nowe pasmo jest możliwość podzielenia dostępnego spectrum na dużo więcej kanałów, niż w przypadku 2,4 GHz. To istotne o tyle, że sieci Wi-Fi są podzielone na 20 MHz kanały. Podczas gdy w paśmie 2,4 GHz dostępne były maksymalnie cztery kanały, o tyle ich liczba w 5 GHz wzrosła aż do 19, z możliwością ich łączenia w celu dostarczenia szerszego pasma dla pojedynczego urządzenia.

#### 2. Większe szerokości kanałów
Im szerszy jest kanał radiowy, tym więcej danych może być przesłanych w jednostce czasu. Technologia AC zamiast 40 MHz wykorzystuje kanały o szerokości 80, a nawet 160 MHz. Alternatywnie standard może pracować też z tak zwanym channel bondingiem - łączeniem dwóch oddzielnych kanałów.

Zwiększa jednocześnie prędkość transmisji, poprawia przepustowość sieci.
Dla 80 MHz tworzone są z dwóch sąsiadujących kanałów 40 MHz
Dla 160 MHz tworzone są z dwóch niekoniecznie sąsiadujących kanałów 80 MHz (channel bonding)

#### 3. Poprawiona modulacja
Chipsety radiowe o większej mocy obliczeniowej pozwoliły na bardziej skomplikowane metody modulacji. Limit został podniesiony z 64 QAM do 256 QAM. Przekłada się to na zakodowanie większej ilości bitów w kanale o takiej samej szerokości.

https://www.pcworld.pl/spons_dlink.html

#### 4. Multi-user MIMO
Technologia MU-MIMO - pozwala stacji bazowej na wysyłanie różnych strumieni danych do różnych klientów w tym samym czasie i w tym samym kanale radiowym - **AP zachowuje się wiec jak bezprzewodowy switch**

Umożliwia to przypisanie przestrzennych strumieni do więcej niż jednego urządzenia na raz. Liczba urządzeń będzie zależeć od liczby anten oraz od sposobu implementacji MU-MIMO. Jednak nawet bez względu na to, MU-MIMO i tak przyczyni się do zwiększenia przepustowości.

W praktyce odczują to właściciele urządzeń wyposażonych w jedną antenę, takich jak np. smartfony, którzy już nie będą musieli szukać dla swojego urządzenia pozycji, w której „złapie” ono sygnał sieci. 

#### 5. Beamforming (kształtowanie wiązki)
To po prostu kierunkowa transmisja sygnału.
Wiązka staje się bardziej skoncentrowana i jest kierowana wprost do poszczególnych urządzeń. 
Zwiększa to siłę, zasięg i stabilność sygnału.

#### 6. (OLAĆ) Zaktualizowany mechanizm RTS/CTS
Ze względu na możliwość wykorzystywania kombinacji różnych szerokości kanałów w standardzie
802.11ac mechanizm Request to Send/Clear to Send został zaktualizowany tak aby w wydajny sposób
wspierał dynamiczne wykorzystanie pasma


### Porównanie

|                           | 802.11n                  | 802.11ac                                  |
|---------------------------|--------------------------|-------------------------------------------|
| Pasmo częstotliwości      | 2.4 oraz 5 GHz           | 5 GHz                                     |
| Szerokość kanału          | 20, 40 MHz               | 20, 40, 80, 160 MHz                       |
| MU-MIMO (Multi-user MIMO) | Nie                      | Tak                                       |
| Modulacja                 | BPSK, QPSK, 16QAM, 64QAM | BPSK, QPSK, 16QAM, 64QAM, 256QAM          |
| Strumienie przestrzenne?  | Od 1 do 4                | Od 1 do 8 (per AP) Od 1 do 4 (per klient) |
| Teoretyczna prędkość      | 450 Mbps                 | 1300 Mbps                                 |
| Rzeczywista prędkość      | 200 Mbps                 | 222 Mbps (dane z 2013)                    |


### Dodatki
https://www.howtogeek.com/394266/what-is-4x4-mimo-and-does-my-smartphone-need-it/

What is 4×4 MU-MIMO?
Some newer wireless routers support MU-MIMO, too. This refers to “multi-user multiple input, multiple output.” A router with 4×4 MU-MIMO has four antennas it can communicate on at once. If you had several 4×4 MIMO devices connected to that router, they would all maintain a connection of four data streams at the same time.

Or, if you have a laptop with 3×3 MIMO like Apple’s newer MacBook Pros, they can connect to a 4×4 MIMO access point with three data streams at once.

However, if you have a phone with 2×2 MIMO Wi-Fi or a laptop with 3×3 MIMO and you connect it to an older router that doesn’t support MIMO at all, it will only receive a single data stream. If you connect a 3×3 MIMO device to a 2×2 MIMO router, it will only use two data streams.
