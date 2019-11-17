K12 Omów własności liniowego generatora kongruencyjnego (MISS)


- Jest rekurencyjny (bo zależy od wyrazu poprzedniego)
- Jest bardzo szybki, wymaga mało pamięci
- Zbyt prosty żeby korzystać w niego w kryptografii albo metodach statystycznych np. Monte Carlo: znając m wystarczą zaledwie 3 wygenerowane wartości żeby poznać a i c
- LCG jest używany do generowania liczb losowych w wielu językach programowania jako domyślny generator.

`LCG(n+1) = a*LCG(n) + c (mod m)`

dla m=5 liczby 2 i 7 sa kongruentne
- Okres wynosi m-1 => czyli wyrazy zaczną się powtarzać
- Maksymalna wartość losowa wynosi m
- Najszybciej działa kiedy m jest potęgą 2 np. 2^32 -> szybko się liczy przez przesuwanie bitowe
- Najlepiej losuje kiedy m i c są względnie pierwsze (nie mają wspólnych dzielników)

Super wytlumaczenie: https://www.youtube.com/watch?v=PtEivGPxwAI
