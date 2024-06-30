# Step-6 : Entrées-sorties

## Travail à réaliser

A l'aide du **diagramme UML** (partiel, centré sur les classes utiles) disponible dans le répertoire `Step-6/uml`, de la **documentation Javadoc complète** disponible dans le répertoire `Step-6/docs`, 
et des **précisions** données dans la section `compléments de spécifications` ci-dessous :

- :wrench: **Copier** le code des classes de `Step-5/src` vers `Step-6/src`.
- :wrench: **Configurer** `Step-6/src` comme **unique** répertoire source du projet.
- :pencil: **Ecrire** la classe `PositionFormatException`.
- :pencil: **Modifier** la classe `Position`.
- :pencil: **Ecrire** l'interface `LabyrinthParser`.
- :pencil: **Ecrire** la classe `AsciiLabyrinthParser`.
- :pencil: **Ecrire** la classe `ByContentLabyrinthParser`.
- :pencil: **Modifier** le code de l'application `Main`.
- :white_check_mark: **Exécuter l'application `Main` et vérifier que la sortie console est conforme à ce qui est attendu**.
- :label: **Effectuer un commit** de l'ensemble des modifications, en indiquant `Step-6` comme message et en utilisant la zone détail si besoin.
- :rocket: **Pousser immédiatement** le commit sur Gitlab.
- :eyes: **Vérifier** que le commit est bien disponible sur Gitlab.


:warning: Gestion des paquetages :

- la classe `Main` appartient au **paquetage par défaut**,
- les classes `InvalidLabyrinthException` et `PositionFormatException` appartiennent au paquetage `fr.iutvalence.info.but.r2_01.labyrinthGame.exceptions`
- la classe `ConsoleLogger` appartient au paquetage `fr.iutvalence.info.but.r2_01.labyrinthGame.loggers`
- les classes `AbstractRobotArtificialIntelligence`,
  `RandomRobotArtificialIntelligence` et `ConsoleLogger` appartiennent au paquetage `fr.iutvalence.info.but.r2_01.labyrinthGame.robots`.
- l'interface `LabyrinthParser` et les classes `AsciiLabyrinthParser` et 
    `ByContentLabyrinthParser` appartiennent au paquetage `fr.iutvalence.info.but.r2_01.labyrinthGame.parsers`.
- toutes les autres classes appartiennent au paquetage
  `fr.iutvalence.info.but.r2_01.labyrinthGame.core`.


## Compléments de spécifications

## `Position`


*** REPRENDRE ICI ***
*** Refaire uml, et la doc

Cette classe représente un tour de la simulation, c'est une structure de données immuable.

N.B. cette classe redéfinit `toString`.

## `RobotArtificialIntelligence`

Cette interface décrit le contrat d'une intelligence artificielle de robot :

- obtenir le nom du robot, l'action à réaliser pour le tour
- notifier en retour le robot du résultat d'une action de mouvement.

## `Logger`

Cette interface décrit le contrat d'un mécanisme de journalisation pour la simulation :

- journaliser l'état de début de simulation (nombre maximum de tours, position/direction du robot, position de la sortie)
- journaliser un tour
- journaliser la fin de simulation (atteinte de la sortie, timeout)

## `LabyrinthGame`

Cette classe représente une simulation (pour un labyrinth, une intelligence artificielle de robot et un mécanisme de journalisation).

## `ConsoleLogger`

Cette classe est une implémentation de mécanisme de journalisation qui affiche des messages sur la console.

## `AbstractRobotArtificialIntelligence`

Cette classe est une implémentation d'intelligence artificielle de robot qui factorise la gestion du nom.

## `RandomRobotArtificialIntelligence`

Cette classe est une implémentation d'intelligence artificielle de robot dont la décision d'action respecte la règle :
- si le dernier mouvement vers l'avant a conduit à un blocage, l'action est un changement de direction choisi aléatoirement
- sinon, l'action est un mouvement vers l'avant.

## `Main`

L'application est modifiée de sorte qu'après avoir créé le labyrinthe, elle lance une simulation sur ce labyrinthe avec
le mécanisme de journalisation sur la console et le comportement de robot précédent.
