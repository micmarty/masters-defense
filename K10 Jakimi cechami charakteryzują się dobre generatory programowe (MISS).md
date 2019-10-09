# K10 Jakimi cechami charakteryzują się dobre generatory programowe

Przede wszystkim dobry generator powinien:
- generować liczby o rozkładzie najbardziej zbliżonym do oczekiwanego
- podciągi powinny być od siebie niezależne, nieskorelowane
- mieć możliwie długi okres - idealnie zmierzający do nieskończoności
- dawać  odtwarzalne/powtarzalne wyniki (na podstawie ziarna)
- mieć krótki czas generowania sekwencji ciągu - idealnie bliski 0 s

Do kryptografii:
- nie może być łatwe odgadnięcie ziarna ani jego stanu wewnętrznego na podstawie obserwacji tego co zwraca
- ponownie... możliwie długi okres
- dawać nieprzewidywalne dla osób postronnych wyniki

