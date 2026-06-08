# CNN-projekt: Bildklassificering med CIFAR-10

Gruppprojekt i Deep Learning — bygger och utvärderar ett Convolutional Neural Network (CNN) för bildklassificering på CIFAR-10-datasetet.

## Dataset

**CIFAR-10** — 60 000 RGB-bilder (32×32 px) fördelade på 10 klasser:
`airplane, automobile, bird, cat, deer, dog, frog, horse, ship, truck`

- 50 000 träningsbilder
- 10 000 testbilder

## Projektstruktur

```
CNN_projekt_CIFAR10/
├── CNN_CIFAR10.ipynb          # Huvudnotebook med all kod och analys
├── requirements.txt           # Paketberoenden
└── README.md
```

## Modeller

### Modell 1 — Baseline CNN
- 3 konvolutionslager (32 → 64 → 128 filter)
- MaxPooling efter varje lager
- Dense(128) + softmax-utgångslager
- Tränas upp till 30 epoker med EarlyStopping

### Modell 2 — Förbättrad CNN
- Dubbla konvolutionslager per block
- Dropout (0.25 / 0.3 / 0.5) för att motverka overfitting
- Data Augmentation (rotation, förskjutning, horisontell spegling, zoom)
- Dense(256) + softmax-utgångslager
- Tränas upp till 50 epoker med EarlyStopping

## Kom igång

### 1. Installera beroenden
```bash
pip install -r requirements.txt
```

### 2. Starta Jupyter
```bash
jupyter notebook CNN_CIFAR10.ipynb
```

### 3. Kör cellerna i ordning
Datasetet laddas automatiskt via `tensorflow.keras.datasets.cifar10`.

## Ramverk

- Python 3.x
- TensorFlow 2.x / Keras
- NumPy, Matplotlib, Seaborn, scikit-learn
