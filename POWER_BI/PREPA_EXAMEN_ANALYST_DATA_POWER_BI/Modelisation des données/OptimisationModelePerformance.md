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
        - On peut examiner les résultats du test de performances dans le volet **Analyseur de performances**. 
            - Pour passer en revue les tâches par ordre de durée, de la plus longue à la plus courte: 
                - => click droit sur l’icône **Trier** en regard de l’en-tête de colonne **Durée (ms)** => sélection **Durée totale** en guise d’ordre **Décroissant**.

        ![](https://learn.microsoft.com/fr-fr/training/modules/optimize-model-power-bi/media/2-sort-results-performance-analyzer-ss.png)

        - Les informations de journalisation de chaque visuel indiquent le temps nécessaire (durée) pour effectuer les catégories de tâches suivantes :
            - **Requête DAX** : temps qu’il a fallu au visuel pour envoyer la requête et à Analysis Services pour retourner les résultats.
            - **Affichage de visuel** : temps qu’il a fallu pour que le visuel s’affiche à l’écran, y compris le temps nécessaire pour récupérer les images web ou le géocodage.
            - **Autre** : temps qu’il a fallu au visuel pour préparer les requêtes, attendre la fin d’autres visuels ou effectuer d’autres tâches de traitement en arrière-plan. 
                - ***Si cette catégorie affiche une longue durée, le seul moyen réel de réduire celle-ci consiste à optimiser les requêtes DAX pour les autres visuels ou à réduire le nombre de visuels dans le rapport.***
            
            ![](https://learn.microsoft.com/fr-fr/training/modules/optimize-model-power-bi/media/2-categories-performance-analyze-results-ss.png)

            - *Les résultats du test d’analyse aident à comprendre le comportement du modèle de données et à identifier les éléments à optimiser. on peut comparer la durée de chaque élément dans le rapport et identifier les éléments qui ont une longue durée. Il faut se concentrer sur ces éléments et rechercher la raison pour laquelle ils sont longs à se charger sur la page de rapport.*

            - [Pour analyser les requêtes plus en détail, on peut utiliser DAX Studio, outil open source gratuit](https://daxstudio.org/)

#### Résoudre les problèmes et optimiser les performances

- Les informations suivantes fournissent des conseils sur les éléments à rechercher et les modifications que l'on peut apporter : 
    1. **Visuels** 
        - Si on identifie des visuels comme goulot d’étranglement entraînant des performances médiocres, il faut trouver un moyen d’améliorer les performances avec un impact minimal sur l’expérience utilisateur.
        - On regarde le nombre de visuels dans la page du rapport ; ***moins de visuels est synonyme de meilleures performances***. 
        - Se demande si un visuel est vraiment nécessaire et s’il ajoute de la valeur pour l’utilisateur final. Si la réponse est non, on supprime le visuel. Plutôt que d’utiliser plusieurs visuels dans la page, on peut envisager d’autres moyens de fournir des détails supplémentaires, tels que des pages d’extraction et des info-bulles de page de rapport.
        - Il faut Examiner le nombre de champs dans chaque visuel. 
            - Plus le nombre de visuels dans le rapport est grand, plus les risques de problèmes de performances sont élevés. En outre, plus le nombre de visuels est grand, plus le rapport peut sembler encombré et perdre en clarté. 
            - *La limite supérieure pour les visuels étant de 100 champs (mesures ou colonnes), un visuel avec plus de 100 champs est lent à charger. Il faut se poser la question de savoir si on a vraiment besoin de toutes ces données dans un visuel.*
    2. **Requête DAX**
        - Lorsqu'on examine les résultats dans le volet **Analyseur de performances**, on peut voir combien de temps il a fallu au moteur Power BI Desktop pour évaluer chaque requête ***(en millisecondes)***. 
            - *Une requête DAX qui prend plus de **120 millisecondes** est un bon point de départ.* 
            - Dans cet exemple : une requête qui a une longue durée.

            [](https://learn.microsoft.com/fr-fr/training/modules/optimize-model-power-bi/media/2-performance-analyzer-large-duration-measures-ssm.png)

            - L’Analyseur de performances met en évidence les problèmes potentiels, mais n'indique pas ce qui doit être fait pour y remédier. Il faut utiliser [DAX Studio](https://daxstudio.org/) pour étudier les requêtes plus en détail.
                - *En copiant la requete dans **DAX Studio**. on peut ensuite examiner l’étape de calcul.* 
                    - *Par exemple, si on essaie de compter le nombre total de produits dont la quantité commandée est supérieure ou égale à cinq.*
                    -   ```
                            Count Customers =
                            CALCULATE (
                                DISTINCTCOUNT ( Order[ProductID] ),
                                FILTER ( Order, Order[OrderQty] >= 5 )
                            )
                        ```
                - *Après l’analyse de la requête, on peut utiliser ses propres connaissances et expérience pour identifier où se situent les problèmes de performances. on peut également essayer d’utiliser différentes fonctions DAX pour déterminer si elles améliorent les performances.* 
                    -   ```
                            Count Customers =
                            CALCULATE (
                                DISTINCTCOUNT ( Order[ProductID] ),
                                KEEPFILTERS (Order[OrderQty] >= 5 )
                            )
                        ```

                    - Dans l’exemple, la fonction **FILTER** a été remplacée par la fonction **KEEPFILTER**. Quand le test a été réexécuté dans l’Analyseur de performances, la durée a été plus courte en raison de la fonction **KEEPFILTER**.

                    - Apres la modification, pour vérifier si la durée a été améliorée ou non, on vide le cache de données, puis on réexécute le processus de l’**Analyseur de performances**.

                    ![](https://learn.microsoft.com/fr-fr/training/modules/optimize-model-power-bi/media/2-performance-analyzer-small-duration-measures-ssm.png)

    3. **Modèle de données**
        - Si la durée des mesures et visuels affiche des valeurs basses (en d’autres termes, ils ont une durée courte), ils ne sont pas à l’origine des problèmes de performances. ***En revanche, si la requête DAX affiche une valeur de durée élevée, il est probable qu’une mesure est mal écrite ou qu’un problème a affecté le modèle de données***. Le problème peut être dû à des relations, des colonnes ou des **métadonnées dans le modèle**, ou bien à l’état de l’option **Date/heure automatique**.
    4. **Relations**
        - Il faut examiner les relations entre les tables pour vérifier qu'on a établi les bonnes relations. 
        - Vérifier que les propriétés de **cardinalité des relations sont correctement configurées**. 
            - ***Par exemple, une colonne « un » contenant des valeurs uniques peut être configurée de manière incorrecte en tant que colonne « plusieurs ».*** 
    5. **Colonnes**
        - [Voir Doc Techniques de réduction des données pour la modélisation des importations. ](https://learn.microsoft.com/fr-fr/power-bi/guidance/import-modeling-data-reduction)
        - ***Il est conseillé de ne pas importer de colonnes de données dont on a pas besoin***. 
            - *Pour éviter de supprimer des colonnes dans l’Éditeur Power Query, il faut essayer de les traiter à la source lors du chargement de données dans Power BI Desktop.* 
                - Toutefois, s’il est impossible de supprimer les colonnes redondantes de la requête source ou que les données ont déjà été importées dans leur état brut, on peut toujours utiliser l’Éditeur Power Query pour examiner chaque colonne. 
                    - se pose la question de si on a vraiment besoin de chaque colonne et essayer d’identifier l’avantage que chacune d’elles apporte au modèle de données. 
                    - *Supposons, par exemple, qu'on dispose d’une colonne ID avec des milliers de lignes uniques. ***Comme on n’utilisera pas cette colonne dans une relation, elle ne sera utilisée dans aucun rapport***. Il faut donc considérer cette colonne comme inutile et admettre qu’elle gaspille de l’espace dans le modèle de données.*
    6. **Métadonnées** 
        - Les métadonnées sont des informations sur d’autres données. Les métadonnées Power BI contiennent des informations sur le modèle de données, telles que le **nom**, le **type** de données et le **format** de chacune des colonnes, le **schéma** de la base de données, la **conception des rapports**, la **date de dernière modification du fichier**, la **fréquence d’actualisation des données** et bien plus encore...
        - Quand on charge des données dans Power BI Desktop, il est recommandé d’analyser les métadonnées correspondantes afin de pouvoir identifier les incohérences avec le jeu de données et normaliser les données avant de commencer à créer des rapports. L’exécution d’une analyse sur les métadonnées améliore les performances du modèle de données, car, au cours de cette opération, on identifie les colonnes inutiles, les erreurs au sein des données, les types de données incorrects, le volume de données chargées (le chargement des jeux de données volumineux, notamment les données transactionnelles ou historiques, prend plus de temps) et bien plus encore...
        - On peut utiliser l’Éditeur Power Query dans Power BI Desktop pour examiner les colonnes, les lignes et les valeurs des données brutes. 
            - Et ensuite utiliser les outils disponibles, tels que ceux mis en évidence dans la capture d’écran suivante, pour apporter les modifications nécessaires.

            ![](https://learn.microsoft.com/fr-fr/training/modules/optimize-model-power-bi/media/2-query-editor-home-tab-ssm.png)

        - **Les options Power Query sont les suivantes** :
            - **Colonnes inutiles** : évalue la nécessité de chaque colonne. Si on n’envisage pas d’utiliser une ou plusieurs colonnes dans le rapport, il faut les supprimer à l’aide de l’option **Supprimer les colonnes** sous l’onglet **Accueil**.
            - **Lignes inutiles** : vérifie les premières lignes du jeu de données pour voir si elles sont vides ou si elles contiennent des données dont on a pas besoin dans le rapports. Si c’est le cas,il faut supprimer ces lignes à l’aide de l’option **Supprimer les lignes** de l’onglet **Accueil**.
            - **Type de données** : évalue les types de données de colonne pour s’assurer que chacun d’eux est correct. Si on identifie un type de données incorrect, on le change en sélectionnant successivement la colonne, l’option Type de données sous l’onglet **Transformer** et le type de données approprié dans la liste.
            - **Noms des requêtes** : on examine les noms des requêtes (tables) dans le **volet Requêtes**. À l’image des noms d’en-tête de colonne, on doit changer les noms de requête inhabituels ou qui n’aident pas pour des noms qui sont plus évidents ou qui sont plus familiers à l’utilisateur. On peut renommer une requête en cliquant dessus avec le bouton droit, en sélectionnant Renommer, en modifiant le nom comme il se doit, puis en appuyant sur Entrée.
            - **Détails de la colonne** : l’Éditeur Power Query dispose des trois options d’aperçu des données suivantes, que on peut utiliser pour analyser les métadonnées associées oux colonnes. Ces options se trouvent sous l’onglet Affichage.
                - **Qualité de la colonne** : détermine le pourcentage d’éléments de la colonne qui sont valides, comportent des erreurs ou sont vides. **Si le pourcentage de validité n’est pas 100**, il faut en rechercher la raison, corriger les erreurs et remplir les valeurs vides.
                - **Distribution des colonnes** : Identifie le nombre d’éléments distincts et le nombre d’éléments uniques. Ces informations sont utiles pour identifier la cardinalité d’une colonne. 
                - **Profil de colonne** : Affiche des statistiques supplémentaires pour la colonne et un graphique montrant la distribution des éléments uniques.

            ![](https://learn.microsoft.com/fr-fr/training/modules/optimize-model-power-bi/media/2-data-preview-column-profile-options-ssm.png)

            - **NB** ***Si on examine un grand jeu de données contenant plus de 1 000 lignes et que l'on souhaite analyser l’ensemble du jeu de données, il faut changer l’option par défaut en bas de la fenêtre.*** 
                - Sélection **Profilage de la colonne en fonction des 1 000 premières lignes** => **Profilage de colonne basé sur l’ensemble du jeu de données**.

                ![](https://learn.microsoft.com/fr-fr/training/modules/optimize-model-power-bi/media/2-column-profile-rows-ssm.png)

                - *Les autres métadonnées qu'on doit prendre en compte sont les informations sur le modèle de données dans son ensemble, telles que la taille de fichier et la fréquence d’actualisation des données. On peut trouver ces métadonnées dans le fichier Power BI Desktop (.pbix) associé. Les données qu'on charge dans Power BI Desktop sont compressées et stockées sur le disque par le moteur de stockage **VertiPaq**. La taille du modèle de données a un impact direct sur ses performances ; un modèle de données de taille inférieure utilise moins de ressources (mémoire) et permet d’accélérer l’actualisation des données, les calculs et le rendu des visuels dans les rapports.*
    7. **Fonctionnalité Date/heure automatique**
        - [Voir Doc Appliquer l’option de date/heure automatique dans Power BI Desktop.](https://learn.microsoft.com/fr-fr/power-bi/transform-model/desktop-auto-date-time)
        - Par défaut, cette fonctionnalité est activée globalement, ce qui signifie que Power BI Desktop crée automatiquement une table calculée masquée pour chaque colonne de date, à condition que certaines conditions soient remplies. Les nouvelles tables masquées s’ajoutent aux tables qu'on a déjà dans le jeu de données.
        - ***L’option **Date/heure automatique** permet d’utiliser l’Assistant **Time Intelligence** pour le filtrage, **le regroupement et l’exploration des périodes calendaires** au niveau du détail*
            - *Il est ecommandé de conserver l’option **Date/heure automatique** **activée** uniquement quand on utilise des périodes calendaires et quand le modèle présente des exigences simples par rapport à l’heure.*
        - ***Si la source de données définit déjà une **table de dimension de date**, cette table doit être utilisée pour définir de manière cohérente l’heure, et il faut **désactiver** l’option **Date/heure automatique** globale. La désactivation de cette option peut réduire la taille de votre modèle de données et le temps d’actualisation.***
        - On peut **activer/désactiver** cette option Date/heure automatique de manière **globale** afin qu’elle s’applique à tous les fichiers Power BI Desktop, ou bien l’activer ou la désactiver pour le fichier actuel afin qu’elle ne s’applique qu’à un fichier spécifique.
        - Pour **activer/désactiver** cette option Date/heure automatique, => **Fichier** => **Options et paramètres** => **Options** => sélection **page Global** ou **Fichier actuel**. Sur l’une ou l’autre des pages, sélection **Chargement des données** puis, dans la section **Time Intelligence**, on coche ou décochez la case en fonction des besoins.

        ![](https://learn.microsoft.com/fr-fr/training/modules/optimize-model-power-bi/media/2-auto-date-time-configure-global-options-ssm.png)


#### Utilisation des variables pour améliorer les performances et la résolution des problèmes
- On peut utiliser des variables dans les formules DAX pour essayer d’écrire des calculs moins complexes et plus efficaces.     
    - *Elles sont efficaces et il faut les utiliser par défaut pour créez des mesures.* 
    - Certaines expressions impliquent l’utilisation de nombreuses fonctions imbriquées et la réutilisation de la logique d’expression. Le traitement de ces expressions prend plus de temps et celles-ci sont difficiles à lire, ce qui complique la résolution de leurs problèmes. Si on utilise des variables, on peut économiser du temps de traitement des requêtes. Ce changement est une étape dans la bonne direction pour optimiser les performances d’un modèle de données.
- L’utilisation de variables offre les avantages suivants :
    1. **Amélioration des performances** : les variables peuvent rendre les mesures plus efficaces, car Power BI n’a plus besoin d’évaluer plusieurs fois la même expression. On peut obtenir les mêmes résultats dans une requête en environ moitié moins de temps par rapport au traitement d’origine.
    2. **Lisibilité améliorée** : les variables ont des noms courts et autodescriptifs et sont utilisées à la place d’une expression à plusieurs mots ambiguë. Il peut s’avérer plus facile de lire et de comprendre les formules quand des variables sont utilisées.
    3. **Simplification du débogage** : On peut utiliser des variables pour déboguer une formule et des expressions de test, ce qui peut être utile lors de la résolution des problèmes.
    4. **Réduction de la complexité** : les variables ne nécessitent pas l’utilisation des fonctions **DAX EARLIER** ou **EARLIEST**, qui sont difficiles à comprendre. Ces fonctions étaient nécessaires avant l’introduction des variables et étaient écrites dans des expressions complexes qui introduisaient de nouveaux contextes de filtre. Comme on peut désormais utiliser des variables au lieu de ces fonctions, on peut écrire moins de formules complexes.

1. **Utiliser des variables pour améliorer les performances**
    - Les formules suivantes présentent une définition de mesure de deux manières différentes *(les formule répète l’expression qui calcule « même période l’année précédente »)*: 
        - **Sans la variable** 
            -   ```
                    Sales YoY Growth =
                    DIVIDE (
                        ( [Sales] - CALCULATE ( [Sales], PARALLELPERIOD ( 'Date'[Date], -12, MONTH ) ) ),
                        CALCULATE ( [Sales], PARALLELPERIOD ( 'Date'[Date], -12, MONTH ) )
                    )
                ```
        - **Avec la variable** 
            -   ```
                    Sales YoY Growth =
                    VAR SalesPriorYear =
                        CALCULATE ( [Sales], PARALLELPERIOD ( 'Date'[Date], -12, MONTH ) )
                    VAR SalesVariance =
                        DIVIDE ( ( [Sales] - SalesPriorYear ), SalesPriorYear )
                    RETURN
                        SalesVariance
                ```
            - ***Cette définition utilise le mot clé **VAR** pour introduire une variable nommée **SalesPriorYear** et utilise une expression pour attribuer le résultat « même période l’année précédente » à cette nouvelle variable. Elle utilise ensuite la variable deux fois dans l’expression **RETURN***.
        - **NB:** *Dans la première définition de la mesure dans le tableau, la formule n’est pas efficace, car elle nécessite que Power BI évalue deux fois la même expression. La seconde définition est plus efficace car, grâce à la variable, Power BI ne doit évaluer l’expression **PARALLELPERIOD** qu’une seule fois.*
2. **Utilisation des variables pour améliorer la lisibilité**
    - *Quand des variables sont utilisées, il est recommandé de leur attribuer des noms descriptifs. Dans l’exemple précédent, la variable est appelée SalesPriorYear (Ventes de l’année antérieure), indiquant clairement ce qu’elle calcule. En revanche, l’utilisation d’une variable appelée X, temp ou variable1 n’aurait pas du tout mis en évidence l’objectif de la variable.*
    - *L’utilisation de noms clairs, concis et explicites permet de mieux comprendre ce qu'on essaie de calculer, et il sera beaucoup plus simple pour d’autres développeurs de gérer le rapport par la suite.*
3. **Utiliser des variables pour résoudre plusieurs étapes**
    - Il est possible d'utiliser des variables pour essayer de déboguer une formule et identifier le problème.
        - On peut simplifier la résolution des problèmes du calcul DAX à l’aide de variables en évaluant chacune d’elles séparément et en les rappelant après l’expression RETURN.
        ```
            Sales YoY Growth % =
            VAR SalesPriorYear =  CALCULATE([Sales], PARALLELPERIOD('Date'[Date], -12, MONTH))
            VAR SalesPriorYear% = DIVIDE(([Sales] - SalesPriorYear), SalesPriorYear)  
            RETURN  SalesPriorYear
        ```
        - *Ici on teste une expression qui est attribuée à une variable. À des fins de débogage, on réécrit provisoirement l’expression **RETURN** à écrire dans la variable. La définition de la mesure retourne uniquement la variable **SalesPriorYear**, car c’est ce qui vient après l’expression RETURN.*
            - *L’expression RETURN affiche uniquement la valeur **SalesPriorYear**. Cette technique permet de rétablir l’expression quand on a terminé le débogage. En outre, elle simplifie la compréhension des calculs en raison de la réduction de la complexité du code DAX.*
#### Réduire la cardinalité
-La cardinalité est un terme utilisé pour décrire l’unicité des valeurs d’une colonne. La cardinalité est également utilisée dans le contexte des relations entre deux tables, où elle décrit la direction de la relation.
1. **Identifier les niveaux de cardinalité dans les colonnes**
    - Dans le processus d'analyse des metadonnées, l’option **Distribution des colonnes** de l’onglet **Affichage** présente des statistiques sur le nombre d’éléments **distincts** et **uniques** présents dans chaque colonne des données.

    ![](https://learn.microsoft.com/fr-fr/training/modules/optimize-model-power-bi/media/4-column-distribution-statistics-ssm.png)

    - ***Nombre de valeurs distinctes*** : *nombre total de valeurs différentes trouvées dans une colonne donnée.*
    - ***Nombre de valeurs uniques*** : *nombre total de valeurs qui n’apparaissent qu’une seule fois dans une colonne donnée.* 
        1. Une colonne dont la plage **contient de nombreuses valeurs répétées** *(le nombre de valeurs distinctes est faible)* **présente un niveau de cardinalité bas**. 
        2. Une colonne dont la plage **contient de nombreuses valeurs uniques** *(le nombre de valeurs uniques est élevé)* **présente un niveau de cardinalité élevé**.
    - **NB: Une cardinalité plus faible donnant des performances plus optimisées, vous devrez peut-être réduire le nombre de colonnes présentant un niveau de cardinalité élevé dans votre jeu de données.**

2. **Réduire la cardinalité des relations** 
    - Power BI Desktop offre différentes techniques qu'on peut utiliser pour réduire les données chargées dans des modèles de données, **telles que le résumé**. En réduisant les données chargées dans le modèle, on améliore la cardinalité des relations du rapport. Il est donc important de chercher à réduire les données à charger dans les modèles. Cela est particulièrement vrai pour les modèles de grande taille ou les modèles appelés à croître au fil du temps.
    - La technique la plus efficace pour réduire la taille d’un modèle consiste peut-être à utiliser une **table de résumé à partir de la source de données**. 
        - ***Alors qu’une table de détails peut contenir chaque transaction, une table de résumé peut contenir un enregistrement par jour, par semaine ou par mois. Il peut s’agir d’une moyenne de toutes les transactions par jour, par exemple.***
            - *Ainsi, une table source de faits de ventes stocke une ligne pour chaque ligne de commande. Pour réduire significativement les données, on peut résumer toutes les métriques de ventes en effectuant des regroupements par date, client et produit, si les détails des transactions individuelles ne sont pas nécessaires.*
    - On peut ensuite obtenir une réduction encore plus significative des données en effectuant un regroupement par date au niveau du mois. on pourrait ainsi atteindre une réduction de 99 % de la taille du modèle. 
        - ***Toutefois, la création de rapports au niveau du jour ou d’une commande spécifique n’est alors plus possible. Le fait de résumer les données de type fait implique toujours un compromis avec les détails des données. Un inconvénient est qu'on risque de perdre la possibilité d’effectuer des recherches dans les données, car les détails n’existent plus. Ce compromis peut être atténué à l’aide d’une conception de type **mode mixte***.
            - *Une conception de type mode mixte produit un modèle composite. Il permet de déterminer un mode de stockage pour chaque table. Ainsi, chaque table peut avoir sa propriété Mode de stockage définie sur **Importer ou DirectQuery**.*
    - Une technique efficace pour réduire la taille du modèle consiste à définir sur **DirectQuery** la propriété **Mode de stockage pour les tables de type de faits plus grandes**.
        - On peut combiner cette approche de conception avec les techniques utilisées pour résumer les données. 
            - *Par exemple, les données de ventes résumées peuvent être utilisées pour la création de rapports « résumés » hautes performances. 
                - On peut créer une page d’extraction afin d’afficher les ventes précises pour un contexte de filtre spécifique (et étroit), dans laquelle sont reprises toutes les commandes client propres à ce contexte. La page d’extraction inclut des visuels basés sur une table DirectQuery qui permettent de récupérer les données des commandes client (détails des commandes client).
[Voir Doc Techniques de réduction des données pour la modélisation des importations.](https://learn.microsoft.com/fr-fr/power-bi/guidance/import-modeling-data-reduction#group-by-and-summarize/?azure-portal=true)

#### Optimiser les modèles DirectQuery avec un stockage au niveau de la table
[Voir Doc Guide du modèle DirectQuery dans Power BI Desktop. ](https://learn.microsoft.com/fr-fr/power-bi/guidance/directquery-model-guidance)

- DirectQuery est un moyen d’obtenir des données dans Power BI Desktop. La méthode DirectQuery implique la connexion directe aux données dans leur dépôt source à partir de Power BI Desktop. Il s’agit d’une alternative à l’importation de données dans Power BI Desktop.

![](https://learn.microsoft.com/fr-fr/training/modules/optimize-model-power-bi/media/5-direct-query-option-getting-data-ssm.png)

- *Lorsqu'on utilise la méthode DirectQuery, l’expérience utilisateur globale dépend fortement des performances de la source de données sous-jacente. Les temps de réponse lents des requêtes entraînent une expérience utilisateur négative, voire une expiration des requêtes dans les cas les plus pessimistes. En outre, le nombre d’utilisateurs qui ouvrent les rapports à un moment donné impacte la charge qui est placée sur la source de données. Par exemple, si le rapport contient 20 visuels et que 10 personnes utilisent le rapport, 200 requêtes ou plus existent sur la source de données, car chaque visuel émet une ou plusieurs requêtes.*
- Les performances du modèle Power BI ne sont pas uniquement affectées par les performances de la source de données sous-jacente, mais également par d’autres facteurs incontrôlables, tels que les suivants :
    - Latence du réseau : les réseaux plus rapides retournent les données plus rapidement.
    - Les performances du serveur de la source de données et la quantité d’autres charges de travail sur ce serveur. Par exemple,les implications de l’actualisation d’un serveur pendant que des centaines de personnes utilisent ce même serveur pour différentes raisons.
- Ainsi, l’utilisation de DirectQuery représente un risque pour la qualité des performances du modèle. Pour optimiser les performances dans ce cas, il faut contrôler la base de données source ou y accéder.

1. **Implications de l’utilisation de DirectQuery**
- [Voir Doc Implications de l’utilisation de DirectQuery](https://learn.microsoft.com/fr-fr/power-bi/connect-data/desktop-directquery-about#implications-of-using-directquery)
- [Voir Doc  Guide du modèle DirectQuery dans Power BI Desktop](https://learn.microsoft.com/fr-fr/power-bi/guidance/directquery-model-guidance)
- [Voir Doc Guide pour une utilisation efficace de DirectQuery.](https://learn.microsoft.com/fr-fr/power-bi/connect-data/desktop-directquery-about#guidance-for-using-directquery-successfully/?azure-portal=true)
- Il est recommandé d’importer des données dans Power BI Desktop, mais on peut être amenée à utiliser le mode de connectivité des données DirectQuery pour l’une des raisons suivantes (avantages de DirectQuery) :
    - Il est approprié dans les cas où les données changent fréquemment et que la création de rapports en quasi-temps réel est nécessaire.
    - Il peut gérer des données volumineuses sans qu’il soit nécessaire d’effectuer une pré-agrégation.
    - Il applique des restrictions de souveraineté des données pour se conformer aux exigences légales.
    - Il peut être utilisé avec une source de données multidimensionnelles qui contient des mesures comme SAP Business Warehouse (BW).
2. **Comportement des connexions DirectQuery** 
    - Quand on utilise DirectQuery pour se connecter à des données dans Power BI Desktop, cette connexion se comporte de la façon suivante :
        - Quand on utilise initialement la fonctionnalité Obtenir les données dans Power BI Desktop, il faut sélectionner la source. Si on se connecte à une source relationnelle, on peut sélectionner un ensemble de tables, et chacune d’entre elles définit une requête qui retourne un jeu de données de façon logique. Si on sélectionne une source multidimensionnelle, par exemple SAP BW, on ne peut sélectionner que celle-ci.
        - Lorsqu'on charge les données, aucune donnée n’est importée dans Power BI Desktop ; seul le schéma est chargé. Et quand on génére un visuel dans Power BI Desktop, les requêtes sont envoyées à la source sous-jacente pour récupérer les données nécessaires. Le temps nécessaire à l’actualisation du visuel dépend des performances de la source de données sous-jacente.
        - Si des modifications sont apportées aux données sous-jacentes, elles ne sont pas répercutées immédiatement dans les visuels existants dans Power BI en raison de la mise en cache. Il faut effectuer une actualisation pour voir ces modifications. Les requêtes nécessaires sont présentes pour chaque visuel, et les visuels sont mis à jour en conséquence.
        - La publication du rapport dans le service Power BI engendre un jeu de données dans ce service, comme pour une importation. Toutefois, aucune donnée n’est incluse dans ce jeu de données.
        - Lorsqu'on ouvre un rapport existant dans le service Power BI ou que on en crée un, la source sous-jacente est réinterrogée afin que soient récupérées les données nécessaires. Selon l’endroit où se trouve la source d’origine, on doit peut-être configurer une passerelle de données locale.
        - On peut épingler des visuels ou des pages de rapport entières sous forme de vignettes de tableau de bord. Les vignettes sont actualisées automatiquement selon une planification, par exemple toutes les heures. On peut contrôler la fréquence de cette actualisation en fonction des besoins. Quand on ouvre un tableau de bord, les vignettes reflètent les données au moment de la dernière actualisation et peuvent ne pas inclure les dernières modifications apportées à la source de données sous-jacente. On peut toujours actualiser un tableau de bord ouvert pour s'assurer qu’il est à jour.
3. **Limitations des connexions DirectQuery** 
    - L’utilisation de DirectQuery peut avoir des conséquences négatives. Les limitations varient selon la source de données utilisée. Il faut tenir compte des points suivants :
        - **Performances** : Expérience utilisateur globale dépend fortement des performances de la source de données sous-jacente.
        - **Sécurité** : si on utilise plusieurs sources de données dans un modèle DirectQuery, il est important de comprendre comment les données se déplacent entre les sources de données sous-jacentes et les implications de sécurité associées. Il faut également déterminer si des règles de sécurité s’appliquent aux données de la source sous-jacente, car, dans Power BI, chaque utilisateur peut voir ces données.
        - **Transformation des données** : par rapport aux données importées, les données provenant de DirectQuery ont des limites si on souhaite appliquer des techniques de transformation de données dans l’Éditeur Power Query. Par exemple, si on se connectez à une source OLAP, telle que SAP BW, on ne peut pas effectuer de transformations ; le modèle externe entier est extrait de la source de données. Si on souhaite appliquer des transformations aux données, il faut le faire dans la source de données sous-jacente.
        - **Modélisation** : certaines des fonctionnalités de modélisation disponibles avec des données importées ne sont pas utilisables ou sont limitées dans le cadre de DirectQuery.
        - **Création de rapports** : presque toutes les fonctionnalités de création de rapports disponibles avec des données importées sont également prises en charge pour les modèles DirectQuery, à condition que la source sous-jacente offre un niveau de performances approprié. Toutefois, quand le rapport est publié dans le service Power BI, les fonctionnalités **Quick Insights et Questions et réponses** ne sont pas prises en charge. En outre, l’utilisation de la fonctionnalité Explorer dans Excel entraîne probablement une baisse des performances.
4. **Optimiser les performances** 
    1. ***Optimiser les données dans Power BI Desktop***
        - Quand on a optimisé la source de données autant que possible, on peut prendre des mesures supplémentaires dans Power BI Desktop à l’aide de l’ **Analyseur de performances**, où on peut isoler des requêtes pour valider les plans de requête.
        - On peut analyser la durée des requêtes qui sont envoyées à la source sous-jacente pour identifier les requêtes dont le chargement prend beaucoup de temps. En d’autres termes, identifier où se trouvent les goulots d’étranglement.
        - On a pas besoin d’utiliser une approche spéciale pour optimiser un modèle DirectQuery ; on peut appliquer les mêmes techniques d’optimisation que celles que on a utilisées sur les données importées pour ajuster les données provenant de la source DirectQuery. 
            - *Par exemple, on peut réduire le nombre de visuels dans la page de rapport ou réduire le nombre de champs utilisés dans un visuel. On peut également supprimer les colonnes et les lignes inutiles.* 
    2. ***Optimiser la source de données sous-jacente (base de données connectée)***
        - Il faut d’abord se pencher sur la source de données. Il faut ajuster la base de données source autant que possible, car tout ce qu'on fait pour améliorer les performances de cette base de données source améliore à son tour Power BI DirectQuery. Les actions qu'on effectue dans la base de données sont les plus efficaces.
        - Envisager l’utilisation des pratiques de base de données standard ci-dessous, qui s’appliquent à la plupart des situations :
            - Éviter l’utilisation de colonnes calculées complexes, car l’expression de calcul est incorporée dans les requêtes source. Il est plus efficace de renvoyer (push) l’expression à la source, car cela évite l’envoi (push down). On peut également envisager d’ajouter des colonnes clés de substitution à des tables de type dimension.
            - Examiner les index et vérifier que l’indexation actuelle est correcte. Si on a besoin de créer des index , il faut s'assurer qu’ils sont appropriés.
        - **NB:** se reporter aux documents d’aide de la source de données afin d’implémenter leurs recommandations en matière de performances.
    3. ***Personnaliser les options de réduction de requête***
        - Power BI Desktop donne la possibilité d’envoyer moins de requêtes et de désactiver certaines interactions qui entraînent une mauvaise expérience si les requêtes résultantes mettent beaucoup de temps à s’exécuter. L’application de ces options empêche les requêtes d’atteindre continuellement la source de données, ce qui devrait améliorer les performances.
        - Pour modifier les paramettre par defaut et active les options de reduction de donnée disponible au model: 
            - => Sélection **Fichier** => **Options et paramètres** => **Options**, faire défiler la page vers le bas, puis sélection de l’option **Réduction de requête**.
        - ***Les options de réduction de requête suivantes sont disponibles*** :
            - **Réduire le nombre de requêtes envoyées par** : par défaut, chaque visuel interagit avec tous les autres visuels. Si cette case est cochée, l’interaction par défaut est désactivée. On peut ensuite choisir les visuels qui interagissent les uns avec les autres à l’aide de la fonctionnalité **Modifier les interactions**.
            - **Segments** : par défaut, l’option **Appliquer instantanément les changements de segment** est sélectionnée. Pour forcer les utilisateurs du rapport à appliquer manuellement les changements de segment, on sélectionne l’option **Ajouter un bouton Appliquer à chaque segment pour apporter les changements quand vous êtes prêt**.
            - **Filtres** : par défaut, l’option **Appliquer instantanément les changements des filtres de base** est sélectionnée. Pour forcer les utilisateurs du rapport à appliquer manuellement les changements de filtre, on sélectionne l’une des options suivantes :
                - **Ajouter des boutons Appliquer à chaque filtre de base pour appliquer les changements au besoin**
                - **Ajouter un seul bouton Appliquer au volet des filtres pour appliquer tous les changements à la fois (préversion)** 
        
        ![](https://learn.microsoft.com/fr-fr/training/modules/optimize-model-power-bi/media/5-query-reduction-settings-ssm.png)

#### Créer et gérer des agrégations

[Voir Doc  Utiliser des agrégations dans Power BI Desktop.](https://learn.microsoft.com/fr-fr/power-bi/enterprise/aggregations-auto)

![](https://learn.microsoft.com/fr-fr/training/modules/optimize-model-power-bi/media/6-aggregate-data-overview.ss.png)

- L’agrégation de données consiste à résumer ces dernières et à les présenter à un niveau plus général. 
    - *Par exemple, on peut résumer toutes les données de ventes et les regrouper par date, client, produit, etc.* 
- Le processus d’agrégation réduit la taille des tables dans le modèle de données, ce qui permet de se concentrer sur les données importantes et aide à améliorer les performances des requêtes.
- On peut decider d'utiliser des agregations dans le modele de donnée our les raisons suivant:
    - *Si on utilise une grande quantité de données (Big Data), les agrégations fournissent de meilleures performances de requête et aident à analyser et à révéler les **insights** de ces données volumineuses. Les données agrégées étant mises en cache, elles utilisent beaucoup moins de ressources que celles nécessaires pour les données détaillées.*
    - *En cas d’actualisation lente, les agrégations aident à accélérer le processus d’actualisation. La taille de cache étant plus petite, le temps d’actualisation est réduit et les utilisateurs disposent des données plus rapidement. Au lieu d’actualiser ce qui pourrait être des millions de lignes, on doit actualiser une plus petite quantité de données.*
    - *Si on a un grand modèle de données, les agrégations peuvent aider à réduire et à maintenir sa taille.*
    - *Si on pense que la taille du modèle de données est appelée à augmenter, on peut utiliser des agrégations afin de protéger de manière proactive le modèle de données contre les risques éventuels de problèmes de performances, d’actualisation ainsi que de problèmes de requête globaux.* 

1. **Création d'agrégations**
- Avant de commencer à créer des agrégations, il faut choisir le degré de précision (niveau) avec lequel on souhaite les créer. ensuite decider de a facon dont on souhaite les créer
    - Si on a accès à la base de données, on peut créer une table avec l’agrégation, puis importer cette table dans Power BI Desktop.
    - Si on a accès à la base de données, on peut créer une vue pour l’agrégation, puis importer cette vue dans Power BI Desktop.
    - Dans Power BI Desktop, on peut utiliser l’Éditeur Power Query pour créer les agrégations pas à pas.

- ***Exemple*** 

![](https://learn.microsoft.com/fr-fr/training/modules/optimize-model-power-bi/media/6-aggregate-data-before-ssm.png)

- Si on souhaite agreger les données en fonction de la colonne **orderDate** et afficher les colonnes **OrderQuantity** et **SalesAmount** 
    - => Onglet **Acceuil** => Selection **Choisir des colonnes** => selection des colonnes que l'on souhaite agreger => **OK**
    - => Onglet **Acceuil** => **Regrouper par** => Selection de la colonne en fonction de laquelle on souhaite regrouper(OrderDate) => introduction du nom de la nouvelle colonne(OnlineOrdersCount). 
    - => Selection **Avancé** => **Ajouter une agrégation** pour afficher une autre colonne => Introduction du nom de la colonne d'agrégation => selection de l'opération de la colonne => selection de la colonne  laquelle on souhaite lier l'agrégation 
    - On repete les étapes jusqu'a ce qu'on est ajouter toutes les agrégations => **OK**

    1. 
    ![](https://learn.microsoft.com/fr-fr/training/modules/optimize-model-power-bi/media/6-aggregate-data-before-ssm.png)

    2. 
    ![](https://learn.microsoft.com/fr-fr/training/modules/optimize-model-power-bi/media/6-aggregate-choose-columns-ssm.png)

    3. 
    ![](https://learn.microsoft.com/fr-fr/training/modules/optimize-model-power-bi/media/6-aggregate-group-ssm.png)

    4. 
    ![](https://learn.microsoft.com/fr-fr/training/modules/optimize-model-power-bi/media/6-aggregate-data-after-new-columns-ss.png)
    
    - *Une fois l’agrégation affichée, on peut voir comment les données ont été transformées. Les données sont agrégées pour chaque date, avec pour chacune le nombre de commandes ainsi que les sommes respectives du montant des ventes et de la quantité commandée.*
    - **Fermer et appliquer** pour fermer l’Éditeur Power Query et appliquer les modifications apportées au modèle de données. 
        - Retour à la page Power BI Desktop => sélection du bouton **Actualiser** pour voir les résultats. 
            - *On observe l’écran, car un bref message affiche le nombre de lignes que contient désormais le modèle de données. Ce nombre de lignes doit être considérablement inférieur au nombre initial. On peut également voir ce nombre quand on ouvre l’Éditeur Power Query, le nombre de lignes a été réduit à 30.
    
    ![](https://learn.microsoft.com/fr-fr/training/modules/optimize-model-power-bi/media/6-aggregate-data-after-less-rows-ssm.png)

2. **Gestion d'agregation**
    - Il est possible d'apporter des modification aux agregation créée si nécessaire. 
        - => Click droit sur le champs => **Gérer les agrégations** 

    ![](https://learn.microsoft.com/fr-fr/training/modules/optimize-model-power-bi/media/6-open-manage-aggregations-window-ssm.png)

    - *Pour chaque colonne d’agrégation, on peut sélectionner une option dans la liste déroulante Résumé et apporter des modifications à la table et à la colonne de détails sélectionnées.* 




