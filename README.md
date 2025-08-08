# 🧠 Régression multiple & neurone artificiel

Ce mini-projet pédagogique montre comment passer d'une **régression linéaire multiple** à un **neurone artificiel**, à l'aide d'un exemple simple basé sur les performances d'étudiants.

## 🎯 Objectif

Prédire le score d’un étudiant (étudiant D) en fonction de deux paramètres :

- ⏳ Temps d’étude (`x₁ = 4`)
- 😴 Temps de sommeil (`x₂ = 5`)

## 🎯 Données utilisées

| Étudiant | Biais (1) | Étude (x₁) | Sommeil (x₂) | Score (y) |
|----------|-----------|------------|--------------|-----------|
| A        | 1         | 2          | 6            | 0.3       |
| B        | 1         | 3          | 7            | 0.5       |
| C        | 1         | 1          | 8            | 0.4       |

> 🔎 La colonne `1` représente le **biais** (valeur constante permettant au modèle de s’ajuster même si toutes les entrées sont nulles).

## 🧮 Régression linéaire multiple

On cherche une relation linéaire entre les variables d'entrée et le score :

\[
y = a₁ \cdot x₁ + a₂ \cdot x₂ + b
\]

Avec :

- `x₁` = temps d’étude  

- `x₂` = temps de sommeil  

- `a₁`, `a₂` = poids associés à chaque variable  

- `b` = biais (valeur fixe à apprendre)

## 📐 Formule des moindres carrés

Pour calculer les poids optimaux (`a₁`, `a₂`, `b`), on utilise une résolution matricielle :

\[
\theta = (X^T \cdot X)^{-1} \cdot X^T \cdot y
\]

En Python (avec NumPy) :

```python

theta_best = np.linalg.inv(X.T @ X) @ X.T @ y

==> Poids appris par le modèle :

Résultat du calcul :

Poids appris (biais, étude, sommeil) : [-0.5  0.1  0.1]

Soit :
    a1 = 0.1
    a2 = 0.1
    b  = -0.5

Le modèle apprend ces poids automatiquement à partir des données,
afin de minimiser l’erreur de prédiction (par la méthode des moindres carrés).

=> Pas besoin de les choisir à la main !

------------------------------------------------------------

Prédiction pour l’étudiant D

L’étudiant D a :
    x1 = 4 heures d’étude
    x2 = 5 heures de sommeil

Calcul du score :
    yD = 0.1 * 4 + 0.1 * 5 - 0.5 = 0.4

Score prédit (avant activation) : 0.4

------------------------------------------------------------

Visualisation 3D de la régression

Voici le plan de régression 3D qui montre l’influence conjointe du sommeil et de l’étude sur le score :

Image (Heatmap) : https://github.com/DIAPkuik237/regression-multiple-neurone/blob/master/heatmap(2).png

------------------------------------------------------------

Passage au neurone artificiel

On reprend la formule obtenue :
    z = a1 * x1 + a2 * x2 + b

Puis on applique une fonction d’activation. Ici : la fonction sigmoïde

Définition :
    sigma(z) = 1 / (1 + e^(-z))

Application pour z = 0.4 :
    sigma(0.4) ≈ 0.5987

Interprétation :
    Probabilité de réussite : environ 59.87 %

------------------------------------------------------------

Ce que ça nous apprend :

    - La régression multiple combine plusieurs variables via une somme pondérée.
    - Le modèle apprend automatiquement les meilleurs poids à partir des données.
    - En ajoutant une fonction d’activation (sigmoïde), on crée un neurone simple.
    - Cette idée est la base du machine learning et des réseaux de neurones.

------------------------------------------------------------

Ressources :

    - Article complet sur Medium
    - Code source sur GitHub : https://github.com/DIAPkuik237/regression-multiple-neurone
    - Exécuter sur Google Colab
    - Lire d'abord : Un premier pas vers l’IA avec la régression linéaire simple

------------------------------------------------------------

Projet réalisé par :

Franck KOUEKAM – autodidacte en IA & vulgarisateur

Chaîne YouTube : DIAP ∀ — Démystifier l’Intelligence Artificielle & Python pour tout le monde


