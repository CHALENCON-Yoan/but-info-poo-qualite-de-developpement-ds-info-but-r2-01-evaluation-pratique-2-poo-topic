# Step-3 : Exceptions

## Travail à réaliser

A l'aide du **diagramme UML** (partiel, centré sur les classes utiles) disponible dans le répertoire `Step-3/uml`, de la **documentation Javadoc complète** disponible dans le répertoire `Step-3/docs`, 
et des **précisions** données dans la section `compléments de spécifications` ci-dessous :

- :wrench: **Copier** le code des classes de `Step-2/src` vers `Step-3/src`.
- :wrench: **Configurer** `Step-3/src` comme **unique** répertoire source du projet.
- :pencil: **Modifier** le code de la classe `Labyrinth` (excepté le constructeur).
- :pencil: **Ecrire** le code de la classe `InvalidLabyrinthException`
- :pencil: **Modifier** le code du constructeur de la classe `Labyrinth`.
- :pencil: **Modifier** le code de l'application `Main`.
- :white_check_mark: **Exécuter l'application `Main` et vérifier que la sortie console est conforme à ce qui est attendu**.
- :label: **Effectuer un commit** de l'ensemble des modifications, en indiquant `Step-3` comme message et en utilisant la zone détail si besoin.
- :rocket: **Pousser immédiatement** le commit sur Gitlab.
- :eyes: **Vérifier** que le commit est bien disponible sur Gitlab.


:warning: Gestion des paquetages :

- la classe `Main` appartient au **paquetage par défaut**,
- la classe `InvalidLabyrinthException` appartient au paquetage `fr.iutvalence.info.but.r2_01.labyrinthGame.exceptions`
- toutes les autres classes appartiennent au paquetage
  `fr.iutvalence.info.but.r2_01.labyrinthGame.core`.


## Compléments de spécifications

## `InvalidLabyrinthException`

Cette classe est une **exception contrôlée** représentant une erreur lors de la création d'un labyrinthe, à laquelle peut-être associé un message texte précisant
pourquoi la construction du labyrinthe a échoué :
- dimensions invalides
- position de spawn ou de sortie en dehors des limites
- positions de spawn et de sortie confondues
- positions de spawn ou de sortie confondues avec un mur

## `Labyrinth`

Cette classe est modifiée comme suit :

- Une nouvelle méthode, `isForbiddenCellAt`, permet de déterminer si un position correspond à une cellule interdite.
- La méthode `getCellStateAt` est simplifiée en s'appuyant sur la méthode précédente.
- Le **constructeur soulève l'exception** `InvalidLabyrinthException` (accompagnée du message associé) en cas d'erreur (cf. `InvalidLabyrinthException` ci-dessus).

N.B. Les positions de murs en dehors des limites du labyrinthe, de même que les positions de murs en doublon ne sont pas considérés comme des cas d'erreur.

## `Main`

En plus de la création de labyrinthe valide précédente, **le scénario de validation doit manifester chacun des cas d'erreur possibles suivants** (et afficher le message d'erreur associé):
- largeur invalide
- position de spawn en dehors des limites
- position de sortie sur un mur
- positions de spawn et de sortie confondues
