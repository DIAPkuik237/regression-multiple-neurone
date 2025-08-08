# 📘 Régression multiple & neurone artificiel

Ce mini-projet pédagogique montre comment passer d'une **régression linéaire multiple** à un **neurone artificiel**, à l'aide d'un exemple simple basé sur les performances d'étudiants.

## 🎯 Objectif

Prédire le score d’un étudiant (étudiant D) en fonction de deux paramètres :

- ⏳ Temps d’étude (`x₁ = 4`)
- 😴 Temps de sommeil (`x₂ = 5`)

---

## 📊 Données

| Étudiant | Temps d'étude (x₁) | Temps de sommeil (x₂) | Score (y) |
| -------- | ------------------ | ---------------------- | --------- |
| A        | 2                  | 6                      | 0.3       |
| B        | 3                  | 7                      | 0.5       |
| C        | 1                  | 8                      | 0.4       |
| D        | 4                  | 5                      | ?         |

y = a₁ * x₁ + a₂ * x₂ + b

Avec :

- `x₁` : temps d'étude  
- `x₂` : temps de sommeil  
- `a₁`, `a₂` : poids associés à chaque variable  
- `b` : biais

---

## 📐 Méthode : moindres carrés (forme matricielle)

Formule utilisée pour calculer les poids optimaux :

θ = (Xᵀ * X)⁻¹ * Xᵀ * y

Calcul des coefficients par la méthode des moindres carrés :

theta_best = np.linalg.inv(X.T @ X) @ X.T @ y

Résultat obtenu :

Poids appris : [b, a1, a2] = [-0.5, 0.1, 0.1]

Calcul des coefficients par la méthode des moindres carrés :

🔍 Prédiction pour l'étudiant D

Étudiant D :

    x₁ = 4 (étude)

    x₂ = 5 (sommeil)

Calcul du score :

yD = 0.1 * 4 + 0.1 * 5 - 0.5 = 0.4










🖼️ Visualisation 3D de la régression

Voici une représentation du plan de régression :



🧩 Ce que ça nous apprend

✅ La régression multiple permet :

    d’apprendre automatiquement les poids à partir des données

    de combiner plusieurs variables pour faire une prédiction

    de transformer le modèle en neurone artificiel via une fonction d’activation

🚀 C’est l’un des fondements du machine learning moderne !
💬 Et vous ?

Quelles autres variables pourrait-on intégrer pour prédire la réussite d’un étudiant ?

📌 Par exemple :

    Le niveau de stress ?

    La motivation personnelle ?

    La qualité de l'alimentation ?

    L'environnement familial ?

💡 Et vous, quelles idées auriez-vous pour enrichir ce modèle ?
👨‍🔬 Réalisé par

Franck KOUEKAM — autodidacte en IA & vulgarisateur
📺 Chaîne YouTube : DIAP ∀ — Démystifier l’IA & Python pour tout le monde











