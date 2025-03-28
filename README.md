# 🔬 Klasyfikator Raka Skóry

## 📋 Opis projektu
Ten projekt wykorzystuje uczenie maszynowe do klasyfikacji różnych typów zmian skórnych, w tym nowotworów złośliwych, przy użyciu zbioru danych HAM10000. Implementacja obejmuje dwa podejścia:
- Model CNN zbudowany od podstaw
- Model z wykorzystaniem transfer learningu (MobileNetV2)

## 💉 Klasyfikowane typy zmian
- **akiec**: Rogowacenie słoneczne / Rak kolczystokomórkowy (in situ)
- **bcc**: Rak podstawnokomórkowy
- **bkl**: Łagodne zmiany keratotyczne
- **df**: Włókniak twardy (dermatofibroma)
- **nv**: Znamię melanocytowe
- **mel**: Czerniak
- **vasc**: Zmiany naczyniowe

## 🛠️ Technologie
- Python 3.x
- TensorFlow/Keras
- Scikit-learn
- Pandas
- NumPy
- Matplotlib
- PIL (Python Imaging Library)

## 📂 Struktura projektu
```
SkinCancerClassifier/
│
├── notebook.ipynb          # Główny notebook z implementacją
├── models/                 # Katalog z zapisanymi modelami
│   ├── model_cnn.h5       # Model CNN
│   └── model_tl.h5        # Model Transfer Learning
│
└── README.md              # Dokumentacja projektu
```

## ⚙️ Funkcjonalności
1. **Przetwarzanie danych**
   - Automatyczne pobieranie datasetu HAM10000
   - Przygotowanie i augmentacja danych
   - Podział na zbiory treningowy, walidacyjny i testowy

2. **Wizualizacja danych**
   - Przykłady obrazów dla każdej klasy
   - Rozkład klas w zbiorze danych
   - Wykresy procesu uczenia

3. **Modele**
   - CNN od podstaw
   - Transfer Learning z MobileNetV2
   - Zapisywanie najlepszych modeli

4. **Ewaluacja**
   - Macierze pomyłek
   - Dokładność klasyfikacji
   - Porównanie wyników obu modeli

## 🚀 Jak uruchomić
1. Sklonuj repozytorium
2. Zainstaluj wymagane biblioteki:
```bash
pip install tensorflow pandas numpy matplotlib scikit-learn pillow kagglehub
```
3. Uruchom notebook `notebook.ipynb`
4. Wykonuj komórki po kolei, aby przejść przez cały proces

## 📊 Wyniki

### Model CNN
- Dokładność: 50.85%
- Macierz pomyłek:
![CNN Confusion Matrix](evaluation/percentage_confusion_matrix_cnn.png)

### Model Transfer Learning (MobileNetV2)
- Dokładność: 57.04%
- Macierz pomyłek:
![Transfer Learning Confusion Matrix](evaluation/percentage_confusion_matrix_tl.png)

### 📈 Porównanie modeli
| Model | Dokładność | Zalety | Wady |
|-------|------------|--------|------|
| CNN   | 50.85%    | • Szybszy trening | • Niższa dokładność<br>• Większy rozmiar |
| TL    | 57.04%    | • Wyższa dokładność<br>• Lepsza generalizacja | • Dłuższy czas treningu |

## 📝 Przypisy
Projekt wykorzystuje zbiór danych HAM10000, który jest publicznie dostępnym zbiorem dermatoskopowych obrazów zmian skórnych.

## 👨‍💻 Autor
[LiCHUTKO](https://github.com/LiCHUTKO)

## 🔗 Referencje
- 📚 [HAM10000 Dataset](https://www.kaggle.com/datasets/kmader/skin-cancer-mnist-ham10000)
- 📄 [MobileNetV2 Paper](https://arxiv.org/abs/1801.04381)

## 📈 Wykresy uczenia

### Model CNN
![Learning Curves CNN](learning_curves/learning_curves_cnn.png)

### Model Transfer Learning
![Learning Curves TL](learning_curves/learning_curves_tl.png)