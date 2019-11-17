# K7 Wymień podstawowe paradygmaty przetwarzania, które mogą być wykorzystywane przez aplikacje równoległe (SOWW)

Zrodlo: http://www.buyya.com/cluster/v2chap1.pdf

### 0. Pojęcia
* Statyczna dekompozycja/partycjonowanie – robiona nim aplikacja rozpocznie działanie. Wymagana wiedza na temat tego jak podzielić problem.

* Dynamiczna dekompozycja - wykonywana w czasie działania programu. Dodatkowe procesy są rozmnażane w razie potrzeby. Minimum tyle procesów ile węzłów. 


#### 1. Task farming/Master-Slave 
W tym paradygmacie master partycjonuje dane wejściowe na części, które są później przypisywane do slave’ów celem dalszych obliczeń. Po zakonczeniu obliczeń slave’y zwracają wyniki do mastera, który je zbiera. Dane mogą być partycjonowane statycznie i przydzielane do slave’ów albo slave’y mogą same prosić o kolejne kawałki po zakończeniu swoich obliczeń. 

Kiedy liczba zadan przekracza liczbe slave albo jest nieznana na początku to korzysta sie z **dynamicznej alokacji zadań** (zamiast statycznej).

Ten paradygmat jest bardzo skuteczny dla algorytmów sekwencyjnych z brakiem zależności pomiędzy slavami (gadają tylko z masterem) - nie trzeba niczego koordynować ani wymieniac wiadomosci. Można czasem chcieć stworzyć grupę masterów gdzie kazdy ma swoich slave'ów.

Dekompozycja danych: Statyczna 
Alokacja danych: Statyczna lub dynamiczna

#### 2. Single-Program Multipe-Data (SPMD) tzw. Geometric Parallelism

Wszystkie procesy mają ten sam kod, który wykonują na innych częściach danych. 
Oddzielne procesy wykonują te same operacje na różnych częściach danych wejściowych. 
Procesy mogą wymieniać się między sobą danymi w czasie obliczeń. Dynamiczne partycjonowanie danych może być wymagane w celu skompensowania zmian obciążenia procesów w czasie obliczeń. 

Dekompozycja danych: Statyczna lub dynamiczna 
Alokacja danych: Statyczna

#### 3. Pipeline (potok) 
Podejście funkcyjne, różne, niezależne i kolejne części algorytmu muszą być zidentyfikowane, a operacje wykonywane są równolegle na fragmentach danych przechodzących przez potok. 

Po prostu **w potoku części algorytmu są rozdzielane na procesy**, a nie części danych. Każda kolejna 'kostka' wykonuje inną część algorytmu na całych danych. Komunikacja może być asynchroniczna

Dekompozycja danych: Statyczna 
Alokacja danych: Statyczna 

#### 4. Divide-and-Conquer (dziel i rządź) 
Pierwotny algorytm jest dzielony na dwie lub więcej mniejszych części, które są niezależnie rozwiązywane, a następnie wyniki łączone celem uzyskania ostatecznego rozwiązania. Można wyobrazić to sobie jako strukturę drzewa.

Mniejsze części mogą byc po prostu mniejszymi rozmiarowo instancjami tego samego problemu (w tym wypadku rekurencja), mogą jednak wymagać rozwiązania z pomocą zupełnie innych algorytmów.  Podproblemy są typowo niezależne od siebie, więc nie ma narzutu komunikacji z nodami na tym samym poziomie zagłębienia.

Dekompozycja danych: Dynamiczna 
Alokacja danych: Dynamiczna 

>  For instance, in geometric parallelism both the decomposition and distribution are static. The same happens with the functional decomposition and distribution of data pipelining. In task farming, the work is statically decomposed but dynamically distributed. Finally, in the divide and conquer paradigm both decomposition and distribution are dynamic


![image](https://user-images.githubusercontent.com/12485656/69008383-0e473900-094a-11ea-9c4c-371159127941.png)
![image](https://user-images.githubusercontent.com/12485656/69008495-75b1b880-094b-11ea-8f18-d7d5e2884d72.png)
![image](https://user-images.githubusercontent.com/12485656/69008559-02f50d00-094c-11ea-9b9d-948159077b1f.png)
![image](https://user-images.githubusercontent.com/12485656/69008568-130cec80-094c-11ea-8d4f-277a045c24b9.png)


