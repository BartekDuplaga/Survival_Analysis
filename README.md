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
* Zmienna ciągła age została zdychotomizowana wzdłuż mediany wynoszącej 53. Empiryczny rozkład tej zmiennej przypominający rozkład dwumianowy uzasadnia taki wybór. Pacjentki poniżej 53 roku życia zostały przydzielonej do młodszej grupy wiekowej – 1, pacjentki powyżej 53 roku życia do starszej grupy wiekowej - 2.
* Estymacja nieparametryczna funkcji dożycia w grupach metodą K-M wykazała brak istotności różnic w przeżywalności wyszczególnionych grup dla przyjętego poziomu istotności 0.05.

<img src="https://github.com/BartekDuplaga/Survival_Analysis/blob/master/images/Non_parametric_age.png" alt="KM_estimates" width="600" height="600" />

4.4 **Analiza czasu przeżycia pacjentek w jednoczesnym podziale na grupy wiekowe oraz udział w terapii hormonalnej:**
</br>Wszystkie statystyki testowe nakazują odrzucenie hipotezy zerowej mówiącej o braku różnic w funkcji dożycia pomiędzy 4 rozróżnionymi grupami dla przyjętego poziomu istotności 0.05.
</br>Najbardziej narażoną grupą pacjentek są pacjentki starsze niepoddane terapii hormonalnej a najmniej pacjentki młodsze poddane terapii hormonalnej.
</br> Po przeliczeniu różnic w grupach z uwzględnieniem poprawki Tukeya dla testu Wilcoxona, brak podstaw do odrzucenia hipotezy zerowej o różnicach pomiędzy grupami 1 i 4, 2 i 3 oraz 3 i 4 – co potwierdza zasadność rozróżnienia pomiędzy grupą najbardziej i najmniej narażoną na ryzyko czyli grupą starszych kobiet niepoddanych terapii hormonalnej a grupą młodszych kobiet poddanych tej terapii (grupy 2 i 3).

<img src="https://github.com/BartekDuplaga/Survival_Analysis/blob/master/images/Non_parametric_age_horTh.png" alt="KM_estimates" width="600" height="600" />
<img src="https://github.com/BartekDuplaga/Survival_Analysis/blob/master/images/Tukey_adj_LogRank.png" alt="KM_estimates" width="300" height="200" />
**PARAMETRIC MODELS** </br>
5.1 **Funkcja hazardu wyestymowana z tablic trwania życia**
<img src="https://github.com/BartekDuplaga/Survival_Analysis/blob/master/images/Empirical_hazard_function.png" alt="KM_estimates" width="600" height="600" />
</br>Niemonotoniczność empirycznej funkcji hazardu nakazuje odrzucenie parametrycznej analizy rozkładem wykładniczym
lub Weibulla.

5.2 **Wygładzona jądrowo funkcja hazardu** </br>
* Za szerokość pasma przyjęto 570 dni – co oznacza, że obserwacje o takiej rozpiętości przyjęto do obliczania hazardów w
danych momentach czasowych w celu wygładzenia funkcji hazardu. Pasmo nie zostało ręcznie sprecyzowane lecz zostało
zaproponowane przez optymalizator wygładzania. Na wykres naniesiono 95%przedziały ufności.
<img src="https://github.com/BartekDuplaga/Survival_Analysis/blob/master/images/Epanechnikov_smoothing.png" alt="KM_estimates" width="600" height="600" />




