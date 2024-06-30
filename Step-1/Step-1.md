# Step-1 : Classes simples, énumérations

## Travail à réaliser

A l'aide du **diagramme UML** disponible dans le répertoire `Step-1/uml`, de la **documentation Javadoc complète** disponible dans le répertoire `Step-1/docs`
et des **précisions** données dans la section `compléments de spécifications` ci-dessous :

- :wrench: **Copier** le code des classes de `Step-0/src` vers `Step-1/src`.
- :wrench: **Configurer** `Step-1/src` comme **unique** répertoire source du projet.
- :pencil: **Ecrire**  le code de l'énumération `CellState`.
- :pencil: **Ecrire**  le code de l'énumération `Action`.
- :pencil: **Ecrire**  le code de l'énumération `Direction`.
- :pencil: **Ecrire**  le code de la classe `Position`.
- :pencil: **Modifier** le code de l'application `Main`.
- :white_check_mark: **Exécuter l'application `Main` et vérifier que la sortie console est conforme à ce qui est attendu**.
- :label: **Effectuer un commit** de l'ensemble des modifications, en indiquant `Step-1` comme message et en utilisant la zone détail si besoin.
- :rocket: **Pousser immédiatement** le commit sur Gitlab.
- :eyes: **Vérifier** que le commit est bien disponible sur Gitlab.


:warning: Gestion des paquetages :

- la classe `Main` appartient au **paquetage par défaut**,
- toutes les autres classes appartiennent au paquetage
`fr.iutvalence.info.but.r2_01.labyrinthGame.core`.

## Compléments de spécifications

### `CellState`

Cette énumération décrit tous les états possibles d'une case du labyrinthe.

N.B. cette énumération redéfinit `toString` (cf. Javadoc).

### `Action`

Cette énumération décrit toutes les actions possibles pour le robot, et fournit des méthodes permettant d'obtenir
des actions tirées au sort (parmi toutes les actions ou seulement les actions représentant des rotations).

N.B. cette énumération redéfinit `toString` (cf. Javadoc).

### `Direction`

Cette énumération décrit toutes les directions possibles vers lesquelles le robot peut se diriger,
et fournit des méthodes permettant d'obtenir une direction tirée au sort ainsi que la direction résultante après une action de rotation.


A chaque direction sont associés les décalages en ligne/colonne qu'implique un mouvement.

N.B. cette énumération redéfinit `toString` (cf. Javadoc).

### `Position`

Cette classe représente une position dans le labyrinthe, c'est une structure de données immuable.

N.B. cette classe redéfinit `equals`, `hashCode` et `toString` (cf. Javadoc).

### `Main`

Cette application met en oeuvre le scénario suivant :

- affichage sur la console de la valeur de la constante énumérée `CellState.EXIT`
- création d'une nouvelle instance de la classe `Position` représentant la position `(0, 0)`
- affichage sur la console de la représentation texte de la position précédente
- obtention au hasard d'une des constantes de l'énumération `Direction`
- affichage sur la console de la représentation texte de la direction précédente
- obtention au hasard d'une des constantes de l'énumération `Action` correspondant à une action de rotation
- affichage sur la console de la représentation texte de l'action précédente
- affichage sur la console de la représentation texte de la position voisine de la position précédente dans la direction résultante de l'action de rotation
appliquée à la direction précédente.
