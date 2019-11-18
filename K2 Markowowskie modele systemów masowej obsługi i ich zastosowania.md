# K2 Markowowskie modele systemów masowej obsługi i ich zastosowania

Źródła z K1 + to:
https://usosweb.uwb.edu.pl/kontroler.php?_action=actionx:katalog2/przedmioty/pokazPrzedmiot(kod:1000-IS1-3MSK)

Generalnie, markowowskimi nazywamy systemy kolejowe, w **których rozkłady prawdopodobieństwa czasów pomiędzy kolejnymi wpływami zgłoszeń do systemu oraz czasów ich obsługi są wykładnicze (np. Poissona)**, w wyniku czego, tego typu modele mogą być opisane za pomocą łańcuchów Markowa z czasem ciągłym. 

Proces Markowa to proces stochastyczny, czyli oparty na prawdopodobieństwie. Stan **w przyszłyści zależy wyłącznie od stanu obecnego** (jeden krok w tył). Czyli proces taki jest **bez pamięci**.

Modele kolejkowe, które można przedstawić za pomocą procesu narodzin i śmierci są modelami markowowskimi. 
Proces narodzin i śmierci - w pewnej populacji pojawiają się i giną osobniki w sposób losowy wyznaczony przez rozkład Poissona

Banały (pominąć blah blah):
Zaletą markowowskich modelki kolejkowych jest ich łatwość symulacji oraz dobrze rozwinięty opis analityczny oparty m.in. na formalizmie procesu narodzin i śmierci. 
- W praktyce jednak zachowanie wielu systemów jest niemarkowowskie, stąd istnieje potrzeba korzystania z innych metod umożliwiających ich analizę, o czym będzie więcej w dalszej części pracy.
- Proces markowowski dyskretny to taki gdzie możla przeliczyć (ponumerować) stany

## Jakie są modele (patrz notacja Kendalla)

* M/M/1 - rozkład czas obsługi i rozkład interwał nadchodzenia jest wykładniczy, 1 stanowisko obsługi, nieograniczona kolejka
* M/M/1/Q - -||- + ograniczona kolejka
* M/M/infinite - -||- + niskończona liczba stanowisk, ergo brak kolejek bo obsługiwani od razu

## Zastosowania
Modelowanie kolejek, modele narodziń i śmierci np. w epidemiologi (przenoszenie chorób), biologii (mutacje), migracjach ludności, demografii.

![image](https://user-images.githubusercontent.com/12485656/69078841-0a461480-0a39-11ea-8f0a-3eff8c075be6.png)
