# Survival_Analysis (Breast Cancer, GBSG2 Study)
Analiza przeżycia pacjentek poddanych terapii hormonalnej w trakcie leczenia onkologicznego.

1. **Dane** :</br>
Zbiór danych GBSG2 pochodzi z badania Sauerbrei, W., and P. Royston 1999. Zbiór składa się z grupy obserwacji 686 pacjentek, które zostały poddane leczeniu nowotworu piersi.

Zmienne ujęte zbiorze: </br>
  * time – zmienna określająca dzień od rozpoczęcia obserwacji w którym pacjentka umarła lub
jej obserwacja została ucięta
  * cens – zmienna binarna określająca to czy obserwacja została ocenzurowana czy nie – {0,1)
  * age – zmienna ciągła, wiek pacjentki w latach
  * tsize – wielkość guza w [mm]
  * menostat – status pacjentki, przed menopauzą 0, po menopauzie 1
  * pnodes – liczba ognisk nowotworowych
  * tgrade – stopień zaawansowania guza: {1,2,3} – 3 najwyższy stopień
  * progrec – ilość receptorów progesteronowych w [fmol]
  * estrec – ilość receptorów estrogenowych w [fmol]
  * horTh – zmienna binarna oznaczająca bycie poddanym terapii hormonalnej

2. **Cel badawczy** – ocena wpływu czynników na przeżywalność pacjentek poddanych terapii leczenia nowotworu piersi.
3. **Hipotezy badawcze**:
  * Im wyższy wiek pacjentki tym krótszy czas przeżycia podczas terapii nowotworowej.
  * Terapia hormonalna wydłuża czas przeżycia podczas leczenia nowotworu.

4. **Analiza nieparametryczna - estymacja metodą Kaplana-Meiera:** </br>
Mediana funkcji przeżycia wskazuje, że połowa pacjentów przeżyła do minimum do **1806** dnia badania.
Prawdopodobieństwo przeżycia do końca obserwacji (t=2700)wyniosło na tym zbiorze **0.34**.

<img src="https://github.com/BartekDuplaga/Survival_Analysis/blob/master/Kaplan-Meier-Estimates.png" alt="KM_estimates" width="600" height="450" />
