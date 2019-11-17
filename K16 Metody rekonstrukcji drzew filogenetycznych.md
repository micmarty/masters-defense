# Metody rekonstrukcji drzew filogenetycznych (Elementy bioninformatyki - K.Giaro)

- Drzewo filogenetyczne lub drzewo rodowe – to rozgałęziający się diagram, który odzwierciedla pokrewieństwo ewolucyjne pomiędzy taksonami
  - Takson lub grupa taksonomiczna - jest to grupa organizmów spokrewnionych, wyróżniających się konkretną cechą różniąca je od innych jednostek taksonomicznych.

Po co nam te drzewa?
- Aby stworzyć hierarchiczny system klasyfikacji organizmów - katalog, który umożliwi dostęp do zgromadzonej wiedzy
- Aby zbadać przebieg ewolucji - dokonywac rekonstrukcji zmian cech organizmów w czasie

--------------

- O filogenezie wnioskujemy w oparciu o cechy homologiczne. Cechę występującą u dwóch gatunków uznaje się za homologiczną, jeżeli występowała u ich wspólnego przodka.
- Drzewo czyta się od korzenia, przez węzły wewnętrznę (wspólni przodkowie), aż do węzłów zewnętrznych (liście, to gatunki żyjące dzisiaj). 
- Istnieją również drzewa nieukorzenione, one nie informują nas o kierunku ewolucji. Z nich czerpiemy tylko informację o wzajemnych bliskościach
relacji pomiędzy gatunkami.
- Długości gałęzi mogą mieć znaczenie!


## Metody szacowania filogenezy
#### Metoda największej parsymonii

Najstarsza i najprostsza metoda.

Najbardziej prawdopodobne jest takie zdarzenie ewolucyjne, które wymaga najmniejszej liczby zmian.
Drzewo NIE jest obliczane, sprawdzane i porównywane są wszystkie (lub najbardziej obiecujące) drzewa. Szukamy wśród nich nich
takiego, które wyjaśniało by zróżnicowanie badanych sekwencji jak najmniejszą liczbą mutacji - *najkrótsze drzewo*

#### Metody odległościowe (np. łączenie sąsiadów - Neighbourhood Joining)

Obliczane jest drzewo na podstawie macierzy odległości pomiędzy wszystkimi sekwencjami w analizie.

Metoda przyłączania sąsiadów (http://www.michalbereta.pl/dydaktyka/bioinf_io_/Bioinformatyka_slides_11_drzewa_filogenetyczne.pdf)
- Generuje drzewa nieukorzenione
- Zakłada addytywność odległości w konstruowanym drzewie
- Złożonośd obliczeniowa O(n^2)
- Dokładna jeśli macierz odległości jest addytywna
- Duża szansa na dobre wyniki jeśli macierz odległości jest prawie addytywna
– Macierz może nie być addytywna w wyniku zastosowania błędnej metody wyznaczania odległości ewolucyjnej lub niedokładnego dopasowania wielosekwencyjnego.

1. Obliczanie macierzy odległości
2. Obliczne jest drzewo na podstawie tej macierzy (np. metodą Neighbour-Joining)

#### Metoda największej wiarygodności

Drzewo nie jest obliczane. Sprawdzamy wszystkie drzewa (lub najbardziej obiecujące) szukając takiego, dla którego 
najbardziej prawdopodobne jest uzyskanie obserwowanego rozkładu cech (nukleotydów lub aminokwasów w sekwencjach) przy założonym modelu sybstytucji (parametry są określone) WTF.

- Model wybitnie statystyczny
- Oblicza długości odgałęzień
- Bardzo kosztowna obliczeniowo
- Oszacowuje wiarygodność wyników

#### Analiza Bayesowska

Drzewo nie jest obliczane. Poszukujemy WIELU a nie jednego drzewa, które są najbardziej obiecujące, czyli mające dobry rozkład obserwowanych cech przy założonym modelu 
substytucji ( parametry NIE SĄ określone).
Finalnie, łączymy jakoś te wybrane drzewa w jedno.

![image](https://user-images.githubusercontent.com/12485656/69012775-d1933600-0979-11ea-9d0f-a40975b1cc75.png)
![image](https://user-images.githubusercontent.com/12485656/69012876-b37a0580-097a-11ea-9349-7d70a2293975.png)
http://marcin_filipecki.users.sggw.pl/PDFY/BIOINF_WYKL/filogenetyka.pdf
![image](https://user-images.githubusercontent.com/12485656/69013153-40be5980-097d-11ea-99e3-aadaa77a7d69.png)


## Wybór metody
- duża ilość danych, niewielkie zasoby obliczeniowe ==> Metoda najbliższego sąsiedztwa (Neighbor joining)
- niewielka liczba mutacji/homoplazja ==> Maximum Parsimony
- ograniczona długość sekwencji, występowanie zjawiska homoplazji ==> Maximum Likelihood

## Pojęcia
Homoplazja - dwie niezależne mutacje doprowadziły do wyewoluowania tego samego genu (czyli w innych miesjcach drzewa), czyli  podobieństwo sekwencji NIE będące rezultatem wspólnego pochodzenia
