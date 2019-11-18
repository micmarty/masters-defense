# K1 Parametry opisu warunków ruchowych i ich wpływ na jakość pracy w systemach kolejkowych (BO)

http://www2.wt.pw.edu.pl/~akw/Wyklad_TMO.pdf

Teoria kolejek (easy): http://aragorn.pb.bialystok.pl/~walenty/modelowanie/TeoriaKolejek.htm

Od strony 25: http://delibra.bg.polsl.pl/Content/37809/BCPS_42381_2016_Modele-kolejkowe-z-o_0000.pdf

Od strony 205: http://www.rose.pwr.wroc.pl/PMS/PMS.pdf

## Parametry:

Perspektywa zgłoszenia:
- rozmiar (czas wymagany do obsłużenia)
- interwał (czas pomiędzy dwoma zgłoszeniami)

Perspektywa obsługującego:
- wydajność procesora
- liczba stanowisk
- współczynnik obciążenia

reszta jest w Kendallu:

## Notacja Kendalla
A/B/C/K/L/D

### 1. Rozkład zmiennej losowej >czasu między kolejnymi zgłoszeniami<
Symbol A. 

### 2. Rozkład zmiennej losowej >czasu obsługi zgłoszenia<
Symbol B.

**Dla A I B**:
D - deterministyczny, regularny
M - wykładniczy rozkład tzw. poissonowski 
E - Erlanga
G - dowolny

### 3. Liczba stanowisk (procesorów)
Symbol C: ile zgłoszeń może być jednocześnie obsługiwanych

### 4. Długość kolejki
Symbol K: ile zgłoszeń można zakumulować w oczekiwaniu na obsługę. Jeśli pełna, to opuszcza system bez obsługi.

### 5. Oczekiwana liczba zgłoszeń
Symbol L.

### 6. Dyscyplina obsługi (algorytmy szeregowania)
Symbol D: LIFO, FIFO, SIRO (losowa kolejność), priorytetowa (których obsługa jest najkrótsza), round robin (nadawany jest czas w jakim złoszenie ma być obsłużone, jeśli nie zdążymy to ponownie trafia na koniec kolejki)

Kiedy K lub L sa pominięte to zakłada się nieskończoność

## Przykład
![image](https://user-images.githubusercontent.com/12485656/69081146-ab36ce80-0a3d-11ea-9a8b-0328cd785bf8.png)

