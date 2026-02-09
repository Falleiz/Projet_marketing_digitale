# 📊 Projet CVM : Segmentation Client & Plan d'Activation

## 🎯 Contexte du Projet

Ce projet s'inscrit dans le cadre du cours **Marketing Digital et Outils IA** (3A Cycle Ingénieur - Sciences de Données et Digitalisation - ECC).

### Objectif
Mettre en pratique les compétences de **Customer Value Management (CVM)** pour :
1. Explorer une base de clients prépayés anonymisée d'un opérateur télécom.
2. Réaliser une **segmentation robuste** des clients (**8 segments attendus**).
3. Caractériser finement chaque segment (profil usage, valeur...).
4. Proposer un **plan d'animation CVM** adapté à chaque segment.

### Dataset
Le fichier `base_seg_gsm.csv` contient **8000 clients** avec les variables suivantes :

| Variable | Description |
|----------|-------------|
| `ID` | Identifiant unique du client |
| `MMPR` | Montant Moyen Par Recharge (proxy de l'ARPU) |
| `FREQR` | Fréquence de Recharge |
| `POIDS_VAS` | Part des Services à Valeur Ajoutée (jeux, sonneries...) |
| `POIDS_IN` | Part des appels entrants |
| `POIDS_IN_OFFN` | Part des appels entrants depuis la concurrence |
| `POIDS_OPK` | Part des communications Off-Peak (heures creuses) |
| `POIDS_ONG` | Part des communications Off-Net sortantes (vers concurrence) |
| `POIDS_INT` | Part des communications internationales |
| `POIDS_ONN` | Part des communications On-Net (même opérateur) |
| `SMART_PHONE` | Client équipé d'un smartphone (0/1) |
| `MULTI_EQUIPE` | Client possédant plusieurs SIM (0/1) |
| `USERS_INTERNET` | Client utilisant la Data (0/1) |

---

## 🛠️ Setup

### Prérequis
- **Python 3.12.10**

### Installation

1. Cloner le dépôt ou télécharger les fichiers.

2. Créer un environnement virtuel (recommandé) :
```bash
python -m venv venv
# Windows
venv\Scripts\activate
# Linux/Mac
source venv/bin/activate
```

3. Installer les dépendances :
```bash
pip install -r requirements.txt
```

### Librairies principales utilisées
- `pandas` : Manipulation de données
- `numpy` : Calculs numériques
- `matplotlib` & `seaborn` : Visualisation
- `scikit-learn` : Clustering (K-Means) et preprocessing

---

## 📓 Ce qui est déjà fait dans le notebook (`cvm.ipynb`)

### 1. Configuration de l'environnement
- [x] Import des librairies (pandas, numpy, matplotlib, seaborn, sklearn)
- [x] Chargement du dataset `base_seg_gsm.csv`

### 2. Analyse Exploratoire des Données (EDA)
- [x] Statistiques descriptives (info, describe)
- [x] Vérification des valeurs manquantes (aucune)
- [x] Distribution des variables (histogrammes, boxplots)
- [x] Matrice de corrélation (heatmap)

### 3. Preprocessing
- [x] Standardisation des données (StandardScaler)

### 4. Modélisation : Segmentation K-Means
- [x] Application de K-Means avec K=8 (conformément à la consigne)
- [x] Calcul du score de Silhouette (~0.22)
- [x] Profiling des clusters (moyennes par segment)

### 5. Visualisation des résultats
- [x] Snake Plot montrant les caractéristiques de chaque segment

### 6. Export
- [x] Sauvegarde des résultats dans `resultats_segmentation_cvm.csv`

---

## 📝 Ce qui reste à faire (Livrable attendu)

Le livrable final est un **PowerPoint de 12 à 20 slides** contenant :

| Élément | Status | Description |
|---------|--------|-------------|
| **Analyse exploratoire** | ✅ Données prêtes | Stats descriptives, visualisations, interprétation |
| **Segmentation (8 segments)** | ✅ Fait | Méthodologie K-Means, résultats |
| **Profiling de chaque segment** | ⚠️ À rédiger | Nommer chaque segment, créer des "fiches segment" |
| **Plan CVM** | ❌ À faire | Actions marketing ciblées par segment |
| **Design PowerPoint** | ❌ À faire | Mise en forme pro, storytelling visuel |

### Segments identifiés (à affiner dans le PPT)

| Cluster | Nom proposé | Caractéristiques clés |
|---------|-------------|----------------------|
| 0 | High Value Smartphone | MMPR élevé, 99% smartphone, On-Net |
| 1 | Receveurs Low Cost | Faible budget, essentiellement récepteurs |
| 2 | Appelants Off-Net | Forte communication vers concurrence |
| 3 | Fans de VAS | Services à valeur ajoutée (75%) |
| 4 | Standard Mass Market | Le client moyen (2144 clients) |
| 5 | Zappeurs Multi-SIM | Multi-équipés, reçoivent de la concurrence |
| 6 | International | 74% de communications internationales |
| 7 | Data Users | 100% utilisateurs internet |

### Recommandations CVM à développer

Pour chaque segment, proposer :
- **Canal de communication** (SMS, Push, Appel, Agence...)
- **Type d'offre** (Fidélisation, Upsell, Rétention, Réactivation)
- **Exemple d'action concrète** (ex: "Pass International -30%" pour le segment 6)

---

## 📁 Structure du projet

```
Projet_marketing_digitale/
├── base_seg_gsm.csv              # Dataset source
├── cvm.ipynb                     # Notebook d'analyse principal
├── resultats_segmentation_cvm.csv # Résultats de la segmentation
├── requirements.txt              # Dépendances Python
└── README.md                     # Ce fichier
```

---

## 👥 Auteurs

- **BELEMCOABGA Rosteim Falleiz**
- **RBIB Marouane**
- **MENDY Vincent**

Projet réalisé dans le cadre du Cycle Ingénieur 3A - Sciences de Données et Digitalisation - ECC (2025-2026)
