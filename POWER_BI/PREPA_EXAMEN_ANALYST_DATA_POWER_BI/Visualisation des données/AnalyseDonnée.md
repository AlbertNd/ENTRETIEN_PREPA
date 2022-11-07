# Analyse de données dans Power Bi 
- L'analytique englobe les pratique suivant:
    - L’exploration de données, 
    - L’analytique de Big Data, 
    - Le machine learning, 
    - L’IA 
    - L’analytique prédictive.
- L’analytique peut transformer des données brutes en une vaste collection d’informations qui catégorise les données pour identifier et analyser les données et modèles (patterns) comportementaux.
    - *On peut utiliser ces informations pour analyser l’état actuel de leurs opérations et prédire le comportement et les tendances à venir, en effectuant des simulations de scénarios*
    - *les analyses peuvent être utiles pour la détection des fraudes, la reconnaissance d’images, l’analyse des sentiments, la productivité générale des employés, et elles remplacent souvent des processus manuels fastidieux.*
- Il est possible d'utiliser le visuel des **influenceurs clés de Microsoft Power BI** pour effectuer des tâches analytiques avancées. La qualité du visuel dépend de la qualité des données. 
    - *Les fonctionnalités analytiques avancées de Power BI vous permettent d’identifier les catégories et les tendances, de voir comment les données changent au fil du temps. À partir de ces informations, on peut créer des modèles de données prédictifs. Ainsi aider à prendre des décisions stratégiques, ou à établir des plans et des prévisions d’une plus grande fiabilité.*

