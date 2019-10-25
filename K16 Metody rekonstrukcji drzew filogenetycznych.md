# Metody rekonstrukcji drzew filogenetycznych (Elementy bioninformatyki - K.Giaro)

- Drzewo filogenetyczne lub drzewo rodowe – to rozgałęziający się diagram, który odzwierciedla pokrewieństwo ewolucyjne pomiędzy taksonami
  - Takson lub grupa taksonomiczna - jest to grupa organizmów spokrewnionych, wyróżniających się konkretną cechą różniąca je od innych jednostek taksonomicznych.

Po co nam te drzewa?
- Aby stworzyć hierarchiczny system klasyfikacji organizmów - katalog, który umożliwi dostęp do zgromadzonej wiedzy
- Aby zbadać przebieg ewolucji - dokonywac rekonstrukcji zmian cech organizmów w czasie

--------------

- O filogenezie wnioskujemy w oparciu o cechy homologiczne. Cechę występującą u dwóch gatunków uznaje się za homologiczną, jeżeli występowała u ich wspólnego przodka.
- Przy rekonstrukcji drzewa trzeba znać różnicę między pokrewieństwem a podobieństwem.
  - Podobieństwa nieznaczące o wspólnym pochodzeniu to homoplazje, utrudniają one odtworzenie rzeczywistej filogenezy organizmów.
- Drzewo czyta się od korzenia, przez węzły wewnętrznę (wspólni przodkowie), aż do węzłów zewnętrznych (liście, to gatunki żyjące dzisiaj). 
- Istnieją również drzewa nieukorzenione, one nie informują nas o kierunku ewolucji. Z nich czerpiemy tylko informację o wzajemnych bliskościach
relacji pomiędzy gatunkami.
- Długości gałęzi mogą mieć znaczenie!


# Metody szacowania filogenezy
- Metoda największej parsymonii
Najbardziej prawdopodobne jest takie zdarzenie ewolucyjne, które wymaga najmniejszej liczby zmian.
Drzewo NIE jest obliczane, sprawdzane i porównywane są wszystkie (lub najbardziej obiecujące) drzewa. Szukamy wśród nich nich
takiego, które wyjaśniało by zróżnicowanie badanych sekwencji jak najmniejszą liczbą mutacji - *najkrótsze drzewo*

- Metody odległościowe (np. łączenie sąsiadów)
Obliczane jest drzewo na podstawie macierzy odległości pomiędzy wszystkimi sekwencjami w analizie.

1. Obliczanie macierzy odległości

2. Obliczne jest drzewo na podstawie tej macierzy (np. metodą Neighbour-Joining)

- Metoda największej wiarygodności
Drzewo nie jest obliczane. Sprawdzamy wszystkie drzewa (lub najbardziej obiecujące) szukając takiego, dla którego 
najbardziej prawdopodobne jest uzyskanie obserwowanego rozkładu cech (nukleotydów lub aminokwasów w sekwencjach) przy założeniu modelu sybstytucji (parametry są określone) WTF.

- Analiza Bayesowska
Drzewo nie jest obliczane. Poszukujemy WIELU a nie jednego drzewa, które są najbardziej obiecujące, czyli mające dobry rozkład obserwowanych cech przy założonym modelu 
substytucji ( parametry NIE SĄ określone).
Finalnie, łączymy jakoś te wybrane drzewa w jedno.
