# Note explicative : Observatoire forestier du Haut-Rhin
 
## 1. Analyse et préparation des données
La première phase du projet a consisté à isoler les enjeux strictement forestiers à partir du jeu de données « Occupation du sol du Haut-Rhin (DIMAP) » et de la couche de « Sensibilité aux feux de forêt dans le Haut-Rhin (DDT 68) ».

* **Filtrage thématique :** Pour garantir la pertinence de l'analyse, seuls les peuplements forestiers ont été conservés pour l’occupation du sol (cod_n3 : 311, 312, 313, 314 et 315). Ce choix permet d'exclure les surfaces urbanisées ou en eau pour se concentrer sur la vulnérabilité des essences (feuillus, conifères, mixtes, jeunes plantations).
* **Croisement spatial :** Une intersection a été réalisée entre l'occupation du sol et la grille de sensibilité. Ce traitement permet de lier chaque polygone de forêt à son indice de risque (DN).
* **Indicateurs surfaciques :** Le calcul des surfaces en hectares a révélé des points de vigilance majeurs, notamment pour les feuillus (81 603 ha en risque critique) et les conifères (31 286 ha en risque critique).

## 2. Choix technologiques pour la valorisation
Dans une première approche, des outils de valorisation des données ont été envisagés, notamment MapStore, mis à disposition en libre accès sur la plateforme DataGrandEst. Toutefois, les possibilités de personnalisation de la cartographie interactive et des interactions avancées y apparaissaient limitées au regard des objectifs de l’observatoire. L’outil Mviewer Studio, identifié comme une alternative pertinente, n’était quant à lui pas accessible dans le cadre de cet exercice. Ces constats ont conduit à privilégier le développement d’une solution sur mesure, offrant une plus grande liberté de conception et d’interaction. 

Ainsi, une solution de webmapping interactive reposant sur l’utilisation de la bibliothèque **Leaflet.js**, couplée à **Chart.js**, a été mise en œuvre. Ce choix offre une meilleure accessibilité et une grande réactivité, en permettant une exploration dynamique des données. Par ailleurs, l’interactivité croisée entre la carte et les graphiques permet une lecture conjointe des dimensions spatiales et statistiques : une action sur l’un des éléments entraîne automatiquement une mise à jour de l’autre, facilitant ainsi l’analyse des informations.

## 3. Stratégie de représentation visuelle
L’outil a été pensé pour répondre à différents niveaux de lecture : une approche synthétique destinée aux décideurs, reposant sur la visualisation des zones prioritaires et des indicateurs clés, une lecture analytique à destination des techniciens forestiers via les filtres et la datavisualisation détaillée, ainsi qu’une dimension pédagogique favorisant l’appropriation des données par un public plus large.

Le design a été pensé pour offrir une lecture immédiate des zones à enjeux :

* **Thème sombre (Dark mode) :** Ce choix esthétique permet de faire ressortir les couleurs vives des indices de sensibilité. Il réduit également la fatigue visuelle lors d'une utilisation prolongée en mode analyse.
* **Échelle chromatique du risque :** Une progression chromatique intuitive a été retenue, allant du bleu (risque 0) au rouge (risque 4). Cette sémiologie graphique permet une identification rapide des secteurs prioritaires par les décideurs.
* **Datavisualisation dynamique :** Le graphique en anneau situé en bas de la barre latérale présente la répartition des niveaux de risque. Son titre et son contenu s’adaptent dynamiquement en fonction du type de peuplement ou du niveau de sensibilité aux feux sélectionné, permettant une contextualisation précise des données statistiques.
* **Transparence et fonds de carte :** L'ajout d'un curseur d'opacité et de trois fonds de carte (sombre, clair, satellite) permet à l'utilisateur d'alterner entre une vue d'analyse statistique et une vue de terrain pour localiser précisément les massifs.

## 4. Conclusion et perspectives
Cet observatoire constitue un outil d’aide à la décision en mettant en évidence la nécessité, pour la gestion du risque incendie dans le Haut-Rhin, de prioriser l’intégration de la vulnérabilité spécifique des différents peuplements, dont une part très importante est exposée à un niveau de risque élevé (niveau 4). Par ailleurs, l’outil présente un caractère évolutif et pourrait être enrichi par l’intégration de données relatives à la défense des forêts contre les incendies (points d’eau, pistes DFCI), afin de croiser les niveaux de sensibilité avec les capacités opérationnelles de lutte.
