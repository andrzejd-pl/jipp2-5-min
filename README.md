
# Prolog

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

Termami to:
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