#### Explorer le récapitulatif statistique 
1. **Fonctions statistique**
    - Power BI Desktop dispose d’un certain nombre de fonctions DAX qui permettent d’obtenir des statistiques rapides en fonction des données.
        - On peut accéder à ces fonctions rapides en cliquant avec le bouton droit sur le champ **Valeur** dans le volet **Visualisations**.

        ![](https://learn.microsoft.com/fr-fr/training/modules/perform-analytics-power-bi/media/2-statistical-functions-ssm.png#lightbox)

        - ***NB: pour éviter tout problème de performances, il est préférable de créer les mesures statistiques soit meme, en utilisant les fonctions DAX pour calculer la moyenne, la somme, le minimum, le maximum, etc.***
            - `Average Qty = AVERAGE ( Sales[Order Qty] )`
2. **Histogramme**
    - Un visuel de graphique à barres ou d’histogramme classique dans Power BI met en relation deux points de données, une mesure et une dimension. Un histogramme diffère légèrement d’un graphique à barres standard, car il ne permet de visualiser qu’un seul point de données.
    - Si on veut utiliser le visuel d’histogramme groupé pour présenter un histogramme qui détermine les quantités commandées par tailles de commandes.
        1. sélection l’icône d’histogramme groupé dans le volet Visualisation
        2. Creation d'un regroupement pour l’axe X
            - Dans le **Champs** => click droit sur le champs de donées à analyser => Selection **Nouveau groupe** => une fenetre **Groupe** s'affiche 

            ![](https://learn.microsoft.com/fr-fr/training/modules/perform-analytics-power-bi/media/2-add-group-histogram-ss.png)

            1. On renomme le groupe Classes de commande (compartiments).
            2. On affecte à l’option **Type de groupe** la valeur **Compartiment**, et l’option **Type de compartiment** la valeur **Nombre de compartiments**.
            3. Introduire la valeur 5 pour le Nombre de compartiments, la valeur 1 pour la Valeur minimale et la valeur 44 pour la Valeur maximale.
        3. On remplit le visuel 
            1. Un drag and drop du champs concerné (OrderQty), du volet **Champs** vers le champs **Valeur** dans le volet **Visualisations**
            2. Un drag and drop du groupe concerné (Classes de commande (compartiments)), du volet **Champs** vers le champ **Axe** dans le volet **Visualisations**.

            ![](https://learn.microsoft.com/fr-fr/training/modules/perform-analytics-power-bi/media/2-set-up-histogram-ssm.png)

            - *l'histogramme affiche la quantité commandée (champ OrderQty) par compartiments de taille de commande.*
3. **Analyse des N premiers**
    - *La fonction **DAX TOPN** retourne les N premières lignes d’une table spécifique. L’analyse des N premiers est un excellent moyen de présenter des données qui peuvent être importantes, par exemple les 10 produits les plus vendus, les 10 meilleurs éléments d’une organisation ou les 10 meilleurs clients. On peut également adopter le point de vue inverse, et présenter les 10 derniers éléments d’une liste, en d’autres termes, les plus mauvais éléments.*
        - IL est possible d'utiliser trois methodes 
            1. **Un visuel Questions et réponses**
                - Power BI dispose d’un visuel Questions et réponses intégré qui permet aux utilisateurs de poser leurs propres questions et d’obtenir des réponses.
                - Le visuel Questions et réponses est un outil efficace, car il permet aux utilisateurs d’obtenir rapidement des réponses relatives aux données de manière indépendante.
                - Les utilisateurs peuvent poser leur question et peuvent eux aussi créer des visuels pertinents.
                - **On ajoute la visualisation Questions et réponses au rapport, puis on repositionne le visuel et on personnalise sa mise en forme selon les besoins.**

                ![](https://learn.microsoft.com/fr-fr/training/modules/perform-analytics-power-bi/media/2-add-question-answer-visual-ssm.png)

                - ***Ainsi si on souhaite connaître les 10 produits les plus vendus. on entrer une question telle que « Quels sont mes 10 produits les plus vendus ». Power BI affiche automatiquement ces résultats.***

                ![](https://learn.microsoft.com/fr-fr/training/modules/perform-analytics-power-bi/media/2-use-question-answer-find-top-n-ss.png)
            
            2. **un filtre de type N premiers**
                - N premiers est une option de filtrage disponible dans le **volet Filtres**
                    - Sélection du champ à analyser dans la page de rapport. *Dans cet exemple, il s’agit du champ Product Name (Nom de produit)*. 
                    - Dans le **volet Filtres**, dans la liste Type de filtre => sélection **N premiers**. 
                        - Dans les paramètres correspondant à Afficher les éléments, => sélection **Top et 10** =>  Sélection **Cost of Sales** (Coût des ventes) en tant que valeur de filtrage du champ. Le visuel se met à jour en conséquence.

                        ![](https://learn.microsoft.com/fr-fr/training/modules/perform-analytics-power-bi/media/2-use-filter-find-top-n-ssm.png)
            
            3. **une fonction DAX TOPN**
                - Il est possible de calculer la part représentée par les 10 meilleurs produits en DAX, à l’aide de la fonction TOPN. 
                    - Cette option peut s’avérer utile si on souhaite présenter les 10 premiers éléments dans un autre contexte, par exemple la part que représentent les 10 produits les plus vendus dans le total des ventes.
                - => On utilise la fonction **TOPN** ainsi que la fonction **SUMX**, pour calculer la part des 10 meilleurs produits par rapport au total des ventes
                    - `Top 10 Products = SUMX ( TOPN ( 10, Product, Product[Total Sales]), [Total Sales] )`

                    ![](https://learn.microsoft.com/fr-fr/training/modules/perform-analytics-power-bi/media/2-use-dax-function-calculate-top-n-ss.png#lightbox)

                - [Voir Doc Fonctions statistiques - DAX](https://learn.microsoft.com/fr-fr/dax/statistical-functions-dax)

#### Identifier les valeurs hors norme avec les visuels Power BI
- Une valeur hors norme est un type d’anomalie dans les données, quelque chose qu'on n’attend pas ou qui a surpris, en fonction des moyennes ou des résultats historiques. 
    - Il faut identifier les valeurs hors norme pour isoler les points de données qui diffèrent considérablement des autres points de données, puis prendre des mesures afin de comprendre les raisons de ces différences. Les résultats de cette analyse peuvent avoir un impact significatif sur la prise de décision.
    - Supposons un scénario dans lequel on analyse les données d’un entrepôt d’expédition. On remarque que le nombre de commandes a dépassé la moyenne pour une catégorie de produit spécifique. On souhaite d’abord identifier la catégorie de produit concernée. on se poser plusieurs questions sur la valeur hors norme :
        - Est-ce qu’il y a eu des expéditions supérieures à la moyenne ce jour-là ?
        - Cette anomalie s’est-elle produite dans un entrepôt spécifique ?
        - Un seul événement a-t-il provoqué la hausse des commandes pour une catégorie spécifique ?
        - Cet événement est-il survenu d’autres jours comme celui-ci au cours du dernier mois, du dernier trimestre, de la dernière année ou d’une année antérieure ?
- **Power BI permet d’identifier les valeurs hors norme dans les données.** 
    - *Toutefois, il faut d’abord déterminer quelle est la logique sur laquelle reposent ces valeurs hors norme. On peut utiliser des points de déclenchement, comme par exemple des calculs, autour de ce qu'on considére comme une valeur hors norme.*
    - Le processus d’identification des valeurs hors norme implique la segmentation des données en deux groupes:
        - Correspond aux données hors norme et l’autre non. 
        - On peut utiliser des colonnes calculées pour identifier les valeurs hors norme. 
            - *Toutefois, les résultats sont statiques jusqu’à ce qu'on actualise les données.*
    - ***Une meilleure façon d’identifier les valeurs hors norme est d’utiliser une visualisation ou une formule DAX, car avec ces méthodes on a la garantie que les résultats sont dynamiques.***
    - Une fois qu'on a identifié les valeurs hors norme dans les données, on peut utiliser des segments ou des filtres pour mettre en évidence ces valeurs hors norme. En outre, on peut ajouter une légende aux visuels afin que les valeurs hors norme puissent être identifiées parmi les autres données. Ainsi, on peut accéder aux données hors norme pour une analyse plus détaillée.
        1. **Utiliser un visuel pour identifier les valeurs hors norme**
            - Le meilleur visuel à utiliser pour identifier les valeurs hors norme est **le nuage de points**, 
                - Ils montrent la relation entre deux valeurs numériques. 
                - Ils affichent des modèles dans de grands ensembles de données et sont donc idéaux pour afficher les valeurs hors norme.
                - Quand on ajoute un nuage de points au rapport Power BI, on place les champs intéressants dans les sections **Axe X** et **Axe Y** respectivement.
                    - *Le champ Orders Shipped (Commandes expédiées) se trouve sur l’axe X et le champ Qty Orders (Quantité commandes) sur l’axe Y.*

                    ![](https://learn.microsoft.com/fr-fr/training/modules/perform-analytics-power-bi/media/3-add-scatter-chart-ss.png) 

                    ![](https://learn.microsoft.com/fr-fr/training/modules/perform-analytics-power-bi/media/3-scatter-chart-outlier-ss.png)

                    - ***Les éléments isolés sont ceux éloignés de la majeure partie des données. On peut rechercher les raisons de leur existence et entreprendre une action corrective.***
        2. **Utiliser DAX pour identifier les valeurs hors norme**
            - On peut utiliser la formule DAX pour créer une mesure qui va identifier les valeurs hors norme dans les données:
                -   ```
                       Valeur hors normes =
                        CALCULATE (
                            [Order Qty],
                            FILTER (
                                VALUES ( Product[Product Name] ),
                                COUNTROWS ( FILTER ( Sales, [Order Qty] >= [Min Qty] ) ) > 0
                            )
                        ) 
                    ```
                    - ***Order Qty*** *est une mesure dans la table* ***Sales***, *tandis que* ***Min Qty*** *fait référence à la plus petite quantité de commandes dans la table* ***Sales*** 
            - Une fois qu'on a créé une mesure hors norme, on peut regrouper les produits en catégories à l’aide de la fonctionnalité de regroupement, comme fait au moment de la création d’un histogramme. 
                - Il faut ensuite ajouter un visuel de nuage de points, comme fait dans la section précédente, car il s’agit de la meilleure option de visualisation pour afficher les valeurs hors norme.
                - Une fois que on a ajouté le nuage de points, on remplis avec les champs associés à la formule DAX et à la mesure de valeurs hors norme.

                ![](https://learn.microsoft.com/fr-fr/training/modules/perform-analytics-power-bi/media/3-select-outlier-logic-fields-ss.png)

                ![](https://learn.microsoft.com/fr-fr/training/modules/perform-analytics-power-bi/media/3-scatter-chart-populate-outliers-ss.png)

#### Regrouper les données et leur appliquer un binning à des fins d’analyse
- Le **Binning** est similaire au regroupement mais il est utilisé pour regrouper des champs continus, tels que des nombres et des dates.
    - On peut utiliser les fonctionnalités de regroupement et de compartimentage pour s'assurer que les visuels des rapports affichent les données selon nos préférences. L’utilisation de ces fonctionnalités permet d’afficher, d’analyser et d’explorer clairement les données et les tendances des visuels. 
        - On peut identifier des clusters, 
        - des modèles comportementaux, 
        - des moyennes de données, 
        - etc. 
    - Les résultats de cette analyse fournissent aux utilisateurs des **insights** plus spécifiques de leurs données, ce qui peut déclencher des décisions commerciales.
1. **Créer un groupe**
    1. Sélection (Ctrl + clic) des points de données qu'on souhaite regrouper sur le visuel. Dans ce cas, il s’agit des États dont les ventes sont supérieures à 500 000 dollars. 
    2. Clic droit sur l’un des points de données sélectionnés => l’option **Données de groupe**.

    
    ![](https://learn.microsoft.com/fr-fr/training/modules/perform-analytics-power-bi/media/4-group-data-visual-ssm.png)

    - Dans ce graphique à barres dans lequel Power BI a automatiquement segmenté les données de la manière la plus utile: *(Total des ventes par État)*.l’idée est de regrouper certaines barres (États) pour les voir sous forme d’une seule catégorie. L'utilisateur pourra ainsi identifier les États présentant les ventes les plus élevées.

    ![](https://learn.microsoft.com/fr-fr/training/modules/perform-analytics-power-bi/media/4-updated-visual-group-ssm.png)

    - ***Le champ du nouveau groupe s’affiche dans le compartiment Légende du visuel et qu’il est listé dans le volet Champs***
    - *Quand on crée un groupe, il est possible de changer la façon dont les données sont affichées dans le visuel.*
        - *On peut être amené à changer les valeurs de chaque axe*
        - *On peut utiliser le groupe dans l’un des autres visuels du rapport.* 
    - Pour ce faire, faire glisser le champ du groupe depuis le volet **Champs** et le deposer dans le visuel où on souhaite l’utiliser.
2. **Modifier un groupe**
    - Si on souhaite modifier les catégories qui composent le groupe precedent. 
        1. Clic droit sur le champ de groupe dans le compartiment **Légende** ou le volet Champs => sélection **Modifier les groupes**.
        2. Dans la fenêtre Groupes qui s’affiche
            - Une liste des groupes et différents éléments de ces groupes. 

        ![](https://learn.microsoft.com/fr-fr/training/modules/perform-analytics-power-bi/media/4-edit-group-ssm.png)

        - *Le groupe* ***States with Sales > 500k (États avec ventes > 500k)*** *et ses membres ainsi que le groupe*  
        ***Autre*** *, soit* ***States with Sales < 500k*** *(États avec ventes < 500k), qui contient toutes les valeurs qui n’ont pas été placées dans le premier groupe*. 
            - *Si on actualise les données et si de nouveaux éléments apparaissent dans la liste des valeurs dissociées, ils sont tous placés dans le groupe Autre.*
        - Il est possible de renommer un groupe en double-cliquant sur le titre du groupe dans la section Groupes et membres, puis en entrant un nouveau nom. 
        - Il est possible d'ajouter des valeurs dissociées à un groupe existant, supprimer des valeurs d’un groupe existant et créer un groupe.
3. **Créer des groupes de classes**
    - Le processus de binning permet de regrouper les données de champs numériques et de temps en « compartiments » (bins) de taille égale. Cette approche permet de visualiser et d’identifier les tendances des données de manière plus explicite. Le binning permet de dimensionner correctement les données affichées par Power BI Desktop.
    - Si on souhaite créer des classes (groupes) pour le champ **Order Qty** (Quantité commandée). 
        1. Dans le **volet Champs** => clic droit sur le champ Order Qty *(pour lequel on souhaite créer les classes)*  => sélection **Nouveau groupe**. 
        2. Dans la fenêtre Groupes qui s’affiche, on affecte à l’option **Taille du compartiment** la valeur souhaitée, et on ajuste d’autres paramètres le cas échéant => sélection **OK**.

        ![](https://learn.microsoft.com/fr-fr/training/modules/perform-analytics-power-bi/media/4-create-bin-ss.png)

        - ***Une fois le groupe de classes configuré, un nouveau champ dans le volet Champs avec la mention (classes) est  ajoutée à son nom. Faire glisser ce champ sur le canevas pour utiliser la taille de classe dans un visuel.***






    