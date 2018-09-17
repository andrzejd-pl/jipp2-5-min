
Prolog
-

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
- odcięcie (!):
	- zawsze spełniony
	- zmienia wykonywanie nawrotów
	- zmniejsza drzewo poszukiwań
	- jest silnie kontekstowy
- fail:
	- wykonuje nawórt w obliczeniu
	
	
**W systemach prologowych istnieje zasada zamkniętego świata (to czego nie ma w programie jest fałszywe).**

Rozwiązywanie problemów:
- model grafowy - znalezienie drogi w grafie
- model redukcji zadania - zamiana zadania na prostrze podzadania


Pre-interpretacja to para (D, m), gdzie _D_ jest dziedziną interpretacji (niepusty zbiór), a _m_ funkcją semantyki, która stałym, symbolom funkcyjnym i predyktatywnym z języka (języka klauzul Horona) przyporządkowuje, odpowiednio, elementy z _D_, funkcje z _D<sup>k</sup> -> D_ i  relacje na _D<sup>k</sup>_

## Interpretacja Herbranda

Dla programu P:
- uniwersum Herbranda U<sub>P</sub> to zbiór wszsytkich termów bez zmiennych, zbudowanych ze stałych i symbolów funkcyjnych
- baza Harbranda B<sub>P</sub> to zbiór atomów z symboli predykatywnych z P i termów z U<sub>P</sub>


