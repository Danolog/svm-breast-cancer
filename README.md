# SVM — Klasyfikacja nowotworów piersi (Breast Cancer Wisconsin)

> Projekt zaliczeniowy z przedmiotu *Wstęp do sztucznej inteligencji* (Laboratorium 3).
> Klasyfikator **Support Vector Machine** trenowany na zbiorze **Breast Cancer Wisconsin** z biblioteki scikit-learn.

## Cel projektu

Zbudować klasyfikator SVM rozpoznający, czy guz piersi jest złośliwy czy łagodny, oraz przeanalizować wpływ:

- parametru regularyzacji **C**,
- typu jądra (**linear** vs **rbf**),
- standaryzacji cech (`StandardScaler`).

## Wyniki w skrócie

| Konfiguracja | Accuracy (test) |
|---|---|
| _wypełnić po eksperymentach_ | _wypełnić_ |

(Pełne wyniki — zob. notebook i raport.)

## Struktura repozytorium

```
svm-breast-cancer/
├── notebooks/
│   └── svm_breast_cancer.ipynb   # Główny notebook z analizą
├── report/
│   └── raport.pdf                 # Raport zaliczeniowy (PL)
├── figures/                       # Pojedyncze wykresy (PNG)
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

- Python 3.11+
- scikit-learn — SVM, preprocessing, metryki
- NumPy, pandas — manipulacja danymi
- Matplotlib — wizualizacja
- Jupyter Notebook — środowisko analityczne

## Autor

Darek — student WSB, kierunek _(uzupełnij)_

## Licencja

Projekt edukacyjny.
