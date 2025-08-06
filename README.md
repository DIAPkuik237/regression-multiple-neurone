# Régression multiple & neurone artificiel
Ce mini-projet pédagogique montre comment passer d'une régression linéaire multiple à un neurone artificiel, à l'aide d'un exemple simple basé sur les performances d'étudiants.

## 🎯 Objectif
Prédire le score d’un étudiant (`étudiant D`) en fonction de **deux paramètres** :
- Temps d’étude
- Temps de sommeil

## 📊 Jeu de données

| Étudiant | Temps d'étude (h) | Temps de sommeil (h) | Score |
|----------|-------------------|-----------------------|-------|
| A        | 2                 | 6                     | 0.3   |
| B        | 3                 | 7                     | 0.5   |
| C        | 1                 | 8                     | 0.4   |
| D        | 4                 | 5                     | ?     |

---

## 🧮 Calculs manuels

On suppose une relation du type :

Score = a1 · (temps d'étude) + a2 · (sommeil) + b

Poids obtenus via régression matricielle :

a1 (étude) = 0.1
a2 (sommeil) = 0.1
b (biais) = -0.5

### 🔍 Score prédit pour l’étudiant D :
Score = 0.1×4 + 0.1×5 - 0.5 = 0.4

## 🧠 Transformation en neurone artificiel

On applique une **fonction d'activation sigmoïde** :

sigmoid(z) = 1 / (1 + exp(-z))
z = 0.4
probabilité = 1 / (1 + np.exp(-0.4)) ≈ 0.5987
