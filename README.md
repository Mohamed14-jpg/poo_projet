Livrable 02
 
	
	ABDELKADER MEKKI Mohamed 
	NIATI Mohamed Amine 

Implémentation du Jeu de la Vie
Introduction
Dans ce livrable, nous présentons l'implémentation du Jeu de la Vie de Conway en C++ en respectant les principes de la programmation orientée objet (POO). L'objectif est de concevoir une solution modulaire et évolutive tout en fournissant une expérience utilisateur interactive en mode console et graphique grâce à la bibliothèque SFML.
Explication des Classes
Le programme repose sur plusieurs classes, voici un résumé des rôles de chaque classe :
•	Cell (classe abstraite) : Définit les méthodes essentielles (update, display, et isAlive) implémentées dans ses sous-classes.
o	AliveCell : Représente une cellule vivante et applique les règles de survie.
o	DeadCell : Représente une cellule morte et applique les règles de naissance.

•	Grid : Modélise la grille principale, gère l'état des cellules et calcule leur évolution en fonction des règles du jeu.
•	FileManager (en planification) : Permettrait de sauvegarder/charger l'état de la grille à partir de fichiers.
•	Modes (graphiques et console) : Offrent deux interfaces utilisateur distinctes. ModeGraphic utilise SFML pour un rendu visuel, tandis que ModeConsole utilise une représentation textuelle.

Changements par rapport au Livrable 01 :
Lors de l’implémentation, nous avons réalisé que certaines modifications étaient nécessaires pour mieux répondre aux exigences fonctionnelles et pour améliorer la modularité du code. Voici les principaux changements apportés :
 
1)	Ajout de la classe abstraite Cell :
o	Le diagramme initial ne comprenait pas de distinction claire entre les cellules vivantes et mortes. Nous avons introduit une classe abstraite Cell pour gérer ces deux types de cellules.
      


   Attributs :
•	bool isAlive : Indique si la cellule est vivante.
                   Méthodes abstraites :
•	update(Grid grid) : Met à jour l'état de la cellule.
•	getNextState(Grid grid) : Calcule l'état futur de la cellule.
•	display() : Affiche la cellule.
	AliveCell : Représente une cellule vivante.
	DeadCell : Représente une cellule morte.

2)	Classe abstraite Mode
•	Définit une interface commune pour les différents modes d'affichage (ModeGraphic et ModeConsole) et qui contient des méthodes abstraites :
o	displayGrid(Grid grid) : Affiche une grille donnée.
o	handleInput() : Gère les entrées utilisateur.
o	initialize() : Initialise le mode.
o	refresh() : Met à jour l'affichage.

3)	Révision de la classe Grid :
o	La classe Grid a été enrichie pour inclure des méthodes facilitant le calcul des voisins vivants et la gestion de l'évolution de l'automate.

4)	Classe FileManager
Gère les fichiers d'entrée/sortie.
•	Méthodes :
o	loadFromFile(string filename, Grid grid) : Charge une grille à partir d'un fichier.
o	saveToFile(string filename, Grid grid) : Sauvegarde une grille dans un fichier.
o	validateFile(string filename) : Vérifie si un fichier est valide.





Modification du Diagramme de Cas d'Utilisation
Dans cette nouvelle version du diagramme de cas d’utilisation, nous avons apporté quelques ajustements pour mieux refléter les fonctionnalités ajoutées et les flux d'interaction. Le diagramme montre désormais plus précisément comment l'utilisateur interagit avec l'application.





 

