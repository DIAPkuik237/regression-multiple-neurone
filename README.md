# 📘 Régression multiple & neurone artificiel

Ce mini-projet pédagogique montre comment passer d'une **régression linéaire multiple** à un **neurone artificiel**, à l'aide d'un exemple simple basé sur les performances d'étudiants.

---

## 🎯 Objectif

Prédire le score d’un étudiant (étudiant D) en fonction de deux paramètres :

- ⏳ Temps d’étude (`x1 = 4`)
- 😴 Temps de sommeil (`x2 = 5`)

---

## 📊 Données

| Étudiant | Temps d'étude (x1) | Temps de sommeil (x2) | Score (y) |
|----------|--------------------|------------------------|-----------|
| A        | 2                  | 6                      | 0.3       |
| B        | 3                  | 7                      | 0.5       |
| C        | 1                  | 8                      | 0.4       |
| D        | 4                  | 5                      | ?         |

> 🔎 On ajoute une colonne de `1` dans la matrice des données pour intégrer le **biais** `b`.

---

## 🧮 Régression linéaire multiple

On cherche une relation du type :
y = a1 * x1 + a2 * x2 + b

Avec :

- `x1` : temps d'étude  
- `x2` : temps de sommeil  
- `a1`, `a2` : poids appris pour chaque variable  
- `b` : biais (interception)

---

## 📐 Méthode des moindres carrés

### Forme matricielle

Formule utilisée :
theta = (Xᵗ * X)^(-1) * Xᵗ * y


























