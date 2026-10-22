# Mathis Frinzi

Projets de recherche personnels en IA et mathématiques appliquées :

---

## Entre un réservoir et un RNN · [partially-frozen-rnn](https://github.com/mathisfrinzi/partially-frozen-rnn)

*Une récurrence aléatoire figée dont on n'apprend qu'une pièce choisie (atténuation, rotation, cisaillement…) : que vaut l'espace entre un Echo State Network et un RNN complet ?*


- **La facilité d'apprentissage bat la géométrie de la cible**, même quand la solution exacte est dans la famille apprenante : ce sont des bandes de quelques centaines de coefficients qui gagnent.
- Rester entre les deux bat le RNN qui apprend tout sur les séries synthétiques (100 à 2 000 neurones) ; mieux que le GRU sur un système physique réel (Silverbox) avec 127× moins de paramètres. 10 parties, bilingue, tests CI.

---

## Optimiser avec des couleurs quaternioniques · [quaternionic-colorimetry-optimization](https://github.com/mathisfrinzi/quaternionic-colorimetry-optimization)

*Trouver les zéros de f : ℍ → ℍ en ne voyant qu'une couleur quantifiée de f — luminosité, teinte, axe — jamais sa valeur.*



- **La couleur suffit** : zéros en dimension 4 et 4n, points fixes de RNN, entraînement d'une couche quaternionique, sans jamais lire `f`.
- Deux apports : un **certificat topologique** de zéro lu dans les seules couleurs (13/13 points fixes certifiés, résiste au bruit) et un **Broyden quaternionique**, la méthode la moins chère de l'étude sur les problèmes structurés.
- La couleur ne bat pas la valeur : face à une méthode classique qui connaît la même structure, toutes les sondes perdent ; le certificat ne passe pas à l'échelle au-delà de ℍ.

---

## Optimiser avec des couleurs · [complex-colorimetry-optimization](https://github.com/mathisfrinzi/complex-colorimetry-optimization)

*L'étude d'origine, sur les complexes : optimiser avec la seule couleur d'un domain coloring, quantifiée sur 8 à 12 bits par canal.*

- Zéros de fonctions holomorphes : 99-100 % de succès en 24-35 évaluations, moins que Newton ou Nelder-Mead ; en boîte noire (n = 16), 100 % là où Nelder-Mead, Powell et CMA-ES échouent.
- La teinte porte une deuxième information par lecture : la courbure (−30 à −52 % d'évaluations) ou la perte de validation (arrêt précoce lu dans la couleur).
- À mesures dégradées égales, pas d'avantage : Broyden classique reste moins cher ; fragile au bruit face à CMA-ES.

---

## ⚙️ Réseaux à engrenages · [gear-networks](https://github.com/mathisfrinzi/gear-networks)

*Chaque neurone apprend sa fonction d'activation avec un seul paramètre : un angle sur un cycle relu → silu → tanh → identité. Conclu sur un résultat négatif assumé.*
