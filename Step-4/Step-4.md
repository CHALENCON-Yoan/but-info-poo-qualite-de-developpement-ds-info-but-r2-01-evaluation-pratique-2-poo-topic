# Step-4 : Collections

## Travail à réaliser

A l'aide du **diagramme UML** (partiel, centré sur les classes utiles) disponible dans le répertoire `Step-4/uml`, de la **documentation Javadoc complète** disponible dans le répertoire `Step-4/docs`
et des **précisions** données dans la section `compléments de spécifications` ci-dessous :

- :wrench: **Copier** le code des classes de `Step-3/src` vers `Step-4/src`.
- :wrench: **Configurer** `Step-4/src` comme **unique** répertoire source du projet.
- :pencil: **Modifier** le code de la classe `Labyrinth`.
- :pencil: **Modifier** le code de l'application `Main`.
- :white_check_mark: **Exécuter l'application `Main` et vérifier que la sortie console est conforme à ce qui est attendu**.
- :label: **Effectuer un commit** de l'ensemble des modifications, en indiquant `Step-4` comme message et en utilisant la zone détail si besoin.
- :rocket: **Pousser immédiatement** le commit sur Gitlab.
- :eyes: **Vérifier** que le commit est bien disponible sur Gitlab.


:warning: Gestion des paquetages :

- la classe `Main` appartient au **paquetage par défaut**,
- la classe `InvalidLabyrinthException` appartient au paquetage `fr.iutvalence.info.but.r2_01.labyrinthGame.exceptions`
- toutes les autres classes appartiennent au paquetage
  `fr.iutvalence.info.but.r2_01.labyrinthGame.core`.


## Compléments de spécifications

## `Labyrinth`

Cette classe est modifiée de sorte d'utiliser un ensemble plutôt qu'un tableau pour représenter les cellules interdites.

Ce changement a un impact sur :
- Le constructeur,
- La méthode `isForbiddenCellAt` (qui peut être simplifiée).

## `Main`

L'application est modifiée de sorte de s'adapter à l'évolution du constructeur de la classe `Labyrinth`.
