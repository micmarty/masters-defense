# S3 Metody analiz przestrzennych

## Definicja (w razie czego)
Analiza przestrzenna polega na badaniu wybrango obiektu (lub grupy obiektów) na podstawie jego cech geograficznych
Są różne miary:
- Morana (`I`). Wartość -1 oznacza idealne rozproszenie, +1 idealną korelację, 0 układ losowy
- Geary'ego (`C`). Wartość 0 idealne rozproszenie, 2, idealną korelację, 1 układ losowy

`C` w lepszym stopniu odwzorowuje **lokalną** autokorelację podczas gdy `I` jest lepszym miernikiem **globalnej** autokorelacji.

## Metody
### Autokorelacja (przestrzenna)
W sensie matematycznym chodzi o to jak kolejne wartości zależą od wartości poprzednich.
W sensie geograficznym chodzio o to w jakim stopniu **kilka obserwacji tego samego zjawiska** w **różnych miejscach** zależy od siebie nawzajem.


Rys. Autokorelacja - bogaci = niska przestępczość (Kolumbia)
![image](https://user-images.githubusercontent.com/12485656/66715401-472c4500-edc3-11e9-812f-a4fbabf1e1a4.png)

### Regresja (przestrzenna)
W jakim stopniu **wartość jednej zmiennej zależy od kilku innych, niezależnych od siebie zmiennych**
Można wprowadzić wagi dla poszczególnych zmiennych, tak żeby niektóre czynniki miały aż tak dużego wpływu na wynik.
Np. niski poziom edukacji ma prawdopodobnie mniejszy wpływ na ceny mieszkań niż mała dostępność miejsc pracy w okolicy.

Rys. 
![image](https://user-images.githubusercontent.com/12485656/66715543-02a1a900-edc5-11e9-8b59-45a5147f27e7.png)

### Interakcja (przestrzenna)
Są zwane też modelami grawitacyjnymi. Opisują przepływy wartości np. ludzi, dóbr, informacji w przestrzeni geograficznej.
Wpływ ma często: jakość komunikacjii, poziom atrakcyjności terenu, odległości między ważnymi miejscami, standard życia.

Rys.
![image](https://user-images.githubusercontent.com/12485656/66715770-72189800-edc7-11e9-8d3a-942c82d999c5.png)


### Interpolacja (przestrzenna)

Pozwala **oszacować wartość zmiennej w punktach w których nie dokonano pomiarów** w oparciu o wartości zaobserwowane w pobliskich miejscach. W zależności od tego jak daleko są punkty o znanych wartościach można niechcący wygładać teren, pomijając małe wypukłości pomiędzy.


- Poligony Thiessen'a
- Kriging (nazwisko xD) - wykorzystuje metodę najmniejszych kwadratów
- Inverse Distance weighting (IDW)
- DENSITY (funkcja szacowania zagęszczenia)

### Modelowanie i symulacja

### 1. Zapytania do bazy
### 2. Algebra map
### 3. Operatory

## Reklasyfikacja
Umożliwia dokonywanie zmian atrybutów obiektów znajdujących się na wybranej warstwie.
Zazwyczaj prowadzi do ograniczenia ilosci informacji.

Na przykład: 
- chcemy zredukować liczbę klas obiektów 
- odfiltrować klasy powyżej/poniżej jakiejś wartości (mniej niż 100 m n.p.m)
- ob


## Wariogram
(wtf)
Można za pomocą jego wyznaczać trend. Tworzy się go na podstawie wyników serii pomiarów dokonanych na danym obszarze.
![image](https://user-images.githubusercontent.com/12485656/66715890-d8ea8100-edc8-11e9-91ca-5bbee09533ff.png)

## Metoda Delaunaya


![image](https://user-images.githubusercontent.com/12485656/66714970-f2d29680-edbd-11e9-8ccd-39408b9e1b73.png)
