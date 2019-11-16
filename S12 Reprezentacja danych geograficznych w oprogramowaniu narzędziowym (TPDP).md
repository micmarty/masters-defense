## S12 Reprezentacja danych geograficznych w oprogramowaniu narzędziowym
(TODO nie jestem pewny czy o to chodzi ale inne opracowanie tak to przedstawia)
Generator: https://www.tablesgenerator.com/markdown_tables#


# Modele danych
| Cecha                               | Model wektorowy                                                                                       | Model rastrowy                                                                                 |
|-------------------------------------|-------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------|
| Rozmiar pliku                       | mały, zapisywane są tylko współrzędne, identyfikatory elementów wektorowych                           | duży, każy piksel jest zapisany w jako osobna wartość. Wyższa rozdzielczość = większy rozmiar. |
| Wymogi sprzętowe                    | małe, choć wymaga obliczeń na żywo, zależy od ilości elementów                                        | na ogół wyższe, ale zależy od rozmiaru zdjęcia                                                 |
| Pozyskiwanie danych                 | uciążliwe, czasochłonne - (pół)automatyczna konwersja z rastrów, albo ręczna robota                   | szybkie i proste                                                                               |
| Koszt pozyskania                    | wysoki                                                                                                | niski (cyka się fotkę i tyle)                                                                  |
| Struktura danych                    | złożona                                                                                               | prosta                                                                                         |
| Jakość zobrazowania                 | wysoka, skalowanie nie pogorsza jakości (niezależne, przeliczane na bieżąco w zależności od potrzeby) | standardowe, zależy od rozdzielczości, kwantyzacji                                             |
| Składanie w warstwy                 | możliwe                                                                                               | możliwe                                                                                        |
| Dokładność geometryczna             | wysoka                                                                                                | zależy od rozdzielczości                                                                       |
| Metadane (opis widocznych obiektów) | w pełni możliwe, można dopisywać własne atrybuty do każdego elementu wektorowego                      | raczej ciężkie, dopisywanie info do każdego piksela jest bez sensu + nieskalowalne             |
