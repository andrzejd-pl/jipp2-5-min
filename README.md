# Prolog #


Podstawą prologa są:
- rachunek predykatów I-go rzędu
- zasada rezolucji

Zalety programowania deklaratywnego:
- wysoki poziom abstrakcji
- niezależność od implementacji danych i programu
- programista jest zwolniony z implementacji częsci JAK
- łatwość tworzenia prototypów systemów

Obszary stosowania programowania deklaratywnego:
- tradycyjne:
	- sztuczna inteligencja

- współczesne:
	- systemy z wiedzą
	- rozproszone systemy kooperacyjne
	- systemy otwarte
	- systemy samoopisujace się, zdolne do modyfikowania struktury i zachowań

## Termami są:
- stałe (pisane z małej litery) i zmienne (pisane z dużej)
- symbole funkcyjne z argumentami, które są termami (tzw termy złożone)
- służą do nazywania bytów

Związki między bytami to relacje.
Literał to atom lub zanegowany atom.

Reguła to:
```Prolog
A :- B1, B2, ..., Bn
```

Reguła z pustym ciałem to fakt.

Program to skończony zbiór reguł.

Zasada rezolucji: wykorzystuje metodę "nie wprost" i regułę rezolucji

Wywód rezolucyjny:
- obliczenie kończy się kiedy dalsza redukcja nie jest możliwa
- rezolwenta jest pusta -> sukces, w przeciwnym wypadku porażka

Dla danego zapytania może być wiele obliczeń zakończonych sukcesem.

Obliczenia prologowe, trzeba podjąć decyzję:
- o sposobie wybierania literału aktywnego z rezolwenty (tzw regóła obliczeniowa)
- o sposobie wybierania klauzuli z programu (tzw reguła przeszukiwania drzewa poszukiwań)

Strategia prologowa:
- wybieranie skrajnie lewego literału w rezolwencie jako literału aktywnego
- przegładnie zbioru klauzul kandydujących do redukcji (zgodnie z porządkiem występowania)
- zaniechanie sprawdzania acykliczności procesu unifikacji

## Metapredykaty:
- odcięcie (`!`):
	- zawsze spełniony
	- zmienia wykonywanie nawrotów
	- zmniejsza drzewo poszukiwań
	- jest silnie kontekstowy
- `fail`:
	- wykonuje nawórt w obliczeniu
- `clause(H, B)` - reprezentacja programu przedmiotowego
- `assert(C)` - modyfikacje programu przedmiotowego
- `retractall(C)` - j.w.
	
**W systemach prologowych istnieje zasada zamkniętego świata (to czego nie ma w programie jest fałszywe).**

Rozwiązywanie problemów:
- model grafowy - znalezienie drogi w grafie
- model redukcji zadania - zamiana zadania na prostrze podzadania


Pre-interpretacja to para (D, m), gdzie _D_ jest dziedziną interpretacji (niepusty zbiór), a _m_ funkcją semantyki, która stałym, symbolom funkcyjnym i predyktatywnym z języka (języka klauzul Horona) przyporządkowuje, odpowiednio, elementy z _D_, funkcje z _D<sup>k</sup> -> D_ i  relacje na _D<sup>k</sup>_

## Interpretacja Herbranda

Dla programu P:
- uniwersum Herbranda U<sub>P</sub> to zbiór wszsytkich termów bez zmiennych, zbudowanych ze stałych i symbolów funkcyjnych
- baza Harbranda B<sub>P</sub> to zbiór atomów z symboli predykatywnych z P i termów z U<sub>P</sub>

Język L, który jest identyczny z ML, nazywan się językiem samoreprezentującym (zjawisko amalgamacji języków).

> Prolog slajd 150

# Programowanie funkcyjne #

Obliczenia to wyznaczanie wartości funkcji.

Postawa:
- rachunek lambda

Dane są:
- atomami (elementarne):
	- symbole
	- liczby
	- atomy znakowe
	- atomy boolowskie
	- łańcuchy
