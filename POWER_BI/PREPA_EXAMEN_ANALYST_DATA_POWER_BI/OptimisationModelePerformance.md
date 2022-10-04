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
#### Passer en revue les performances des mesures, des relations et des visuels

[Voir doc  Utiliser l’analyseur de performances pour examiner les performances des éléments de rapport.](https://learn.microsoft.com/fr-fr/power-bi/create-reports/desktop-performance-analyzer)

1. **Identifier les goulots d’étranglement des performances de rapport** 
    - Pour obtenir des performances optimales dans les rapports:
        - Il faut créer un modèle de données efficace avec des **requêtes et des mesures à exécution rapide**. 
        - Lorsqu'on a une bonne base, on peut améliorer le modèle en analysant les plans de requête et les dépendances, puis en apportant des modifications pour optimiser les performances.
        - Il faut examiner les mesures et les requêtes du modèle de données afin de s'assurer qu'on utilise la méthode la plus efficace pour obtenir les résultats souhaités. 
        - ***Le point de départ doit être d’identifier les goulots d’étranglement qui existent dans le code.*** 
            - *Quand on identifie la requête la plus lente dans le modèle de données, on peut se concentrer d’abord sur le goulot d’étranglement le plus important et établir une liste de priorités pour traiter les autres problèmes.*
    1. ***Analyser les performances***
        - On peut utiliser l’Analyseur de performances dans Power BI Desktop pour essayer de savoir comment chacun des éléments de rapport se comporte quand l’utilisateur interagit avec lui. 
            - *Par exemple, on peut déterminer le temps nécessaire à l’actualisation d’un visuel particulier quand l’opération est démarrée par une interaction avec l’utilisateur. L’ ***Analyseur de performances*** aide à identifier les éléments qui contribuent aux problèmes de performances, ce qui peut être utile pour la résolution de ces derniers.*
        - Avant d’exécuter l’Analyseur de performances, et afin d’obtenir les résultats les plus précis de analyse (test), il faut **veuiller à ce que les "caches de visuels" et "de moteur de données" soient vides**.
            1. **Cache de visuels:**
                - Lorsqu'on charge un visuel, on ne peut pas effacer ce cache sans fermer Power BI Desktop et le rouvrir. ***Pour éviter toute mise en cache en opération, il faut démarrer l'analyse avec un cache de visuels vide.***
                - **NB :** *Pour s'assurer d’avoir un cache de visuels vide, on ajoute une page vierge au fichier Power BI Desktop (.pbix), puis, une fois cette page sélectionnée, on enregistre et ferme le fichier. ensuite on reouvre le fichier Power BI Desktop (.pbix) que l'on souhaite analyser. Il s’ouvre sur la page vierge.*
            2. **Cache du moteur de données:**
                - Lorsqu'un une requête est exécutée, les résultats sont mis en cache, de sorte que les résultats d'analyse sont trompeurs. ***Il faut vider le cache de données avant de réexécuter le visuel.***
                - ***Pour vider le cache de données, on peut soit redémarrer Power BI Desktop, soit connecter **DAX Studio** au modèle de données, puis appeler la **commande Clear Cache** (Vider le cache).***
        - **Une fois qu'on a vidé les caches et ouvert le fichier Power BI Desktop sur la page vierge, => Onglet Affichage et sélection de l’option Analyseur de performances.**
    - Pour commencer le processus d’analyse:
        1. sélection **Démarrer l’enregistrement**, 
            - sélection de la page du rapport que l'on souhaite analyser et interagir avec les éléments du rapport que l'on souhaite mesurer. 
            - ====> les résultats des interactions s’afficher progressivement dans le volet Analyseur de performances.
            - Une fois terminé => bouton Arrêter.
    
    ![](https://learn.microsoft.com/fr-fr/training/modules/optimize-model-power-bi/media/2-performance-analyzer-overview-ssm.png)

    2. **Examination des résultats** 
        - 
