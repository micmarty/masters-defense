# Grafika trójwymiarowa na urządzeniach mobilnych
A: https://www.embedded-computing.com/embedded-computing-design/understand-the-mobile-graphics-processing-unit

## Zajawka
Mimo iż smartfony mają obecnie bardzo dużą moc obliczeniową, to ogarnicza je w dużym stopniu 
Mają coraz częściej dedykowane układy graficzne z 
Apple promuje wykorzystanie frameworka **Metal** pod system iOS.

## Konkrety
OpenGL ES - `Open Graphics Library for Embedded Systems`
* cross-platformowe API do renderowania grafiki 2D oraz 3D
* rozwijane przez grupę Khronos
* opracowany dla urządzeń mobilnych, gdzie ważna jest energooszczędność, optymalne wykorzystanie słabych zasobów sprzętowych
* najnowsza wersja to 3.2, zachowuje kompatybilność wsteczną (chyba w większości)
* wspiera Teselację, Compute shadery (+geometry), typy zmiennoprzecinkowe (niegdyś tak nie było)
* do rysowania wykorzystuje dwa bufory: jeden na wierzchołki (vertex buffer), drugi na ich indeksy (index buffer)
* wspierana i wykorzystywana przez platformę Android


## Braki/różnice względem zwykłego OpenGLa:
TODO to było na wykładach wyraźnie poruszone

## Zgrubne porównanie
| OpenGL |	Vulkan |
|----| -----------------|
maszyna stanu z jednym globalnym stanem	oparty na obiektach | bez globalnego stanu
stan jest powiązany z pojedynczym kontekstem | wszystkie stany są zlokalizowane w buforze komend
pamięć karty graficznej i synchronizacja są zazwyczaj ukryte | bezpośrednia kontrola nad pamięcią karty graficznej i synchronizacją
obszerne sprawdzanie błędów	| sterowniki Vulkan nie wykonują sprawdzania błędów; istnieje warstwa sprawdzająca błędy dostępna dla developerów

