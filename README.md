
# Projet de Traitement d'Image

Ce projet rassemble plusieurs travaux pratiques réalisés dans le cadre de mon apprentissage du traitement d'image. Les tâches principales incluent l'augmentation de contraste, la réduction de bruit, la détection de contours, la transformée de Fourier, et le traitement d'images en couleur. Ce projet explore l'impact des différentes techniques sur la qualité visuelle des images et fournit des résultats analysés pour chaque méthode.


## Objectifs du Projet

L'objectif principal de ce projet est de :
1. **Améliorer la qualité visuelle** des images en ajustant le contraste et en réduisant le bruit.
2. **Analyser les effets fréquentiels** grâce à la transformée de Fourier pour mieux comprendre la structure des images.
3. **Explorer les corrections de contraste dans différents espaces colorimétriques** pour des images en couleur.

Ce projet met en pratique diverses techniques de traitement d'image en utilisant la bibliothèque OpenCV et explore l'influence des paramètres sur les résultats obtenus.

## Prérequis et Installation

### Environnement
- **Google Colab** ou un environnement Python 3 avec Jupyter Notebook.
- **Python 3** (idéalement version 3.10 ou plus récente).

### Bibliothèques nécessaires
Installez les bibliothèques nécessaires en exécutant la commande suivante dans votre terminal ou dans une cellule de votre notebook :

```bash
pip install opencv-python matplotlib numpy
```

## Instructions d'Exécution

1. Clonez ou téléchargez le dépôt.
2. Ouvrez le notebook associé  dans Google Colab ou Jupyter Notebook.
3. Exécutez les cellules pas à pas, en ajustant les paramètres si vous souhaitez tester différents réglages.
4. Les images de sortie s'afficheront directement dans le notebook pour visualiser les effets.

## Travaux Pratiques

### 1. Augmentation de Contraste

**Objectif** : Explorer plusieurs méthodes de correction de contraste, dont :
- L’égalisation d'histogramme avec `cv2.equalizeHist()`.
- Une **transformation linéaire** implémentée manuellement.
- Une **correction Gamma** ajustable.

**Résultats** :
- Les images traitées sont accompagnées de leurs histogrammes pour observer l'impact de chaque méthode.
- Les commentaires détaillent l'effet des différents paramètres (par exemple, l'influence de `gamma` pour la correction Gamma) sur le contraste des images.

### 2. Filtres : Réduction de Bruit et Détection de Contours

#### Réduction de Bruit
**Objectif** : Réduire le bruit dans les images en appliquant des filtres, tels que :
- **Moyenneur**, **gaussien**, **médian**, **min/max**.

**Résultats** :
- Le filtre médian s'est avéré le plus efficace pour les bruits de type "sel et poivre".
- Une analyse des paramètres montre que la taille du noyau influence grandement la qualité de l'image obtenue.

#### Détection de Contours
**Objectif** : Détecter les contours en utilisant deux méthodes :
- **Seuillage sur la norme du gradient**
- **Filtre de Canny**

**Résultats** :
- Le filtre de Canny offre une robustesse supérieure, notamment après une réduction de bruit.
- Les variations de seuils permettent d'ajuster la sensibilité de la détection des contours.

### 3. Transformée de Fourier

**Objectif** : Utiliser la transformée de Fourier pour analyser la fréquence des images, avec :
- Un passage dans le domaine fréquentiel pour visualiser le spectre.
- L'application de filtres passe-bas et passe-haut pour isoler certaines fréquences.

**Résultats** :
- Les hautes fréquences mettent en évidence les contours, tandis que les basses fréquences lissent l'image.
- Les résultats montrent comment le domaine fréquentiel peut être utilisé pour manipuler les détails d'une image.

### 4. Correction du Contraste pour Images Couleurs

**Objectif** : Expérimenter la correction de contraste pour les images en couleur dans différents espaces de couleur (RGB, HSV, Lab).

#### Conversion entre Espaces de Couleurs
- **RGB** : Correction appliquée sur chaque canal séparément.
- **HSV** : Correction uniquement sur la composante de luminance (V).
- **Lab** : Correction sur la composante de luminance (L).

**Résultats** :
- Les corrections en **HSV** et **Lab** montrent un contraste plus naturel en préservant les teintes.
- La correction dans **RGB** amplifie le contraste global mais peut altérer la perception des couleurs.

## Analyses et Limitations

Chaque technique a ses propres avantages et limitations :
- **Réduction de bruit** : Le filtre médian est idéal pour les bruits de type "sel et poivre", mais il peut réduire les détails dans les images fines.
- **Détection de contours** : La méthode de Canny est efficace mais nécessite un prétraitement pour les images très bruitées.
- **Correction de contraste** : La correction de contraste en **HSV** et **Lab** préserve mieux les couleurs par rapport à la correction en **RGB**, mais demande plus de ressources de calcul.

## Références

- **OpenCV Documentation** : [https://docs.opencv.org](https://docs.opencv.org)

---
