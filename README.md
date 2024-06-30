# Evaluation pratique R2.01 #2

A partir d'un __fork/clone__ de ce dépôt, il s'agit de réaliser le développement de l'application étape par étape.

La suite décrit le **contexte général** de l'application à réaliser, et indique où trouver les 
**consignes** associées à chacune des étapes.

# Contexte

On cherche à réaliser un jeu de simulation où des robots tentent de sortir d'un labyrinthe.

### Labyrinthes

Les labyrinthes sont considérés comme des grilles dont les cases sont soit `free` (on peut s'y déplacer) soit `forbidden` (ce sont des murs).

Une des cases libres est la position de départ (`spawn`) sur laquelle le robot est placé en début de simulation.
Une autre des cases libres (distincte de la précédente) est la sortie (`exit`) que le robot doit atteindre pour réussir sa mission.

#### Système de coordonnées

Les positions sont définies par des couples (`row`,`column`).
Le coin supérieur gauche du labyrinth est en `(0,0)`.

Chaque position a 4 voisines selon les directions `NORTH`, `SOUTH`, `EAST` et `WEST`. 

Les cases dont les positions sont en dehors du labyrinthe sont considérées comme `forbidden`.

#### Exemple de labyrinthe

Un exemple de labyrinthe est présenté ci-dessous:
```
XSXX
X  X
XX X
E  X
XXXX
```
- `X` désigne une case `forbidden`
- ` ` désigne une case `free`
- la position `(0,1)` correspond à `spawn`
- la position `(3,0)` correspond à `exit`

## Déroulement de la simulation

Une simulation implique un labyrinthe et un comportement de robot. 

La simulation se déroule au _tour par tour_.
Avant le premier tour, le robot est placé sur la position `spawn` et pointe dans une direction _aléatoire_.

A chaque tour, le comportement du robot est interrogé afin qu'il fournisse une **action** à réaliser. Le résultat de l'action est dans certains cas notifié en retour. 

La partie se termine :
- par une réussite si le robot a atteint la sortie 
- par un échec si le robot n'a pas atteint la sortie dans le nombre autorisé de tours (10 fois le nombre de cases de la grille)

## Actions

Les actions possibles sont `FORWARD_MOVE` (avancer d'une case), `LEFT_TURN` (tourner à gauche), `RIGHT_TURN` (tourner à droite) ou `U_TURN` (faire demi-tour).

### FORWARD_MOVE

Cette action de mouvement met à jour la position du robot comme étant la voisine de la position actuelle dans la direction vers laquelle pointe le robot. 
Si la position voisine est `forbidden`, la position du robot reste inchangée. Dans tous les cas, la direction vers laquelle pointe le robot reste
inchangée.

Le robot est notifié du résultat de cette action par un couple `(position avant, position après)`. 

### LEFT_TURN, RIGHT_TURN, U_TURN

Ces actions de rotation mettent à jour la direction vers laquelle pointe le robot.
La position du robot reste inchangée. Le robot n'est pas notifié du résultat.

# Consignes

Procéder dans l'ordre suivant :

- [0- Configuration du projet](Step-0/Step-0.md)
  - Optionnel (si cela ne pose pas de difficulté, faire la configuration à l'étape 1)
- [1- Classes simples et énumérations](Step-1/Step-1.md)
- [2- Classes plus complexes](Step-2/Step-2.md)
- [3- Exceptions](Step-3/Step-3.md)
- [4- Collections](Step-4/Step-4.md)
- [5- Abstractions](Step-5/Step-5.md)
- [6- Entrées-sorties](Step-6/Step-6.md)