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

Formule utilisée :
theta = (Xᵗ * X)^(-1) * Xᵗ * y


---

## 🔢 Données sous forme matricielle
### Matrice X (avec biais)

| Biais | Étude (x₁) | Sommeil (x₂) |
| ----- | ---------- | ------------ |
| 1     | 2          | 6            |
| 1     | 3          | 7            |
| 1     | 1          | 8            |

> 🔎 On ajoute une colonne de `1` dans la matrice des données pour intégrer le **biais** `b`.

### Vecteur y
| Étudiant | Score (y) |
| -------- | --------- |
| A        | 0.3       |
| B        | 0.5       |
| C        | 0.4       |



---

## 💻 Implémentation en Python
import numpy as np

X = np.array([
    [1, 2, 6],  # Étudiant A
    [1, 3, 7],  # Étudiant B
    [1, 1, 8]   # Étudiant C
])

y = np.array([0.3, 0.5, 0.4])

theta_best = np.linalg.inv(X.T @ X) @ X.T @ y
print(theta_best)



#### ✅ Résultat obtenu
Poids appris par le modèle (dans l’ordre : biais, x1, x2) :

[-0.5  0.1  0.1]

Soit :

a1 = 0.1

a2 = 0.1

b = -0.5

## 🔍 Prédiction pour l’étudiant D

L’étudiant D a :

x1 = 4

x2 = 5

Calcul :

yD = 0.1 * 4 + 0.1 * 5 - 0.5 = 0.4

## 🖼️ Visualisation 3D de la régression

Voici le plan de régression qui modélise l'influence combinée du sommeil et du temps d'étude :
![Heatmap](https://github.com/DIAPkuik237/regression-multiple-neurone/blob/master/heatmap(2).png)


## 🧠 Passage au neurone artificiel

Formule de sortie du neurone :

z = a1 * x1 + a2 * x2 + b

Puis, on applique une fonction d’activation.

Fonction sigmoïde :

σ(z) = 1 / (1 + e^(-z))

Application pour z = 0.4 :

σ(0.4) ≈ 0.5987

#### ✅ Interprétation :

Probabilité de réussite de l’étudiant D : ~59.87 %


## 📌 Conclusion

✅ La régression multiple apprend automatiquement les poids optimaux pour combiner plusieurs variables.

✅ En ajoutant une fonction d’activation, on transforme la sortie en probabilité → on obtient un neurone artificiel simple.

    🧠 C’est le principe fondamental derrière les réseaux de neurones et le machine learning moderne.

## 💬 Et vous ?

Quelles autres variables pourraient influencer la réussite d’un étudiant ?

Le niveau de stress ?

La motivation personnelle ?

La qualité de l’alimentation ?

L’environnement familial ?

💡 Et si vous intégriez ces paramètres dans un futur modèle ?

### 👨‍🔬 Projet réalisé par

Franck KOUEKAM — Autodidacte en IA & vulgarisateur
Chaîne YouTube : DIAP ∀ — Démystifier l’IA & Python pour tout le monde












