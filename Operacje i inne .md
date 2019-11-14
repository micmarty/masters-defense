źródło: `TPDP-W\1. Wykêady dr Kulawiak\3_Przetwarzanie_danych`

# Rodzaje operacji
## Topologiczne, na danych wektorowych:
- iloczyn i suma (intersect, union) [fot](https://user-images.githubusercontent.com/12485656/68885729-03a45e00-0716-11ea-8b06-b1c48386bbd1.png)
- różnica i różnica symetryczna [fot](https://user-images.githubusercontent.com/12485656/68885698-f0918e00-0715-11ea-9f25-11a047463a9f.png)
- buforowanie [fot](https://user-images.githubusercontent.com/12485656/68885761-17e85b00-0716-11ea-96b5-9ad442612930.png)
- łącznie i przycinanie (dissolve, clip) [fot](https://user-images.githubusercontent.com/12485656/68885817-2e8eb200-0716-11ea-991a-b80ab7ea6339.png)
- traingulacja Delaunay'a - tworzenie powierzchni złożonej z trójkątów po podaniu na wejściu dowolnego zbioru punktów (
- diagram Voronoi - wyznaczanie największych możliwych granic wokół punktu, albo inaczej: reprezentuje rejon wpływów każdego z danych punktów.
Przykładowo jeśli jesteśmy znajdujemy sie samochodem w jakiejś "komórce" diagramu, to punkt w jego środku jest najbliższą możliwą stacją benzynową [fot](https://user-images.githubusercontent.com/12485656/68886071-b4126200-0716-11ea-8c5c-c131a17af70a.png)
[benz](https://user-images.githubusercontent.com/12485656/68886364-62b6a280-0717-11ea-829f-9b02f44a6cf1.png)

## Na danych rastrowych
- przycięcie wartości (range clipping, histogram range clipping)
- zawężenie zakresu (ściśnięcie) [fot](https://user-images.githubusercontent.com/12485656/68886640-dfe21780-0717-11ea-9e7b-9e52648dd777.png)
- różnego rodzaju filtracje:
  - dolnoprzepustowa - rozmywa, wygładza, wzmacnia te rejony obrazu (wartości pikseli/składowe), które mają małą częstotliwość zmian przestrzennych
  - górnoprzepustowa - wyostrza, uwydatnia szczegóły, jednocześnie zwiększa zaszumienie
  - medianowe - usuwa zakłucenia punktowe typu ziarenka pieprzu/soli - czyli drobny szum
  - krawędziowe/konturowe: pozioma, pionowa, kompasowa [fot](https://user-images.githubusercontent.com/12485656/68887527-706d2780-0719-11ea-9764-915d35d8c562.png)
- algebra obrazu - operacje na wartosciach pikseli np.
  - zmetnienie wody: `-24 + 1.03 * GREEN - 1.65 * RED + ...`
  - wskaznik roslinnosci `Normalised Differential Vegetation Index`
 

# Toole
- OpenLayers - najbardziej rozwinięta biblioteka wspierająca sieciowych SIPów (np. serwisów mapowych), JavaScript, open source
![image](https://user-images.githubusercontent.com/12485656/68888108-96df9280-071a-11ea-9eff-a7d443cc6309.png)

- QGIS
- GeoTools 
- PostGIS - baza danych na Postgresie
- OsmAnd - mapy mobilne, apka 