- parami kropkowymi (złożone):
	- listy
	- drzewa

**Listy własności** - listy par elementów własności - wartość własność.

Każda dana złożona jest parą danych, stąd rekurencja car-cdr.

**Funkcje wyższego rzędu** - fukncje, które przyjmują za argument inne funkcje.

# Erlang #


Silnie typowany.
Definicja funkcji jest sekwencją klauzul.

# Systemy regułowe #


Przetwarza dane w postaci symbolicznej za pomocą przejzystych reguł.
Baza wiedzy opiera się na regułach _IF - THEN_ i składa się z reguł i faktów.

**Przesłanka** to sprawdzenie czy jest relacja _atrybut - wartość_.
**Konkluzja** to wniosek, który mówi co ma się dziać z atrybutem.

## Fukncje:
- klasyfikowanie
- ustalanie przyczyn
- monitorowanie
- diagnozowanie

## Cechy faktów
- niepwene lub pewne
- deaktualizacja i zmienność
- opisywanie specyficznych cech obiektu
- mają pewnien stopień pewności

## Panowanie nad bazą reguł
- grupowanie reguł
- sieć zależności

## Rodzaje reguł
- proste
- złożone

## Rodzaje wnioskowania na regułach
- wstecz (reguła, która spełnia naszą hipotezę) - _PROLOG_
- w przód (reguła, która spełnia nasze warunki) - _CLIPS_
- drzewo wywodu

## Agenda
Uprządkowana lista wystąpień reguł, które są dopasowane do faktów z bazy.

# Haskell #

- język czysto funkcyjny (jest deterministyczny, wynik działania jest zależny tylko od argumentów).
- silnie typowany
- modularny

## Leniwe wartościowanie
Wyznaczane są wyrażenia, które są potrzebne by dać odpowiedź na dany problem.

# Programowanie funkcyjne w OOP #

Zalety:
- software wolny od bugów
- wydajne obliczenia równoległe
- lazy evaluation
- znacznie krótszy kod od analogicznego napisanego w języku proceduralnym
- nie obsługujemy mechanizmów przydzielania i zwalniania pamięci.

Rodzaje:
- _pure function_ (zalezne tylko od przekazanych argumentów)
- _non-pure functions_ (zależnie nie tylko od przekazanych argumentów) (funkcje typu void są _non-pure_)

## Currying
Zmiana funkcji z n argumentami na n funkcji z jednym arguemntem.

# Algorytmy ewolucyjne #

Pojęcia:
- Osobnik - podstawowa jednostka poddawana ewolucji, punkt w przestrzeni poszukiwań
- Genotyp - reprezentuje osobnika, składa się z chromosomem (najczęściej jednym)
- Chromosom - łańcuch genów (najczęście to są bity), czyli łańcuch bitów
- Locus - pozycja genu w chromosomie
- Allel - wartość genu
- Populacja - zbiór osobników
- Otoczenie - problemdo rozwiązania, wywiera wpływ na osobników za pomocą funkcji przystosowania (ocena rozwiązania problemu)

## Operacje genetyczne
- krzyżowanie:
	- _one point crossover_ - jeden punkt do krzyżowania
	- _multi point crossover_ - wiele punktów do krzyżowania (zamiany genów)
	- _uniform crosover_ - kompletne wymieszanie obu genomów (taki duży _multi point_ ?)
- mutacja - zamiana jednego lub więcej genóœ z losowością równą _częstosci mutacji_, służy do eksploracji przestrzeni rozwiązań:
	- _bit flip mutatuin_ - zmiana wartości tulko jednego genu
	- _swap mutation_ - zamiana miejscami dwóch genów
	- _scramble mutation_ - losowa zamiana miejscami danego odcinka genomu
- selekcja - wybór osobników do krzyżowania:
	- ranking liniowy
	- turniej - losowanie osobników i wybranie najlepszego
	- koło ruletki

