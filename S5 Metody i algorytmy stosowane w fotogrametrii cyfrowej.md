# TODO
# S5 Metody i algorytmy stosowane w fotogrametrii cyfrowej

1. RANSAC czyli RANdom SAmple Consensus - modeluje płaszyzny w zbiorze danych, który zawiera znaczą (przekraczającą nawet połowę) liczbę błędów grubych (czyli outlierów), którzy nie należą do modelowanej powierzchnii
- historia sięga lat '80 (identyfikacja obiektów w widzeniu komputerowym - Fischler, Bolles, 1981)
- wyodrębnia płaszczyzny dominujące, reprezentowane przez największą liczbę punktów
- Zaletą jest jej odporność na przypadkowe punkty
- działa w sposób iteracyjny powtarzając dwa podstawowe kroki: hipoteza, test. Wybiera minimalny zbiór losowych punktów sukcesywnie go zwiększając. W fazie testu sprawdzane jest czy maksymalna odległość testowanego punktu przekracza założone kryterium (jakieś)


## 2. SIFT (Scale Invariant Feature Transform) 1999

Jest algorytmem wykorzystywanym w rozpoznawaniu obrazów do:
– zszywania obrazów (ang. image stitching)
– odnajdywania punktów homologicznych/wiążących
– klasyfikacji/detekcji konkretnych obiektów

Działa tylko na obrazie w **odcieniach szarości** (monochromatyczny)

Transformacja SIFT jest niezależna (niezmiennicza) od ... obrazu/obiektu:
– translacji
– rotacji obrazu/obiektu
– skalowania (jednorodnego) - transformacja daje taki sam wynik (zestaw deskryptorów) niezależnie czy obraz jest „mały czy duży”

![image](https://user-images.githubusercontent.com/12485656/68994683-2190d080-0886-11ea-9845-b32fb2c20d51.png)

