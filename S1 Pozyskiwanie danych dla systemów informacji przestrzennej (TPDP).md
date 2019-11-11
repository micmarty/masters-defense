# S1 Pozyskiwanie danych dla systemów informacji przestrzennej (TPDP)

Służą do tego urządzenia peryferyjne (instrumenty geodezyjne, digitizery, skanery, autografy) oraz urządzenia do generowania opracowań tabelarycznych i kartograficznych (drukarki, plotery, naświetlarki).

### Metody
- Skanowanie - zamiana fizycznych, papierowych dokumentów na postać elektroniczną

- Digitalizacja - transformacja, konwersja na prawdziwie cyfrowy format (np. zeskanowane tabele jako zdjęcie zamieniamy na format .docx)

- Wektoryzacja - zamiana danych rastrowych na wektorowe. Są gotowe narzędzie do pół/automatycznej konwersji, bazują one na algorytmach, które budują ciągi linii na podstawie oryginalnych wartości pikseli. Potem z takich linii buduje się poprawną topologię. Dobrze działa z czarno-białymi (monochromatycznymi) mapami (poziomice, cieki, drogi). Do bardziej złożonych wykorzystuje się tryb interaktywny (półautomatyczny), dobiera się różne parametry takie jak: gęstość linii, wielkość przerw, paleta separowalnych kolorów. Jest to czasochłonne ale i tak lepsze niż ręczna robota.

- Rasteryzacja - to samo co wyżej tylko na odwrót

- Geokodowanie - automatyczne przypisywanie współrzędnych na mapie obiektom, które mamy w bazie danych np. adresy budynków

Spróbójcie sami: https://www.vectorizer.io
![image](https://user-images.githubusercontent.com/12485656/66704920-cd437f80-ed20-11e9-9c20-2f691dbaa5c0.png)


### Źródła pozyskiwanych danych
- Inne istniejące systemy (transfer danych)
- Zdjęcia lotnicze
- Zdjęcia satelitarne
- LIDAR
- RADAR

Monitoring zdalny - pozyskiwanie informacji bez kontaktu z obiektem pomiaru (np. przez fale elektromagnetyczne, akustyczne lub komunikację bezprzewodową). Jest taki:
- aktywny - wysyłane są wiązki, fale i mierzy się czas powrotu. Przykład: nietoperze, LIDAR xD
- pasywny - wykorzystuje zjawisko odbicia, rozpraszania, interakcji fal z obiektem. Przykład: fotogrametria