## Metody wyboru rodziciów
- _roulette-whell selection_
- _stochastic universal sampling_
- _tournament selection_

## Strategie ewolucyjne
- _1+1_ - najprostrza, populacja dwóch osobników (rodzic i jego mutacja)
- _1+lambda_ - podobnie jak w _1+1_ tylko powstaje więcej mutacji (lambda-mutacji) i z nich się wybiera rodzica (stary ginie zawsze)
- reguła 1/5 sukcesów - skokowa zmiana w zależnośći od powodzenia mutacji; jeśli liczba sukcesów kilku ostatnich mutacji jest większa niż <sup>1</sup>/<sub>5</sub> to zwięsza się zakres mutacji; w innym wypadku mutacje zmiejszamy
- _u+lambda_ - unikanie przestojów w ektremach lokalnych, pula rodzicielska z u-sosbników, wybiera się p rodziców, gdzie p<=u, i powstaje lambda potomków, osobniki są poddawane mutacji i z puli rodzice+dzieci wybieramy u sosbników do następnej iteracji

## Podstawowe trudności przy stosowaniu metod klasycznych
- Zbieżność algorytmu do rozwiązania optymalnego zależy od wyboru rozwiązania początkowego.
- Większość algorytmów ma tendencję do utknięcia w rozwiązaniu sub optymalnym.
- Algorytm, który może być efektywny przy rozwiązywaniu danego problemu optymalizacji, może nie być efektywny przy rozwiązywaniu innego problemu.
- Algorytmy nie są efektywne w zastosowaniu do problemów z dyskretną przestrzenią poszukiwań.
- Algorytmy nie mogą zostać w sposób efektywny wykorzystane na równoległych maszynach.

## Podstawowe cechy algorytmów ewolucyjnych odróżniające je od innych metod
- Nie przetwarzają one bezpośrednio parametrów zadania, lecz ich zakodowaną postać.
- Prowadzą poszukiwania, wychodząc nie z pojedynczego punktu, lecz z pewnej ich populacji.
- Korzystają tylko z funkcji celu, nie zaś z jej pochodnych lub innych pomocniczych informacji.
- Stosują probabilistyczne a nie deterministyczne reguły wyboru.

## Algorytmy genetyczne

### Standardowy algorytm genetyczny - Algorytm Hollanda
Osobniki są reprezentowaen przez chromosomy w postaci ciągów binarnych. Każdy osobnik jest opisany przez zbiór parametrów p(x,y). Metoda selekcji to _metoda ruletki_.

Operatowy genetyczne:
- krzyżowanie
- selekcja

#### Twierdzenie o schematach
Schematy małego rzędu, o małej rozpiętości i o przystosowaniu powyżej średniej
otrzymują rosnącą wykładniczo liczbę swoich reprezentantów w kolejnych
generacjach algorytmu genetycznego.

## Programowanie genetyczne
Osobniki są reprezentowane w postaci drzewa programów.
Metoda selekcji: **metod turniejowa**.
Krzyżówka: wybranie poddrzew i zamiana -> stworzenie nowego potomka
Mutacja: wybranie losowego poddrzewa i zamiana go na nowe wygenerowane poddrzewo.

Duża populacja, mało generacji.

## Zastosowania
- optymalizacja
- automatyczne programowanie
- uczenie robotów i urządzeń
- badanie systemów społecznych
- badanie związków między ewolucją a uczeniem się
- modelowanie zjawisk występujących w ekologii
- modelowanie procesów występujących w ekonomii
- systemy CAD
- modelowanie naturalnych systemów odpornościowych
- modelowanie zjawisk występujących w populacji genetycznej
- sztuczna inteligencja
- rozwiązywanie problemów NP
- zadania planowania, optymalnego sterowania, wspomagania decyzji
- gry komputerowe
- eksploracja dużych danych
- analiza obrazów
