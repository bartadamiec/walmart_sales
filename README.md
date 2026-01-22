## Bartłomiej Adamiec

**Dlaczego te dane?**

Poszukiwałem datasetu, który będzie jak najbardziej komercyjny, abym mógł pokazać to w CV. Dataset wyróżnia się na tle innych tym, że ma wpisane święta dla Stanów Zjednoczonych oraz dni, w których wydawane są kwoty pieniężne do spożytkowania na jedzenie dzięki programowi SNAP (czynniki egzogeniczne). Dataset wymaga prognozowania dla 30 490 równoległych szeregów czasowych zgrupowanych hierarchicznie Stany → Sklepy → Kategorie → Działy → Produkty.

**Cel:**

Celem analizy jest optymalizacja zarządzania zapasami żywności w celu uniknięcia braków towarowych oraz nadmiernego magazynowania szczególnie dla żywności świeżej.

**Kaggle:**

Popularna platforma społecznościowa dla analityków danych i inżynierów uczenia maszynowego. Są tam organizowane konkursy dla społeczności, gromadzone są zbiory danych, przykładowe notatniki jupyter i pobobne rzeczy, które mogą być interesujące dla społeczności Data Sciencist'ów.

**Opis datasetu:**

Dane konkursowe (M5 Forecasting - Accuracy) z Kaggle. Zadaniem w konkursie było przewidzenie sprzedaży produktów w sieci sklepów Walmart na następne 28 dni. Dataset składa się z 5 plików csv przypominających relacyjną bazę danych w schemacie gwiazdy. Historia sprzedaży (`sales_train_validation.csv`) to główna tabela, a czas (`calendar.csv`) i cena (`sales_prices.csv`) to oddzielne tabele.

**Krótkie opisy plików:**

* `sell_prices.csv` - ceny produktów netto w USD
* `calendar.csv` - daty w różnej postaci oraz święta
* `sales_train_validation.csv` -  ile danego produktu sprzedało się w danym dniu. Dane w formacie szerokim. Dane obejmują zakres 1913 dni
* `sales_train_evaluation.csv` - identyczne do validation, tylko zawiera w sobie 28 następnych dni. Został dodany po zakończeniu konkursu.
* `sample_submission.csv` - przykład formatu w jakim uczestnicy powinni oddać zadanie

[Źródło](https://www.kaggle.com/competitions/m5-forecasting-accuracy/datam)
