 # K5 Wyjaśnij jak wygląda typowe przyspieszenie obliczeń w aplikacjach równoległych i od czego zależy (Systemy obliczeniowe wysokiej wydajności - P. Czarnul) 
 
Typowo aplikacja nie skaluje się idealnie liniowo wraz ze wzrostem liczby procesorów. Chyba największym czynnikiem jest tutaj narzut komunikacji potrzebny do wykonania algorytmu w sposób równoległy.

S = speedup

Generalnie duzo zależy od strategii i problemu do którego podchodzimy, bo są:
- aplikacje z małymi zależnościami lub totalnie bez - embarassingly parallel - wtedy `S(N) = N`
- aplikacje z wymagające komunikacji - communication bound - wymienianie danych pomiędzy procesami, wykonują naprzemiennie obliczenia, synchronizują się, wtedy `S(N) = 1/(A + B/N)` albo `S(N) = 1/(A+ B*log(N))`, gdzie A i B są stałymi wyrażającymi stosunek ilości obliczeń do komunikacji, opóźnienia
- aplikacje dziel i zwyciężaj - divide and conquer - takie dzielenie problemu na podproblemy z mniejsza ilością danych do przerobienia pozwala na uzyskanie `S(N) = O(N/log(N))`

## Czynniki jakie mają wpływ na szybkość 
 - topologia (master-slave, ring, mesh, star)
 - sposób komunikacji pomiędzy procesami
 - sam algorytm (jego właściwości)
 - rodzaj i liczba CPU/GPU
 
sposoób komunikacji - poszczególne procesory muszą co jakiś czas wymieniać się danymi nad którymi pracują, lub przesłać sobie wyniki. W przypadku klastrów ma to spore znaczenie, ponieważ połączenia między procesorami są zazwyczaj realizowane za pomocą medium o dużym - w porównaniu do szybkości pracy procesora - opóźnieniu sygnału. inifiniband?
 
## lekki offtop - Ponadliniowe, superliniowe przyspieszenie jako "nietypowe"
 
Teorytycznie przyspieszenie nie powinno nigdy przekroczyć liczby procesorów p. Jeżeli najlepszy sekwencyjny algorytm zajmuje Ts jednostek czasu by rozwiązać dany problem na pojedynczym procesorze, to przyspieszenie p może być uzyskane na p procesorach jeżeli żadnemu z nich nie zajmuje to więcej niż Ts/p. Przyspieszenie większe niż p jest możliwe tylko jeżeli każdy procesor spędza mniej niż Ts/p czasu na rozwiązanie problemu. W tym przypadku, pojedynczy procesor mógłby emulować p procesorów i rozwiązać problem w czasie mniejszym niż Ts. Jest to sprzeczność, ponieważ wg definicji, przyspieszenie oblicza się w stosunku do najepszego sekwencyjnego algorytmu. Przyspieszenie superliniowe zdarza się rzadko i sprawia wiele trudności początkującym, którzy są przekonani, że teoretycznie maksymalna wartość przyspieszenia nie powinna być większa niż p, czyli ilość zastosowanych procesorów. 

  
 Może być wynikiem buga lub po prostu skumulowanej duzej ilości cache
 Przykład: sekwencyjne (skalarne) mnożenie macierzy
 
> This super-linearity in speed-up can typically occur when you parallelise your code while distributing the data in memory with MPI. In some cases, by distributing the data across several nodes / processes, you end-up having sufficiently small chunks of data to deal with for each individual process that it fits in the cache of the processor. This cache effect might have a huge impact on the code's performance, leading to great speed-ups and compensating for the increased need of MPI communications... This can be observed in many situations, but this isn't something you can really count for for compensating a poor scalability.

> Another case where you can observe this sort of super-linear scalability is when you have an algorithm where you distribute the task of finding a specific element in a large collection: by distributing your work, you can end up in one of the processes/threads finding almost immediately the results, just because it happened to be given range of indexes starting very close to the answer. But this case is even less reliable than the aforementioned cache effect.


## Prawo Amdahla vs Gustafsona

![image](https://user-images.githubusercontent.com/12485656/69008044-3d5bab80-0946-11ea-92d0-5d04e4d5bcb9.png)
![image](https://user-images.githubusercontent.com/12485656/69008056-549a9900-0946-11ea-850c-ce5fc137bd1a.png)

Prawo Gustafsona odnosi się do wad prawa Amdahla
- usuwa problem ustalonego rozmiaru problemu lub ustalonego ładowania
obliczeń na równoległych procesorach
- zamiast tego, proponuje koncepcje ustalonego czasu, która prowadzi do
skalowanego przyspieszenia.

S(p) = p – α∙(p-1)
α - część procesu, której nie da się zrównoleglić.
