# Activité Pratique N°1 – Prise en main de PyTorch

## 📌 Présentation

Ce projet est une introduction pratique au framework **PyTorch**. Il part de la manipulation des tenseurs et va jusqu'à la construction, l'entraînement et l'évaluation de modèles de **Machine Learning** et de **Deep Learning**.

Il se divise en deux parties :

- **Partie 1 :** les bases de PyTorch
- **Partie 2 :** applications en Machine Learning et Deep Learning

---

## 🟦 Partie 1 : les bases de PyTorch

**Objectifs :** configurer l'environnement, comprendre ce qu'est un tenseur, savoir le créer et le manipuler, et poser les bases nécessaires au Deep Learning.

**Contenu :**

1. **Installation et configuration** : Python, environnement virtuel, PyTorch, VS Code et Jupyter Notebook.
2. **Découverte des tenseurs** : création, dimensions et formes, types de données, accès aux éléments et modification.
3. **Opérations sur les tenseurs** : addition, soustraction, multiplication, fonctions mathématiques, changement de forme et conversion de types.
4. **Premières notions de Deep Learning** : tenseurs comme données d'entrée, préparation des données, modèle, fonction de perte et optimisation.

---

## 🟩 Partie 2 : modèles de Machine Learning et Deep Learning

Cette partie met en pratique les notions précédentes à travers quatre exercices couvrant la régression, la classification et la vision par ordinateur.

### Exercice 1 : régression (prédiction de salaire)
- **But :** prédire un salaire à partir de l'ancienneté et du niveau d'expertise.
- **Méthode :** données synthétiques, découpage train/test, normalisation, modèle `nn.Linear`, perte `MSELoss`, optimiseur `SGD`, évaluation par la **MAE**.
- **Architecture :** `Linear(2 → 1)`

### Exercice 2 : classification (dataset Iris)
- **But :** distinguer trois espèces : Setosa, Versicolor et Virginica.
- **Méthode :** données Scikit-learn, standardisation (`StandardScaler`), réseau multicouche avec `ReLU`, perte `CrossEntropyLoss`, optimiseur `Adam`, évaluation par accuracy et matrice de confusion.
- **Architecture :** `Linear(4 → 16)` → `ReLU` → `Linear(16 → 3)`

### Exercice 3 : MLP sur MNIST
- **But :** reconnaître des chiffres manuscrits avec un perceptron multicouche.
- **Architecture :** `Flatten` → `Linear(784 → 128)` → `ReLU` → `Linear(128 → 10)`
- **Points étudiés :** `DataLoader`, entraînement par mini-batch, `CrossEntropyLoss`, `Adam`, métriques (accuracy, precision, recall, F1-score), matrice de confusion, analyse des images mal classées, sauvegarde et chargement du modèle.

### Exercice 4 : CNN sur MNIST
- **But :** améliorer les résultats de l'exercice 3 grâce à un réseau convolutif.
- **Architecture :** `Conv2d` → `ReLU` → `MaxPool2d` (×2) → `Flatten` → `Linear` → `ReLU` → `Dropout` → `Linear(128 → 10)`
- **Points étudiés :** couches convolutives, `Dropout`, évaluation, visualisation des erreurs, sauvegarde via `state_dict`.

---

## 🛠️ Technologies

Python 3.11, PyTorch, Torchvision, Scikit-learn, NumPy, Matplotlib, VS Code, Jupyter Notebook, Git et GitHub.

---

## ⚙️ Installation

Le projet est géré avec [uv](https://docs.astral.sh/uv/) (`pyproject.toml` + `uv.lock`).

```bash
# 1. Cloner le dépôt (remplacer par l'URL de votre dépôt)
git clone https://github.com/<votre-utilisateur>/<nom-du-depot>.git
cd <nom-du-depot>

# 2. Créer l'environnement et installer les dépendances (Python 3.11)
uv sync
```

Sans `uv`, il est aussi possible d'utiliser `pip` :

```bash
python -m venv .venv
.venv\Scripts\Activate.ps1     # Windows (PowerShell)
pip install torch torchvision scikit-learn matplotlib numpy torcheval torchmetrics torchviz ipykernel
```

> `torchviz` nécessite l'outil système [Graphviz](https://graphviz.org/download/) pour générer les graphes de calcul.

## ▶️ Exécution

- **Avec VS Code :** ouvrir le dossier, choisir l'interpréteur `.venv`, ouvrir un notebook et exécuter les cellules une à une.
- **Avec Jupyter :** lancer `uv run jupyter notebook` (ou `jupyter notebook` si l'environnement est activé), puis ouvrir le notebook voulu.

Les exercices 3 et 4 téléchargent automatiquement MNIST dans le dossier `data/` (ignoré par Git).

---

## 📂 Structure du projet

```text
.
├── Activité pratique Bases de Pytorch.ipynb   # Partie 1 : bases de PyTorch
├── lab1.ipynb                                 # Tenseurs, autograd (prise en main)
├── reg.ipynb                                  # Régression linéaire simple
├── Exercice_1.ipynb                           # Régression : prédiction du salaire
├── Exercice_2.ipynb                           # Classification : Iris
├── Exercice_3.ipynb                           # MLP sur MNIST
├── Exercice_4.ipynb                           # CNN sur MNIST (avec Dropout)
├── mnist_mlp.pth                              # Poids du MLP (Exercice 3)
├── mnist_cnn.pth                              # Poids du CNN (Exercice 4)
├── main.py
├── pyproject.toml / uv.lock / .python-version
├── README.md
└── .gitignore
```

> Les dossiers `.venv/` (environnement local) et `data/` (MNIST téléchargé) ne doivent pas être poussés sur GitHub : ils sont listés dans `.gitignore`.

---

## 📊 Évaluation

- **Régression :** MAE
- **Classification :** accuracy, precision, recall, F1-score, matrice de confusion et visualisation des erreurs

## 🎓 Compétences acquises

Mise en place d'un environnement Python, manipulation de tenseurs, préparation et normalisation des données, construction et entraînement de réseaux (MLP et CNN), choix des fonctions de perte et des optimiseurs, évaluation, visualisation, sauvegarde et chargement de modèles, et gestion d'un projet avec Git et GitHub.

---

## 👨‍💻 Auteur

Saad Sainane – Activité Pratique N°1 : mise en œuvre du framework PyTorch.
---
