📘 Régression multiple & neurone artificiel

Ce mini-projet pédagogique montre comment passer d'une régression linéaire multiple à un neurone artificiel, à l'aide d'un exemple simple basé sur les performances d’étudiants.
🎯 Objectif

Prédire le score d’un étudiant (étudiant D) en fonction de deux paramètres :

    ⏳ Temps d’étude x₁ = 4

    😴 Temps de sommeil x₂ = 5

📊 Données utilisées
Étudiant	Biais (1)	Étude (x₁)	Sommeil (x₂)	Score (y)
A	1	2	6	0.3
B	1	3	7	0.5
C	1	1	8	0.4

    🔎 La colonne 1 représente le biais (interception b).

📐 Formule des moindres carrés

Formule matricielle :

θ = (Xᵀ · X)⁻¹ · Xᵀ · y

où :

    X est la matrice des données (avec biais)

    y est le vecteur des scores

    θ contient les paramètres [biais, a₁, a₂]

💻 Implémentation en Python

import numpy as np

X = np.array([
    [1, 2, 6],  # Étudiant A
    [1, 3, 7],  # Étudiant B
    [1, 1, 8]   # Étudiant C
])

y = np.array([0.3, 0.5, 0.4])

theta_best = np.linalg.inv(X.T @ X) @ X.T @ y
print(theta_best)

✅ Résultat obtenu

[-0.5  0.1  0.1]

Ce qui signifie :

    b = -0.5

    a₁ = 0.1

    a₂ = 0.1

📈 Prédiction pour l'étudiant D

Étudiant D :

    x₁ = 4 heures d’étude

    x₂ = 5 heures de sommeil

Calcul du score :

yD = a₁·x₁ + a₂·x₂ + b
yD = 0.1*4 + 0.1*5 - 0.5 = 0.4

🧠 Passage au neurone artificiel

Formule du neurone :

z = a₁·x₁ + a₂·x₂ + b

Ajout d’une fonction d’activation : la sigmoïde

σ(z) = 1 / (1 + e^(-z))

Application :

σ(0.4) ≈ 0.5987

    🔍 Interprétation : probabilité de réussite ≈ 59.87 % pour l'étudiant D

🖼️ Visualisation 3D de la régression

📌 Conclusion

    ✅ La régression multiple permet de combiner plusieurs variables

    ✅ En ajoutant une fonction d’activation, on obtient un neurone simple

    🚀 C’est le point de départ du machine learning moderne

💬 Et vous ?

Quelles autres variables pourrait-on intégrer ?

📌 Exemples :

    Motivation ?

    Niveau de stress ?

    Environnement familial ?

    Qualité de l’alimentation ?

💡 Comment les quantifieriez-vous ?
👨‍🔬 Réalisé par

Franck KOUEKAM – autodidacte en IA
🎓 Fondateur de la chaîne DIAP ∀ — Démystifier l’IA et Python pour tous
