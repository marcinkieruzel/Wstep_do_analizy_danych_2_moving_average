# Szeregi czasowe – temperatura w Warszawie

Dwa ćwiczenia z analizy szeregów czasowych w pandas: średnie kroczące i czyszczenie danych.

## Przygotowanie

```bash
python3 -m venv .venv
source .venv/bin/activate        # Windows: .venv\Scripts\activate
pip install -r requirements.txt
```

Zadanie 1 rozwiąż w notebooku `index.ipynb`, a zadanie 2 w `cleaning_data.ipynb`.

---

## Zadanie 1. Średnia krocząca

Na podstawie 85 lat pomiarów sprawdzisz, jak zmienia się temperatura w Warszawie.

### Dane

`open-meteo.csv` – temperatura powietrza na wysokości 2 m (°C), co godzinę, od 1 stycznia 1940 do 31 grudnia 2025. Źródło: [Open-Meteo](https://open-meteo.com/) (Historical Weather API).

Plik zawiera opis pięciu lokalizacji oraz pomiary temperatury dla każdej z nich.

| `location_id` | Miasto |
| --- | --- |
| 0 | Warszawa |
| 1 | Kraków |
| 2 | Gdańsk |
| 3 | Wrocław |
| 4 | Poznań |

Pracujesz na danych dla Warszawy.

### Kroki

1. **Wczytaj dane.** Obejrzyj pierwsze wiersze i sprawdź typy kolumn.
2. **Zamień daty na datetime.** Kolumna z czasem ma mieć typ daty, a nie tekstu.
3. **Ustaw indeks.** Indeksem ma być czas pomiaru.
4. **Uzupełnij braki.** Sprawdź, ile pomiarów brakuje, i uzupełnij je.
5. **Pokaż wykres** temperatury w Warszawie dla całego okresu.
6. **Policz średnią kroczącą**, która pokaże trend zmian temperatury, i dodaj ją do wykresu.

### Pytania

- Jak długość okna średniej kroczącej zmienia wykres?
- Czy w Warszawie robi się cieplej? O ile stopni w ciągu 85 lat?

---

## Zadanie 2. Czyszczenie danych

Prawdziwe pomiary ze stacji meteorologicznych mają luki i błędy. Twoim zadaniem jest je znaleźć i naprawić.

### Dane

`temperatura_godzinowa_ISD_1975-2025.csv` – pomiary temperatury powietrza (°C) ze stacji meteorologicznych, co godzinę, od stycznia 1975 do sierpnia 2025. Źródło: NOAA ISD.

| Kolumna | Opis |
| --- | --- |
| `time_utc` | data i godzina pomiaru (UTC) |
| `Warszawa_Okecie` | temperatura na lotnisku Okęcie |
| `Krakow_Balice`, `Frankfurt`, `Hannover`, `Boston_Logan` | inne stacje |

Pracujesz na kolumnie `Warszawa_Okecie`.

### Kroki

1. **Wczytaj dane**, zamień czas na datetime i ustaw go jako indeks.
2. **Sprawdź braki.** Ile pomiarów brakuje? Jak długie są luki?
3. **Sprawdź, czy w danych są wszystkie godziny.**
4. **Znajdź wartości, które nie mogą być prawdziwe**, i potraktuj je jak braki.
5. **Uzupełnij braki co najmniej trzema różnymi metodami.**
6. **Porównaj metody** na wykresie wybranego tygodnia z lukami.
7. **Wybierz najlepszą metodę** i uzasadnij wybór.

### Pytania

- Która metoda sprawdza się przy krótkich lukach, a która przy długich?
- Jak sprawdzić, która metoda jest najlepsza, skoro nie znasz prawdziwych wartości?

---

## Dla chętnych

- Porównaj trend w Warszawie z innym miastem z pliku `open-meteo.csv`.
- Porównaj oczyszczone dane ze stacji na Okęciu z danymi Open-Meteo dla Warszawy.

---

## Źródła danych

- `open-meteo.csv` – [Open-Meteo](https://open-meteo.com/), licencja [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)
- `temperatura_godzinowa_ISD_1975-2025.csv` – [NOAA Integrated Surface Database (ISD)](https://www.ncei.noaa.gov/products/land-based-station/integrated-surface-database)
