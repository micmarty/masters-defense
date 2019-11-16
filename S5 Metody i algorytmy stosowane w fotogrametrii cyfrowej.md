# S5 Metody i algorytmy stosowane w fotogrametrii cyfrowej

## 1. RANSAC czyli RANdom SAmple Consensus (~1980)
https://youtu.be/oT9c_LlFBqs?t=3037
https://youtu.be/oT9c_LlFBqs

Modeluje płaszyzny w zbiorze danych, który zawiera znaczą (przekraczającą nawet połowę) liczbę błędów grubych (czyli outlierów), którzy nie należą do modelowanej powierzchnii. 

Czyli:
1. Wyodrębnia płaszczyzny dominujące, reprezentowane przez największą liczbę punktów.
2. Zaletą jest jej odporność na przypadkowe punkty.
3. Działa w sposób iteracyjny powtarzając dwa podstawowe kroki: hipoteza, test. Wybiera minimalny zbiór losowych punktów sukcesywnie go zwiększając. W fazie testu sprawdzane jest czy maksymalna odległość testowanego punktu przekracza założone kryterium (jakieś)

![image](https://user-images.githubusercontent.com/12485656/68994900-366e6380-0888-11ea-8cd2-22f1b1b392b0.png)

UWAGA też może być wykorzystywany do odnajdowania punktów homologicznych (jak SIFT), patrz filmik!

## 2. SIFT (Scale Invariant Feature Transform) 1999

Jest algorytmem wykorzystywanym w rozpoznawaniu obrazów do:
- zszywania obrazów (ang. image stitching)
- odnajdywania punktów homologicznych/wiążących
- klasyfikacji/detekcji konkretnych obiektów

Działa tylko na obrazie w **odcieniach szarości** (monochromatyczny)

Czyli transformacja SIFT jest niezależna (niezmiennicza) od ... obrazu/obiektu:
- translacji
- rotacji obrazu/obiektu
- skalowania (jednorodnego) - transformacja daje taki sam wynik (zestaw deskryptorów) niezależnie czy obraz jest „mały czy duży”

![image](https://user-images.githubusercontent.com/12485656/68994683-2190d080-0886-11ea-9845-b32fb2c20d51.png)

