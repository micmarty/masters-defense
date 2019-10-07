# S17 Rozszerzona rzeczywistość w urządzeniach mobilnych

Rzeczywistość rozszerzona, z ang. Augmented Reality pozwala na wizualizowanie/interakcję z obiektami 3D, generowanymi komputerowo łącząc przy tym obraz rzeczywisty np. z kamery. Potrzebne są do tego sensory, m.in:
- odbiornik GNSS - określenie położenia

- akcelerometr (przyspieszeniomierz) - mierzy przyspieszenie liniowe w 3 osiach. Pozwala na śledzenie ułożenia przestrzennego urządzenia (pochylanie, przekręcanie). Głównym elementem czujnika jest tzw. masa bezwładna zamocowana na sprężystych belkach, która stanowi elektrodę w układzie kondensatora pomiarowego. W wyniku przemieszczenia masy zmienia się pojemność i tym samym napięcie wyjściowe.

- żyroskop - mierzy położenie kątowe, orientację bezpośrednio. Prawie zawsze współpracuje z akcelerometrem. Składa się najczęściej z mikroskopijnych płytek, które wibrują wraz ze zmianą wysokości, a tym samym ciśnienia. W ten sposób specjalne sensory precyzyjnie określają dokładne położenie w przestrzeni. Wszelka zmiana położenia urządzenia i każdy ruch uaktywniają czujniki, które przekazują tę informację do aplikacji i w ten sposób wywołują odpowiedni efekt.


Ograniczenia akcelerometrów: https://elektronikab2b.pl/technika/12098-zyroskopy-i-akcelerometry-mems-w-elektronice-uzytkowej

## Są różne układy odniesienia
a) b-frame (związany z urządzeniem): Z wychodzi z ekranu, Y w górę, X z prawego boku
b) m-frame (lokalny układ odniesienia): Y północ, X na wschód, Z w kieurnku nieba (jak mapa)
c) ECEF (Earth Centered, Earth Fixed): Z biegun północny, Y południk zerowy (Afryka), X południk 90 stopnii (USA)

### TODO
Można robić konwersje pomiędzy reprezentacjami:
1. z b-frame do m-frame 

## Kluczowe pojęcia
1. Macierz rotacji - macierz 3x3
2. Macierz inklinacji - macierz 3x3
3. Inklinacja magnetyczna - to inaczej nachylenie magnetyczne. **Jest kątem zawartym pomiędzy wektorem
natężenia ziemskiego pola magnetycznego (czyli osią swobodnie zawieszonej igły magnetycznej) a płaszczyzną horyzontu**.  Wartość inklinacji zmienia się wraz ze zmianą szerokości geograficznej.

