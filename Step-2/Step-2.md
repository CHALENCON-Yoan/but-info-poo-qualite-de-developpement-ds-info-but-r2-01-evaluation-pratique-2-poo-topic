# Step-2 : Classes plus complexes

## Travail à réaliser

A l'aide du **diagramme UML** (partiel, centré sur les classes utiles) disponible dans le répertoire `Step-2/uml`, de la **documentation Javadoc complète** disponible dans le répertoire `Step-2/docs`,
et des **précisions** données dans la section `compléments de spécifications` ci-dessous :

- :wrench: **Copier** le code des classes de `Step-1/src` vers `Step-2/src`.
- :wrench: **Configurer** `Step-2/src` comme **unique** répertoire source du projet.
- :pencil: **Ecrire** le code de la classe `Labyrinth`.
- :pencil: **Modifier** le code de l'application `Main`.
- :white_check_mark: **Exécuter l'application `Main` et vérifier que la sortie console est conforme à ce qui est attendu**.
- :label: **Effectuer un commit** de l'ensemble des modifications, en indiquant `Step-2` comme message et en utilisant la zone détail si besoin.
- :rocket: **Pousser immédiatement** le commit sur Gitlab.
- :eyes: **Vérifier** que le commit est bien disponible sur Gitlab.

:warning: Gestion des paquetages :

- la classe `Main` appartient au **paquetage par défaut**,
- toutes les autres classes appartiennent au paquetage
  `fr.iutvalence.info.but.r2_01.labyrinthGame.core`.

## Compléments de spécifications

## `Labyrinth`

Cette classe représente un **labyrinthe**.

- les paramètres passés au **constructeur** sont supposés corrects (représentent un labyrinthe valide), aucun contrôle n'est effectué.
- si la position passée en paramètre de la méthode `getCellStateAt` est en dehors des limites du labyrinthe, la méthode retourne `CellState.FORBIDDEN`.
- la position retournée par l'appel de la méthode `getPositionAfterForwardMove` est :
  - la position d'arrivée est libre, 
  - la position actuelle sinon.
- la méthode `toString` est redéfinie de sorte qu'elle retourne une représentation ASCII-art du labyrinthe, où chaque case est représentée par le caractère représentant son état (cf. section `Exemple de labyrinthe` dans le fichier `/README.md`) 

## `Main`

Cette application construit le labyrinthe de l'exemple donné dans la section `Exemple de labyrinthe` du fichier `/README.md`, et affiche sa
représentation sur la sortie standard.

- le labyrinthe a une largeur de `4` et une hauteur de `5`,
- la position de _spawn_ est `(0, 1)`,
- la position de _sortie_ est `(3, 0)`,
- les murs se situent aux positions `(0, 0)`, `(0, 2)`, `(0, 3)`, `(1, 0)`, `(1, 3)`,
`(2, 0)`, `(2, 1)`, `(2, 3)`, `(3, 3)`, `(4, 0)`, `(4, 1)`, `(4, 2)` et `(4, 3)`.

La représentation texte de ce labyrinthe est donc :

```
XSXX
X  X
XX X
E  X
XXXX
```
