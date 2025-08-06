# Régression multiple & neurone artificiel
Ce mini-projet pédagogique montre comment passer d'une régression linéaire multiple à un neurone artificiel, à l'aide d'un exemple simple basé sur les performances d'étudiants.

🎯 Objectif

Prédire le score d’un étudiant (étudiant D) en fonction de deux paramètres :
⏳ Temps d’étude

😴 Temps de sommeil

| Étudiant | Temps d'étude (x1) | Temps de sommeil (x2) | Score (y) |
| -------- | ------------------ | --------------------- | --------- |
| A        | 2                  | 6                     | 0.3       |
| B        | 3                  | 7                     | 0.5       |
| C        | 1                  | 8                     | 0.4       |
| D        | 4                  | 5                     | ?         |

🧮 Régression linéaire multiple
On cherche une relation linéaire entre les variables d'entrée et le score :
y= a1⋅x1 + a2⋅x2 + b

x1 : temps d'étude
x2 : temps de sommeil
y : score
a1, a2 : poids appris
b : biais (interception)
##📐 Méthode : résolution par les moindres carrés
On utilise une formule matricielle pour résoudre ce système de manière rapide et fiable (utilisée aussi en Python) :
θ=(X^TX) −1X^Ty

➕ Construction des matrices
Matrice X (avec biais ajouté sous forme de 1) :

A COMPLETER
​
​
  
​

  
​
 

✅ Résultat du calcul matriciel (ou avec NumPy) :
theta_best = np.linalg.inv(X.T @ X) @ X.T @ y
Donne :
a1 = 0.1
a2 = 0.1
b = -0.5
##🔍 Prédiction pour l'étudiant D
Étudiant D a :

4 heures d’étude
5 heures de sommeil

𝑦𝐷=0.1⋅ 4+0.1⋅5−0.5=0.4y D
=0.1⋅4+0.1⋅5−0.5=0.4

#🧠 Passage au neurone artificiel
On considère maintenant que ce modèle est un neurone simple :
z=a1⋅x1 + a2⋅x2 + b
​Puis on applique une fonction d'activation pour obtenir une probabilité :
✅ Fonction sigmoïde :
σ(z)=1/1+e^−z
Application pour z = 0.4 :
𝜎(0.4)≈0.5987

👉 Ce résultat peut être interprété comme une probabilité de réussite de 59.87% pour l’étudiant D.
--------------------------------------------------------------------------------------------------------------------
📌 Conclusion
✅ La régression multiple apprend les poids optimaux pour combiner plusieurs variables.
✅ En ajoutant une fonction d’activation, on transforme la sortie en probabilité → c’est un neurone artificiel !
🧠 C’est la base du machine learning et des réseaux de neurones.

--------------------------------------------------------------------------------------------------------------------

##💬 Et vous ?
Quelles autres variables pourraient influencer la réussite d’un étudiant ? 💭
Stress, alimentation, motivation ? Faites vos suggestions !
