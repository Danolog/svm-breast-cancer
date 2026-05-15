# SVM — Klasyfikacja nowotworów piersi (Breast Cancer Wisconsin)

> Projekt zaliczeniowy z przedmiotu *Wstęp do sztucznej inteligencji* (Laboratorium 3, WSB MERITO).
> Klasyfikator **Support Vector Machine** trenowany na zbiorze **Breast Cancer Wisconsin** z biblioteki scikit-learn.

## Cel projektu

Zbudować klasyfikator SVM rozpoznający, czy guz piersi jest złośliwy czy łagodny, oraz przeanalizować wpływ:

- parametru regularyzacji **C**,
- typu jądra (**linear** vs **rbf**),
- standaryzacji cech (`StandardScaler`).

## Najważniejsze wyniki

### Dokładność klasyfikacji (zbiór testowy)

| Konfiguracja | Accuracy |
|---|---|
| **SVC, kernel=linear, C=1.0** (najlepszy) | **0.9825** |
| SVC, kernel=rbf, C=1.0 | 0.9766 |
| SVC, kernel=rbf, C=10.0 | 0.9766 |
| SVC, kernel=linear, C=0.1 | 0.9708 |

### Wpływ standaryzacji

| Konfiguracja | Accuracy ze standaryzacją | Accuracy bez standaryzacji | Różnica |
|---|---|---|---|
| rbf, C=1.0 | 0.9766 | 0.9064 | **+7.0 p.p.** |
| linear, C=1.0 | 0.9825 | 0.9532 | **+2.9 p.p.** |

### Macierz konfuzji — najlepszy model (linear, C=1.0)

|                  | Predykcja: malignant | Predykcja: benign |
|---|---|---|
| Rzeczywiste: malignant | 62 | 2 *(false negatives)* |
| Rzeczywiste: benign    | 1 *(false positive)* | 106 |

**Recall klasy malignant:** 96.9% (kluczowa miara w kontekście medycznym).

## Kluczowe wnioski

- Zbiór po standaryzacji jest w przybliżeniu **liniowo separowalny** — proste jądro liniowe wygrywa z RBF.
- **Standaryzacja jest niezbędna** dla SVM, szczególnie z jądrem RBF (wzrost accuracy o ~7 p.p.).
- Accuracy nie wystarcza w problemach medycznych — istotniejszy jest **recall klasy mniejszościowej** (false negatives w diagnostyce nowotworu są dużo groźniejsze niż false positives).

Pełna analiza, wykresy i wnioski znajdują się w [raporcie PDF](report/raport.pdf).

## Struktura repozytorium

```
svm-breast-cancer/
├── notebooks/
│   └── svm_breast_cancer.ipynb   # Główny notebook z analizą
├── report/
│   └── raport.pdf                 # Raport zaliczeniowy (PL)
├── figures/                       # Pojedyncze wykresy (PNG, jeśli wyeksportowane)
├── requirements.txt
├── .gitignore
└── README.md
```

## Jak uruchomić

```bash
# 1. Sklonuj repo
git clone https://github.com/<TWOJ-LOGIN>/svm-breast-cancer.git
cd svm-breast-cancer

# 2. Utwórz i aktywuj środowisko wirtualne
python -m venv venv
# Windows:
venv\Scripts\activate
# macOS/Linux:
source venv/bin/activate

# 3. Zainstaluj zależności
pip install -r requirements.txt

# 4. Uruchom notebook
jupyter notebook notebooks/svm_breast_cancer.ipynb
```

## Wykorzystane technologie

- **Python 3.11+**
- **scikit-learn** — SVM, preprocessing, metryki, F-test
- **NumPy**, **pandas** — manipulacja danymi
- **Matplotlib** — wizualizacja (scatter plot, macierze konfuzji)
- **Jupyter Notebook** — środowisko analityczne

## Autor

Dariusz Gradzik — student WSB MERITO, kierunek Informatyka, Data Science

## Licencja

Projekt edukacyjny, MIT License.
