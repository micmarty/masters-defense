# S4 Produkty i zastosowania fotogrametrii cyfrowej

Dodatkowe źródło: http://home.agh.edu.pl/~zfiit/mat_dydaktyczne_pliki/JB_wyklady.pdf

Zastosowania fotogrametrii: geodezja, kartografia, geologia, rolnictwo, medycyna

## Produkty
### 1. Ortofotomapa (fotomapa, mapa fotograficzna)
To zdjęcie lotnicze lub satelitarne po przetworzeniu na rzut ortogonalny (jednolita skala dla każdego punktu na zdjęciu) zamiast środkowego

aby wytworzyć ten produkt konieczne było:
- znajomość orientacji wewnętrznej, wzajemnej i absolutnej zdjęć (aerotriangulacja)
- znajomość **numerycznego modelu terenu** (wyznaczenie lub pozyskanie z zewnętrznych źródeł)
- wykonanie korekcji geometrycznej zdjęć (zniekształcenia układu opytcznego np. dystorsje)
- połączenie wielu ortozdjęć w mozaikę (złączenie części wspólnych na brzegach)
- dodanie warstwy wektorowej z dodatkowymi informacjami, oznaczeniami np. dróg

### 2. NMPT/NMT - Numeryczny Model (Pokrycia) Terenu

NMT modeluje profil terenu, ukształtowanie. Wykorzystywany do obliczania np. map spadków, objętości mas ziemnych, generowania izolinii
NMPT zawiera również budynki, drzewa itd. Stosowany do opracowywania modeli 3D dla miast.

Najczęściej NMT jest tworzony w postaci **regularnej siatki kwadratów (GRID)**, lub
**nieregularnej siatki trójkątów (TIN)**. Dane dla NMT można pozyskiwać różnymi
drogami:
- z bezpośredniego pomiaru geodezyjnego,
- poprzez digitalizację istniejących map
- metodą skaningu laserowego (np. stosując LIDAR)
- fotogrametrycznie i teledetekcyjnie

### 3. Chmura punktów
Ogromny zbiór punktów wyrażonych jako współrzędne. Tworzona np. przez LIDAR. Taki mesh punktów zamienia się w model 3D, model terenu (NMPT/NMT).

### 4. Model 3D
Ma za zadanie najwierniej reprezentować dany obiekt. Zbudowany z mesha połączonego trójkątami. Na modele nakłada się tekstury.
