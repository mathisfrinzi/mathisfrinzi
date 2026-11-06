# Mathis Frinzi

Projets de recherche personnels en IA et mathématiques appliquées :

## Entre un réservoir et un RNN · [partially-frozen-rnn](https://github.com/mathisfrinzi/partially-frozen-rnn)

*Une récurrence aléatoire figée dont on n'apprend qu'une pièce choisie (atténuation, rotation, cisaillement…) : que vaut l'espace entre un Echo State Network et un RNN complet ?*


- **La facilité d'apprentissage bat la géométrie de la cible**, même quand la solution exacte est dans la famille apprenante : ce sont des bandes de quelques centaines de coefficients qui gagnent.
- Rester entre les deux bat le RNN qui apprend tout sur les séries synthétiques (100 à 2 000 neurones) ; mieux que le GRU sur un système physique réel (Silverbox) avec 127× moins de paramètres

<img width="1494" height="699" alt="s7_une_descente" src="https://github.com/mathisfrinzi/partially-frozen-rnn/blob/main/results/figures/schema_budget.png" />

---

## Un réservoir qui lit son passé · [delay-tensor-esn](https://github.com/mathisfrinzi/delay-tensor-esn)

*Un Echo State Network dont l'état lit directement plusieurs instants passés, chacun par sa propre matrice : quels retards choisir, et que valent-ils à budget égal ?*

- **Une règle exacte** : l'état ne peut contenir l'entrée d'il y a L pas que si L est une somme de retards de l'ensemble S. Ça permet de **calculer S à partir des données**, sans réservoir entraîné ni recherche.
- Sur 13 séries réelles neuves, avec la prévision écrite avant tout calcul : le S calculé bat l'ESN à fuite 10 fois, et la prévision est tenue 10 fois sur 13.
- Mais il ne bat nettement les délais de Iacob et Dambre que là où l'âge utile est long et isolé, et un ridge linéaire sur 200 âges, sans réservoir, fait souvent aussi bien.

<img width="1494" height="699" alt="s7_une_descente" src="https://github.com/mathisfrinzi/delay-tensor-esn/blob/main/results/schemas/schema_modele.svg" />

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

<img width="1494" height="699" alt="s7_une_descente" src="https://github.com/user-attachments/assets/9bfed6f6-8111-4233-a779-3d4fb23ad8fb" />

---

## Optimiser sans lire la perte · [colormezo](https://github.com/mathisfrinzi/colormezo)

*MeZO (fine-tuning de LLM par passes avant seulement) quand la perte passe par un capteur à gain inconnu qui dérive : la différence des logarithmes fait disparaître le gain.*

- Sur OPT-125M / SST-2, après 2 000 lectures, la dérive coûte 9,4 points de précision à MeZO et 2,8 à ColorMeZO. MeZO diverge sous dérive, ColorMeZO reste fini à tous les η testés.
- La robustesse n'en fait pas l'optimum : ColorMeZO dérivant finit à 0,762 contre 0,833 pour l'oracle, et les méthodes à classement restent meilleures sur le jouet.

<img width="1494" height="699" alt="s7_une_descente" src="https://github.com/mathisfrinzi/colormezo/blob/main/figures/schema_principe.svg" />

---

## Réseaux à engrenages · [gear-networks](https://github.com/mathisfrinzi/gear-networks)

*Chaque neurone apprend sa fonction d'activation avec un seul paramètre : un angle sur un cycle relu → silu → tanh → identité. Conclu sur un résultat négatif.*

---

## Générateur jacobien · [integrable-weights](https://github.com/mathisfrinzi/integrable-weights)

*Entraîner des matrices de poids comme jacobiennes d'une fonction : la contrainte d'intégrabilité vaut-elle quelque chose ?*

---
