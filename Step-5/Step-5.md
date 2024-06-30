# Step-5 : Abstractions

## Travail à réaliser

A l'aide du **diagramme UML** (partiel, centré sur les classes utiles) disponible dans le répertoire `Step-5/uml`, de la **documentation Javadoc complète** disponible dans le répertoire `Step-5/docs`, 
et des **précisions** données dans la section `compléments de spécifications` ci-dessous :

- :wrench: **Copier** le code des classes de `Step-4/src` vers `Step-5/src`.
- :wrench: **Configurer** `Step-5/src` comme **unique** répertoire source du projet.
- :pencil: **Ecrire** la classe `StepInfo`.
- :pencil: **Ecrire** l'interface `RobotArtificialIntelligence`.
- :pencil: **Ecrire** l'interface `Logger`.
- :pencil: **Compléter** le code de la classe `LabyrinthGame`.
- :pencil: **Ecrire** la classe `ConsoleLogger`.
- :pencil: **Ecrire** la classe `AbstractRobotArtificialIntelligence`.
- :pencil: **Ecrire** la classe `RandomRobotArtificialIntelligence`.
- :pencil: **Modifier** le code de l'application `Main`.
- :white_check_mark: **Exécuter l'application `Main` et vérifier que la sortie console est conforme à ce qui est attendu**.
- :label: **Effectuer un commit** de l'ensemble des modifications, en indiquant `Step-5` comme message et en utilisant la zone détail si besoin.
- :rocket: **Pousser immédiatement** le commit sur Gitlab.
- :eyes: **Vérifier** que le commit est bien disponible sur Gitlab.


:warning: Gestion des paquetages :

- la classe `Main` appartient au **paquetage par défaut**,
- la classe `InvalidLabyrinthException` appartient au paquetage `fr.iutvalence.info.but.r2_01.labyrinthGame.exceptions`
- la classe `ConsoleLogger` appartient au paquetage `fr.iutvalence.info.but.r2_01.labyrinthGame.loggers`
- les classes `AbstractRobotArtificialIntelligence`,
  `RandomRobotArtificialIntelligence` et `ConsoleLogger` appartiennent au paquetage `fr.iutvalence.info.but.r2_01.labyrinthGame.robots`.
- toutes les autres classes appartiennent au paquetage
  `fr.iutvalence.info.but.r2_01.labyrinthGame.core`.


## Compléments de spécifications

## `StepInfo`

Cette classe représente un tour de la simulation, c'est une structure de données immuable qui contient :

- le numéro du tour
- la position et la direction du robot avant l'action
- l'action effectuée 
- la position et la direction du robot après l'action

N.B. cette classe redéfinit `toString` (cf. Javadoc).

## `RobotArtificialIntelligence`

Cette interface décrit le contrat d'une intelligence artificielle de robot qui permet :

- d'obtenir le nom du robot, l'action à réaliser pour le tour
- de notifier le robot du résultat d'une action de mouvement.

## `AbstractRobotArtificialIntelligence`

Cette classe abstraite est une implémentation de l'interface précédente dont le but est de factoriser le nom.

## `RandomRobotArtificialIntelligence`

Cette classe est comportement de robot qui consiste à : 
- effectuer une action de mouvement si c'est possible (si l'action précédente n'a pas conduit à un blocage)
- effectuer une action de rotation au hasard sinon 

## `Logger`

Cette interface décrit le contrat d'un mécanisme de journalisation pour la simulation qui permet de journaliser :

- l'état de début de simulation (nombre maximum de tours, position/direction du robot, position de la sortie)
- les informations concernant un tour
- la fin de simulation (atteinte de la sortie, timeout)

## `LabyrinthGame`

Cette classe représente une simulation (pour un labyrinthe, une intelligence artificielle de robot et un mécanisme de journalisation).

N.B. La direction dans laquelle pointe initialement le robot est choisie aléatoirement.

## `ConsoleLogger`

Cette classe est une implémentation de mécanisme de journalisation qui affiche des messages sur la console.

- en début de simulation :
```
***
START OF GAME
Labyrinth: 200 steps allowed, exit at (3,0)
Robot (DUMB_BOT) at (0,1) heading E
***
```
- au cours d'un tour :
```
---
Step 1
---
Robot initial position: (0,1)
Robot initial heading: N
Action: F
Robot resulting position: (0,1)
Robot resulting heading: N
```
- en fin de partie en cas de sortie :
```
***
Exit reached in 98 steps
***
```
- en fin de partie en cas de timeout :
```
***
Time out!
***
```

## `AbstractRobotArtificialIntelligence`

Cette classe est une implémentation d'intelligence artificielle de robot qui a pour but unique de factoriser la gestion du nom.

## `RandomRobotArtificialIntelligence`

Cette classe est une implémentation d'intelligence artificielle de robot dont la décision d'action respecte la règle suivante :
```
- si le dernier mouvement vers l'avant a conduit à un blocage, l'action est un changement de direction choisi aléatoirement.
- sinon, l'action est un mouvement vers l'avant.
```

## `Main`

L'application est modifiée de sorte qu'après avoir créé le labyrinthe, elle lance une simulation sur ce labyrinthe avec
le mécanisme de journalisation sur la console et le comportement de robot précédent.
