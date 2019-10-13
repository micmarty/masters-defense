# S2 Parametry techniczne satelitarnego systemu obrazowania Ziemi (TPDP)


## Parametry obrazu
Zapamiętać: są 4 różne rozdzielczości: przestrzenna, czasowa, spektralna, kwantyzacji. 

- Sam rodzaj skanera np. elektrooptyczny, optyczno-mechaniczny. Inne: Multispectral (MSS), Thematic, Thermal, Hyperspectral. Źródło:  https://www.slideshare.net/pramodgpramod/remote-sensing-scanners

- Rozdzielczość przestrzenna
	- GSD (ground sampling distance) - odległość w terenie pomiędzy środkami dwóch sąsiadujących pikseli, czyli ile metrów reprezentuje jeden piksel
	
	- IFOV (Instantaneous Field of View) - kąt zakresu "widzenia" pojedynczego detektora rejestrującego energię promieniowania. Na podstawie tej informacji i wysokości (`altitude`) można wyznaczyć GSD.

	> The IFOV and the distance from the target determines the spatial resolution. A low altitude imaging instrument will have a higher spatial resolution than a higher altitude instrument with the same IFOV."

- Rozdzielczość czasowa (okres rewizyty) - po jakim czasie ponownie odwiedzono ten sam teren (czas pomiędzy kolejnymi akwizycjami)

- Rozdzielczość spektralna - w ilu zakresach spektralnych rejestruje się dane np. promieniowanie widzialne, podczerwień bliska, średnia, termalna, promieniowanie mikrofalowe. Dobór zależy od warunków atmosfery (i powodowanych przez nią zakłóceń!). Im więcej zakresów tym wyższa rozdzielczość spektralna, tak samo gdy są one węższe (gęściej upakowane?)

- Rozdzielczość kwantyzacji - precyzja reprezentacji wartości zarejestrowanego promieniowania dla 1 piksela, czyli ile bitów jest przeznaczonych np. 8, 11-bit. Czym większa, tym teoretycznie dokładniejsze pomiary. Analogicznie jak fp32, fp64

- Szerokość pasma rejestracji - szerokość zasięgu satelity nad danym obszarem.

Rys. **IFOV vs FOV**

![ifov](http://www.fao.org/3/t0355e/T0355E16.gif)


Spisane zakresy spektralne i długości fal: https://zasoby1.open.agh.edu.pl/dydaktyka/inzynieria_srodowiska/c_technika_satelitarna/radary.html

### Parametry satelity

| Parametry         | Wartości                                                                             |
|-------------------|--------------------------------------------------------------------------------------|
| Rodzaj orbity     | zsynchronizowana ze słońcem/biegunowa (polarna)/równikowa/itp.                       |
| Wysokość orbity   | niskie od 160-2000 km (większość), średnie do 36k, geostacjonarna 36k, wysokie 36k+, |
| Bitów na piksel   | 8/11/14                                                                              |
| Rozmiar sceny     | 16.5 X 16.5 km^2                                                                     |
| Czas rewizyty     | np. 1 - 3.5 dnia                                                                     |
| Sensor            | Panchromatyczny                                                                      |
| Rozdzielczość     | 2.5 m                                                                                |
| Liczba zakresów   | 1                                                                                    |
| Zakres spektralny | 0.48 - 1.75 mikrometra                                                               |
| Sensor 2          | Multi Spectral Instrument                                                            |
| Rozdzielczość     | 10/20 m                                                                              |
| Liczba zakresów   | 4                                                                                    |

### Parametry techniczne sensora
- liczba i gęstość elementów CCD
- ogniskowa kamery
- kąt bryłowy obiektywu (zakrzywienie)
- zakresy spektralne
