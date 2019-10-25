# Zestawianie pary sekwencji i wielu sekwencji biologicznych - definicje, sposoby oceny,aspekty algorytmiczne. (Elementy bioinformatyki K. Giaro) 

Zestawianie par sekwencji rozumiem jako dopasowanie / porównywanie ze soba dwóch struktur (DNA / RNA / białka) w celu znalezienia regionów podobieństw.
Można porównywać zarówno parę sekwencji jak i wiele sekwencji.

- Przykład:
Mamy dwa ciągi DNA, o których wiemy, że mają wspólne pochodzenie:
1. AGAGTCAATCCATAG
2. CAGAGGTCCATCATG

Zastanawiamy się teraz, w jaki sposób one ewoluowały (lub zmutowały, nie wiem która forma poprawna). Przykładowe dwie mozliwości:

A)

-AGAG-TCAATCCATAG

CAGAGGTCCATC-ATG-

B)

------AGAGTCAATCCATAG

CAGAGG----TCCATCATG--

Pytanie : Które jest bardziej prawdopodobne?

# Rodzaje operacji
- Znak nie został zmieniony
- Zamiana znaku (substytucja) np. A -> C albo T -> G
- Indel (Insertion or Deletion), co oznacza wstawienie znaku zamiast kreski (insercja) albo wstawienie kreski zamiast znaku (delecja) (A -> kreske albo kreska -> G) UWAGA, to nie oznacza, że kasujemy literkę A i zamiast nią wstawiamy kreskę, to oznacza, że PRZESUWAMY nasz ciąg dalej a na miejsce literki A wsadzamy kreske! (CHYBA :D)

Każdej operacji nadajemy różne wagi. Przykładowo, 
- Brak zmiany -> 0
- Zmiana znaku -> 2
- Indel -> 3

Uwaga, można też dawać dodatkowe kary za robienie dużych przerw. Np. każda kolejna kreska kosztuje nas o ILEŚ więcej.

I obliczamy sobie jaki będzie koszt każdej ewolucji. Obliczając powyższe ewolucje mamy
A = 16
B = 44
Z tego wynika, że tańsza (bardziej prawdopodobna) jest ewolucja pierwsza.

-------------------------

# Co można policzyć:
  - Odległość edycyjną - CHYBA to co policzyliśmy wyżej
  - Podobieństwo - CHYBA jeżeli znak się nie zmienia to dajemy +1 jeżeli się zmienia to -1
  - Dopasowania
    - globalne - stara się dopasować całość ciągu do drugiego ciągu
    - lokalne - stara się dopasować część jednego ciągu do drugiego, tak aby osiągnąć najoptymalniejszą wartość

![image](https://www.researchgate.net/profile/Tomas_Flouri/publication/260376769/figure/fig2/AS:216362501840900@1428596248757/Global-local-and-semi-global-alignment-The-global-local-and-semi-global-alignments.png)

* Wyżej, liczyliśmy tylko koszty gotowych dopasowań. Teraz zadajemy sobie pytanie, w jaki sposób samemu znaleźć od razu optymalne dopasowania.
Służą do tego różnego rodzaju algorytmy, z tych które mieliśmy na wykładzie możemy wymienić: 
- Smith-Waterman (dopasowanie lokalne)
- Needleman-Wunsch (do liczenia dopasowania GLOBALNEGO) 
- Hirschberg (też dopasowanie GLOBALNE) 

Jak kogoś interesuje jak działają to odsyłam do WIKI :D Tam są przykłady. 

