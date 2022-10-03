# Optimiser un modèle pour améliorer les performances dans Power BI 
- ptimisation des performances consiste à apporter des modifications à l’état actuel du modèle de données afin qu’il s’exécute plus efficacement
    - *Il arrive que le rapport s’exécute correctement dans les environnements de test et de développement, mais que des problèmes de performances se produisent quand il est déployé en production en vue d’une consommation élargie. Du point de vue d’un utilisateur du rapport, les performances médiocres se caractérisent par un chargement des pages de rapport et une mise à jour des visuels qui prennent plus de temps. Cette dégradation des performances entraîne une expérience utilisateur négative.* 
    - ***Neuf fois sur dix, les performances médiocres sont le résultat direct d’un modèle de données incorrect et/ou d’expressions DAX (Data Analysis Expressions) incorrectes.***
- Un modèle de données de taille inférieure utilise moins de ressources (mémoire) et permet d’accélérer l’actualisation des données, les calculs et le rendu des visuels dans les rapports. 
    - ***le processus d’optimisation des performances implique de réduire la taille du modèle de données et de tirer pleinement parti des données dans le modèle, notamment en :***
        - ***S’assurant que les types de données corrects sont utilisés***
        - ***Supprimant les colonnes et les lignes inutiles***
        - ***Évitant les valeurs répétées***
        - ***Remplaçant les colonnes numériques par des mesures***
        - ***Réduisant les cardinalités***
        - ***Analysant les métadonnées du modèle***
        - ***Résumant les données dans la mesure du possible***
    
    ![](https://learn.microsoft.com/fr-fr/training/modules/optimize-model-power-bi/media/1-conceptual-graphic-of-tasks-c.png)

    ```
        Toutefois, gardez à l’esprit que, même si vous pouvez la plupart du temps vous appuyer sur les recommandations de base en matière de performances et de bonnes pratiques dans Power BI, pour optimiser un modèle de données afin d’améliorer les performances des requêtes, vous devrez probablement vous associer à un ingénieur Données pour conduire l’optimisation du modèle de données dans les sources de données sources.
    ```