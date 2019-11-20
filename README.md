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

4.1. **Analiza nieparametryczna - estymacja metodą Kaplana-Meiera:** </br>
* Mediana funkcji przeżycia wskazuje, że połowa pacjentów przeżyła do minimum do **1806** dnia badania.
* Prawdopodobieństwo przeżycia do końca obserwacji (t=2700)wyniosło na tym zbiorze **0.34**.

<img src="https://github.com/BartekDuplaga/Survival_Analysis/blob/master/images/Kaplan_Meier_Estimates.png" alt="KM_estimates" width="600" height="600" />

4.2. **Analiza czasu przeżycia pacjentek poddanych i niepoddanych terapii hormonalnej:**
* Pacjentki poddane terapii hormonalnej (horTh=1) miały statystycznie dłuższy czas dożycia okresie obserwacji.
* Przy poziomie istotności 0.05 dla każdego z wykonanych testów (log-rang i Wilcoxona) należy odrzucić hipotezę zerową od braku różnic w grupach.
<img src="https://github.com/BartekDuplaga/Survival_Analysis/blob/master/images/Non-parametric%20horTh.png" alt="KM_estimates" width="600" height="600" />

4.3 **Analiza czasu przeżycia pacjentek w podziale na grupy wiekowe:**
</br>
Analiza czasu przeżycia pacjentek ze względy przynależności do grupy wiekowej:
* Zmienna ciągła age została zdychotomizowana wzdłuż mediany wynoszącej 53. Empiryczny rozkład tej zmiennej przypominający rozkład dwumianowy uzasadnia taki wybór. Pacjentki poniżej 53 roku życia zostały przydzielonej do młodszej grupy wiekowej – 1, pacjentki powyżej 53 roku życia do starszej grupy wiekowej - 2.
* Estymacja nieparametryczna funkcji dożycia w grupach metodą K-M wykazała brak istotności różnic w przeżywalności wyszczególnionych grup dla przyjętego poziomu istotności 0.05.

<img src="https://github.com/BartekDuplaga/Survival_Analysis/blob/master/images/Non_parametric_age.png" alt="KM_estimates" width="600" height="600" />





