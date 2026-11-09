![lyon2 geonum](https://perso.liris.cnrs.fr/lmoncla/GEONUM/fig/logos.png)

# Master GEONUM - 2F2 - Gestion et traitement des données spatio-temporelles
***

Ce dépôt git contient les fichiers pour le cours "2F2 - Gestion et traitement des données spatio-temporelles" du Master [GEONUM](https://mastergeonum.org/programme/).


L'objectif de ce tutoriel est d'appréhender la problématique d'analyse de données spatio-temporelles grâce à l'utilisation de librairies Python.
Pour cela nous allons travailler sur un cas d'étude visant la visualisation et le traitement des données de disponibilités des stations Vélo'v de la Métropole de Lyon. 

**Information** Pour ceux qui ont des difficultés à installer un environnement python sur leur ordinateur, vous pouvez simplement executer les notebooks (`.ipynb`) à distance avec [Google Colab](http://colab.research.google.com) (*Compte Google requis*).


*******
Cheat Sheets :
* [Pandas Cheat sheet](https://pandas.pydata.org/Pandas_Cheat_Sheet.pdf)
* [Python for Data Science Cheat sheet](https://www.utc.fr/~jlaforet/Suppl/python-cheatsheets.pdf) (Pandas, Matplotlib, Scikit-Learn, etc.)


*******

La suite de ce document explique comment installer et configurer un environnement python avec conda et installer toutes les bibliothèques requises.

***

## 1. Installer conda

[Conda](https://conda.io/projects/conda/en/latest/index.html) est un système de gestion de paquets et d'environnement à code source ouvert. Il installe, exécute et met à jour rapidement les paquets et leurs dépendances. 
Nous l'utiliserons pour gérer l'environnement python et toutes les bibliothèques python nécessaires pour les tutoriels.
Il existe plusieurs façons d'installer conda sur votre ordinateur:
1. [Anaconda distribution](https://www.anaconda.com/products/distribution): fournit des applications GUI et de nombreux paquets de science des données déjà installés.
2. [Miniconda](https://docs.conda.io/en/latest/miniconda.html): un installateur minimal pour conda, sans application GUI
3. [Miniforge](https://github.com/conda-forge/miniforge): un autre installateur minimal pour conda, sans application GUI (recommandé pour les puces Mac M* (Apple Silicon))

## 2. Configurer un environnement Conda

### 2.1 Télécharger les fichiers de configuration

* Cloner ce dépôt github

```bash
git clone https://github.com/bcahier/geonum_python_26.git
```


### 2.2 Configurer l'environnement avec toutes les dépendances

> [!TIP]
> **Où taper les commandes `conda` ?**
>
> Le plus simple est d'utiliser le terminal fourni avec conda :
> * **Windows** : ouvrez **Anaconda Prompt** (ou **Miniforge Prompt**) depuis le menu Démarrer.
> * **Mac / Linux** : le terminal classique fonctionne en général directement après l'installation.
>
> Si vous préférez utiliser un autre terminal (PowerShell, cmd, terminal de VS Code, Git Bash…) et que la commande `conda` n'est pas reconnue, ouvrez **une fois** Anaconda Prompt et lancez :
>
> ```bash
> conda init --all
> ```
>
> Fermez puis rouvrez votre terminal : `conda` y fonctionne désormais.
>


* Créez un nouvel environnement appelé `geonum-velov-py313` 

```bash
conda create -n geonum-velov-py313 python=3.13
```

* Activez l'environnement

```bash
conda activate geonum-velov-py313
```

* Installer le paquet fiona avec `conda` (cela permet d'éviter un problème lors de l'installation de geopandas avec `pip`)

```bash
conda install fiona=1.10.1
```

* Install dependencies with `pip`

```bash
pip install -r requirements.txt
```


## 3 Lancer le serveur jupyter

```bash
jupyter notebook
```
