# Régression multiple et neurone artificiel

Ce mini-projet pédagogique montre comment passer d'une régression linéaire multiple à un neurone artificiel, à l'aide d'un exemple simple basé sur les performances d'étudiants.

## Objectif

Prédire le score d’un étudiant (étudiant D) en fonction de deux paramètres :

- Temps d’étude (x₁ = 4)
- Temps de sommeil (x₂ = 5)

## Données

| Étudiant | Biais (1) | Temps d'étude (x₁) | Sommeil (x₂) | Score (y) |
|----------|-----------|--------------------|--------------|-----------|
| A        | 1         | 2                  | 6            | 0.3       |
| B        | 1         | 3                  | 7            | 0.5       |
| C        | 1         | 1                  | 8            | 0.4       |

La colonne de biais (1) permet d'ajouter une constante dans le modèle (le biais b).

## Régression linéaire multiple

On cherche une relation linéaire entre les variables d’entrée et le score :

y = a₁ * x₁ + a₂ * x₂ + b
- x₁ : temps d’étude
- x₂ : temps de sommeil
- a₁, a₂ : poids (coefficients)
- b : biais (interception)

## Formule des moindres carrés

Pour calculer les poids optimaux, on utilise la méthode des moindres carrés sous forme matricielle :
θ = (Xᵀ * X)⁻¹ * Xᵀ * y
## Implémentation en Python

```python
import numpy as np

X = np.array([
    [1, 2, 6],  # Étudiant A
    [1, 3, 7],  # Étudiant B
    [1, 1, 8]   # Étudiant C
])

y = np.array([0.3, 0.5, 0.4])

theta_best = np.linalg.inv(X.T @ X) @ X.T @ y
print(theta_best)

## Objectif









