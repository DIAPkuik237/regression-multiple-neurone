📘 Régression multiple & neurone artificiel

Ce mini-projet pédagogique montre comment passer d'une régression linéaire multiple à un neurone artificiel, à l'aide d'un exemple simple basé sur les performances d'étudiants.
🎯 Objectif

Prédire le score d’un étudiant (étudiant D) en fonction de deux paramètres :

    ⏳ Temps d’étude (x1 = 4)

    😴 Temps de sommeil (x2 = 5)

📊 Données

| Étudiant | Temps d'étude (x1) | Temps de sommeil (x2) | Score (y) |
| -------- | ------------------ | --------------------- | --------- |
| A        | 2                  | 6                     | 0.3       |
| B        | 3                  | 7                     | 0.5       |
| C        | 1                  | 8                     | 0.4       |
| D        | 4                  | 5                     | ?         |

🧮 Régression linéaire multiple

On cherche une relation linéaire entre les variables d'entrée et le score :

y = a1*x1 + a2*x2 + b

    x1 : temps d'étude
    x2​ : temps de sommeil
    y  : score

    a1​,a2​ : poids appris
        b : biais (interception)

📐 Méthode : moindres carrés (forme matricielle)

On utilise une résolution matricielle, identique à celle utilisée en Python :
y=X⋅θ
avec :

X = [
  [1, 2, 6],   # Étudiant A
  [1, 3, 7],   # Étudiant B
  [1, 1, 8]    # Étudiant C
]

y = [0.3, 0.5, 0.4]

    🔎 La colonne de 1 sert à intégrer le biais (b).

Formule des moindres carrés :
theta(θ) = (X^T * X)^(-1) * X^T * y

✅ Résultat (via calcul ou NumPy)

theta_best = np.linalg.inv(X.T @ X) @ X.T @ y

Ce qui donne :

    a1=0.1
    a2=0.1
    b=−0.5

🔍 Prédiction pour l'étudiant D

L’étudiant D a :

    4 heures d’étude

    5 heures de sommeil

yD=0.1⋅4+0.1⋅5−0.5=0.4

🧠 Passage au neurone artificiel

On considère maintenant ce modèle comme un neurone simple :
z=a1⋅x1+a2⋅x2+b

Puis on applique une fonction d'activation pour transformer la sortie en probabilité.

✅ Fonction d’activation sigmoïde :

σ(z) = 1 / (1 + e^(-z))

Application pour z=0.4:

σ(0.4) = 1 / (1 + e^(-0.4)) ≈ 0.5987

👉 Ce résultat peut être interprété comme une probabilité de réussite de 59.87 % pour l’étudiant D.

🧠 Et maintenant ?

Tu peux prolonger ce projet :

    🔄 En testant d'autres étudiants (changer les x1​ et x2​)

    📈 En visualisant la sortie sigmoïde pour différentes entrées

    🧪 En comparant les résultats avec ou sans activation

📌 Conclusion

✅ La régression multiple permet d’apprendre des poids optimaux pour combiner plusieurs variables.
✅ En ajoutant une fonction d’activation, on transforme la sortie en probabilité :➡️ C’est un neurone artificiel !

🧠 Cette idée est la base du machine learning moderne et des réseaux de neurones.

##💬 Et vous ?

Quelles autres variables pensez-vous qu'on pourrait inclure pour prédire la réussite d’un étudiant ?

📌 Par exemple :
- Le niveau de stress ?
- La motivation personnelle ?
- La qualité de l'alimentation ?
- L'environnement familial ?

💡 Comment ces données pourraient-elles être quantifiées et intégrées dans un modèle ?
Partagez vos idées !

📘 Par : Franck Kouekam  
🌐 DIAP ∀ — Démystifier l’Intelligence Artificielle et Python pour tout le monde

