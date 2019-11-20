# Survival_Analysis
Analiza przeżycia pacjentek poddanych terapii hormonalnej w trakcie leczenia onkologicznego.

1. Dane :
Zbiór danych GBSG2 pochodzi z badania Sauerbrei, W., and P. Royston 1999. Zbiór składa się z grupy obserwacji 686 pacjentek, które zostały poddane leczeniu nowotworu piersi.

Zmienne ujęte zbiorze:
⋅⋅* time – zmienna określająca dzień od rozpoczęcia obserwacji w którym pacjentka umarła lub
jej obserwacja została ucięta
⋅⋅* cens – zmienna binarna określająca to czy obserwacja została ocenzurowana czy nie – {0,1)
⋅⋅* age – zmienna ciągła, wiek pacjentki w latach
⋅⋅* tsize – wielkość guza w [mm]
⋅⋅* menostat – status pacjentki, przed menopauzą 0, po menopauzie 1
⋅⋅* pnodes – liczba ognisk nowotworowych
⋅⋅* tgrade – stopień zaawansowania guza: {1,2,3} – 3 najwyższy stopień
⋅⋅* progrec – ilość receptorów progesteronowych w [fmol]
