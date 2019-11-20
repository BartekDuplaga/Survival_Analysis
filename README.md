# Survival_Analysis
Analiza przeżycia pacjentek poddanych terapii hormonalnej w trakcie leczenia onkologicznego.

1. Dane :
• Zbiór danych GBSG2 pochodzi z badania Sauerbrei, W., and P. Royston 1999.
• Zbiór składa się z grupy obserwacji 686 pacjentek, które zostały poddane leczeniu
nowotworu piersi.
• Zmienne ujęte zbiorze:
o time – zmienna określająca dzień od rozpoczęcia obserwacji w którym pacjentka umarła lub
jej obserwacja została ucięta
o cens – zmienna binarna określająca to czy obserwacja została ocenzurowana czy nie – {0,1)
o age – zmienna ciągła, wiek pacjentki w latach
o tsize – wielkość guza w [mm]
o menostat – status pacjentki, przed menopauzą 0, po menopauzie 1
o pnodes – liczba ognisk nowotworowych
o tgrade – stopień zaawansowania guza: {1,2,3} – 3 najwyższy stopień
o progrec – ilość receptorów progesteronowych w [fmol]
