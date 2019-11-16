Współczesne systemy GIS są otwarte na integracje danych i współpracę z innymi systemami.
Stało się to dzięki ustandaryzowaniu formatu wymiany danych przestrzennych m.in jako pliki GML, oraz wzroście konkurencyjności oprogramowania otwartoźródłowego.

## GML (Geography Markup Language)
1. język znaczników bazujący na formacie XML
2. wykorzystywany do modelowania danych przestrzennych w GIS
3. otwarty format, zdefiniowany przez OGC (Open Geospatial Consortium), rozszerzalny

- sformalizowany opis obiektów geograficznych wraz z ich geometrią i zależnościami topologicznymi
- umożliwia wykonywanie zapytań tematycznych, analiz przestrzennych
- skupiony na opisie obiektów w bardziej pełnym spektrum (mosty, drogi, parki, itd.)

Bogaty zbiór prymitywów:
  - Feature - reprezentuje jednostę fizyczną (budynek, rzeka, osoba). Może ale nie musi posiadać aspektów geometrycznych (lokalizacja). Generalnie to wrapuje prymitywy (jak pola klasy w obiektowości)
  - Point
  - LineString
  - Polygon
GML 3.0+ daje struktury do opisu "pokrycia" (coverage), oraz "rastra" (uwzględnienie danych z sensorów, kamer, danych satelitarnych)
. Opisy obiektów przestrzennych są przez schematy XSD


## KML (Keyhole Markup Language)
1. też oparty na XMLu
2. przeznaczony przede wszystkim do wizualizacji trójwymiarowych danych przestrzennych
3. też zatwierdzony przez OGC

- spopularyzowany przez Google
- wykorzystywany przez Google Earth, Google Maps, Bind Maps, Flick, Wikimapię

Znaczniki (są **case-sensitive**):
  - Document - kontener, root dla wszystkich obiektów i stylów
  - Point - współrzędne geograficzne
  - Placemark - pinezka ma: nazwę, opis, lokalizację (jako `Point`)
  - CDATA - dane traktowane jako zwykły tekst, nie można zagnieżdżać, pozwala uniknąć parsowania
  - Icon - link do jakiegoś obrazu źródłowego
  - GroundOverlay - nałożenie obrazu rastrowego na mapę (np. erupcja wulkanu z przeszłości)
  - Path - zbudowana z `LineString`
  - Polygon - trójwymiarowy obiekt złożony z dwóch zamkniętych obszarów LinearRing (obrys zewnętrzny - `OuterBoundary`) i wewnętrzny (`InnerBoundary`). Każdy wierzchołek opisany jest przez `longitude`, `latitude`, `altitude` (nad poziomem morza)
  - TimeStamp - definiuje datę i godzine związaną z obiektem (`rok`-`miesiąc`-`dzień`T`godzina`:`minuta`:`sekunda`Z)
  - TimeSpan - początek i koniec w czasie. Razem z `TimeStamp` pozwala na animacje modeli, obrazów, pinezek (transitions)
  - LineString - trójwymiarowy obiekt reprezentujący polilinię
    - LineStyle
    - altitude
    - altitudeMode
      - RelativeToGround - od powierzchni ziemi
      - RelativetoSeaFloor - jeśli obiekt jest nad wodą to od dna morskiego, jeśli pod wodą to od poziomu gruntu 
      - Absolute - od bezwzględnego poziomu morza
      - ClampToGround - ignoruje każą wartość wysokości, umieszcza obiekt bezpośrednio na powierzchni ziemii
      - ClampToSeaFloor - podobnie jak wyżej, tylko że do dna
  - Tesselate - bool, zagęszczenie punktów na linii (jak w grafice komputerowej)
  - Extrude - bool, łączenie/niełączenie ścieżki z ziemią
 
## Porównanie
1. KML może być używany do renderowania zawartości z GML
2. Przenoszenie z GML do KML skutkuje utratą dużej ilości informacji
3. Około 90% struktur nie można przenieść do KMLa
4. Zamiana KML na GML nie porzuci aż tak dużo: głównie info o animacjach, stylach, reprezentacji w różnych skalach
