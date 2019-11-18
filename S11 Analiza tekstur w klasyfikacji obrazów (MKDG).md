# S11 Analiza tekstur w klasyfikacji obrazów (MKDG)

5/11: http://yadda.icm.edu.pl/yadda/element/bwmeta1.element.baztech-a5d36b6d-0e0d-409f-9751-af7ebc51a0bc/c/Badurska.pdf

## Parametry statystyczne
### Pierwszego rzędu (lub zerowego - podobno zależy od punktu widzenia)
Metody te działają niezależnie od skali i orientacji.

Podstawą jest **histogram** jasności obrazu, opisujący liczbę pikseli mających zadaną jasność.
- **odchylenie standardowe** czyli jaka jest zmienność jasności pikseli w obrazie
- **wartość średnia** czyli wartość oczekiwana
- **skośność histogramu** opisuje stopień asymetrii rozkładu. Jesli jest dodatnia to w badanym obszarze jest więcej pikseli o jasności większej od średniej
- **kurtoza** jest parametrem opisującym stopień skupienia rozkładu jasności, czyli płaskość histogramu
Wartość dodatnia wskazuje 
Wartość ujemna wskazuje że rozkład jasności jest stosunkowo płaski
- **entropia** określa stopień skomplikowania obrazu - im więcej szczegółów w teksturze tym większa wartość entropii

### Drugiego rzędu (wszystko to wielkie WTF!?) bez slajdów z MKDG nie się nie wymyśli z neta ciekawego
Źródło (uzyte w opracowaniu widocznie): https://snauka.pl/metody-klasyfikacji-danych-geoinformatycznych.html
Wyznaczane na podstawie zależności w przestrzennym rozkładzie par pikseli

PCA - może być uznana za formę kompresji danych bo redukuje wymiar informacji

- moment drugiego rzędu (f1), który określa jednorodność obrazów (im większa liczba poziomów jasności, tym mniejsza wartość cechy, a więc dla obrazów gładkich o małych wahaniach jasności cecha ta przyjmuje większe wartości).


Wybrane metody estymacji lokalnych cech obrazu zależnych od skali i orientacji
- metody oparte na analizie widmowej (np. filtry kwadraturowe)
- metody oparte na funkcji autokorelacji obrazu
- piramidy Gaussa i Laplace'a
- macierze wspólnych wystąpień (GLCM - Grey Level Co-occurrence Matrices)
- funkcje Gaboraa jako detektory krawędzi


![image](https://user-images.githubusercontent.com/12485656/69084958-8f372b00-0a45-11ea-9a5a-1f3ec4a29d09.png)
![image](https://user-images.githubusercontent.com/12485656/69085010-a37b2800-0a45-11ea-985c-f3781b8973c2.png)
![image](https://user-images.githubusercontent.com/12485656/69089531-da067200-0a48-11ea-835d-c497ae5eecbe.png)

