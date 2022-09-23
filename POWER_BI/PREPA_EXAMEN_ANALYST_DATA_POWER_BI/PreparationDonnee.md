# PREPARATION DES DONNEES

### Table des matières

1. [Obtenir les données des fihiers ](#obtenir-des-données-des-fihiers)
    - [Emplacement du fuchier](#1-emplacement-du-fichier-plat)
    - [Se connecter aux données d'un fichier](#2-se-connecter-aux-données-dun-fichier)
    - [Selection des données du fichier à importer](#3-selection-des-données-du-fichier-à-importer)
    - [Changer le fichier source](#4-changer-le-fichier-source)


- Power BI permet d'obetnir des données provenant de nombreux type de fichiers:
    - **Fichiers plats**:
        - Type de fichier qui n'ont qu'un seule table de données et où chaque ligne de données se trouve dans la meme structure.
        - Le fichier ne contient pas de hierarchies
            - **.CSV** : fichier separer par des virgules
            - **.TXT** : fichier texte delimité 
            - Les fichier de largeur fixe
    - **Fichier Excel**
    - ... (***Voir Obetnir Données dans Power BI Desktop***). 

#### Obtenir des données des fihiers 
##### 1. Emplacement du fichier plat.
- ***Local*** : 
    -à l'importation un nouveau jeu de données est créé dans Power BI et les données du fichier excel y sont chargées. 
    - Les modification apportées au fichier excel d'origine ne sontpas refletées dans le jeu de données Power BI. 
    - *On l'utilise pour des données qui ne change pas*
- ***OneDrive Entreprise***:
    - Méthode efficace pour la synchronisation entre un fichier Excel et le jeu de donnée, les rapport et les tableau de bord dans Power BI. 
    - Power BI se connecte regulierement au fichier sur OneDrive, si des modifications sont detectées, le jeu de données, les rapports et les tableaux de bord sont automatiquement mis à ajour dans Power BI. 
- ***OneDrive - Personnel***:
    - Possibilité de beneficier des avantage de oneDrive Entreprise. 
    - Apres connection, selection de l'option **Maintenir la connexion**.
        - *Contact de l'administrateur système pour déterminer si ce type de connexion est autorisé dans l'organisation*.
- ***SharePoint - Site d'équipe***:
    - L’enregistrement des fichiers Power BI Desktop sur des sites d’équipe SharePoint est similaire à un enregistrement sur OneDrive Entreprise. La principale différence est dans la façon de se connecter au fichier depuis Power BI. il faut spécifier une URL ou se  connecter au dossier racine.
    - ![](https://learn.microsoft.com/fr-fr/training/modules/get-data/media/2-local-vs-cloud-c.png)

***NB : L’utilisation d’une option cloud, comme OneDrive ou des sites d’équipe SharePoint, est le moyen le plus efficace de conserver la synchronisation des fichiers avec le jeu de données, les rapports et les tableaux de bord dans Power BI. Cependant, si les données ne changent pas régulièrement, l’enregistrement de fichiers sur un ordinateur local est une option appropriée.***

##### 2. Se connecter aux données d'un fichier

    ![](https://learn.microsoft.com/fr-fr/training/modules/get-data/media/2-get-data-excel-ssm.png)

    ![](https://learn.microsoft.com/fr-fr/training/modules/get-data/media/2-excel-save-data-ssm.png)

##### 3. Selection des données du fichier à importer
    - Une fois le fichier connecté à Power BI Desktop, la fenêtre du Navigateur s’ouvre. 
        - Elle montre les données qui sont disponibles dans la source de données
        - Il est possible de sélectionner une table ou une entité pour afficher un aperçu de son contenu, pour vérifier que les données correctes sont chargées dans le modèle Power BI.

    - On coche la ou les cases à cocher de la ou des tables que l'on souhaite importer dans Power BI. Cette sélection active les boutons:
        - **Charger**: Charger automatiquement vos données dans le modèle Power BI 
        - **Transformer les données** : Lancer l’éditeur Power Query, pour passer en revue et nettoyer les données avant de les charger dans le modèle Power BI.
    ![](https://learn.microsoft.com/fr-fr/training/modules/get-data/media/2-excel-worksheet-ssm.png)

##### 4. Changer le fichier source 
    - Il peut être nécessaire de changer l’emplacement d’un fichier source pour une source de données pendant le développement ou si l’emplacement de stockage des fichiers change. Pour que les rapports restent à jour, il faut mettre à jour les chemins de connexion des fichiers dans Power BI.
        - Power Query offre plusieurs façons d’effectuer cette tâche: 
            1. Paramètres de source de données  
            2. Paramètres de requête 
            3. Éditeur avancé
    ![](https://learn.microsoft.com/fr-fr/training/modules/get-data/media/2-excel-data-source-settings-ssm.png#lightbox)

    -   ```
            Si on change un chemin de fichier, il faut veiller à se reconnecter au même fichier
            avec la même structure de fichier. Toute modification structurelle apportée à un
            fichier, comme la suppression ou le renommage des colonnes dans le fichier source
            interrompt le bon fonctionnement du modèle de génération de rapports.
        ```
____ 

#### Obtenir des données de sources de données relationnelles 
- Power BI Desktop peut se connecter à de nombreuses bases de données relationnelles qui sont locales ou dans le cloud.

1. **Se connecter aux données d’une base de données relationnelle**
    - Utilisation de la fonctionnalité Obtenir les données dans Power BI Desktop et sélection de l’option applicable pour votre base de données relationnelle. 
    
    ![](https://learn.microsoft.com/fr-fr/training/modules/get-data/media/3-get-data-sql-server-dropdown-ssm..png)

    - Introduire le nom du serveur de base de données et un nom de base de données dans la fenêtre **Base de données SQL Server**. Les deux options du mode de connectivité aux données sont les suivantes : 
        - **Importer** (sélectionné par défaut, recommandé) 
        - **DirectQuery**
    ![](https://learn.microsoft.com/fr-fr/training/modules/get-data/media/3-get-data-sql-server-db-ss.png)
    - Connection avec un ***nom d’utilisateur*** et un ***mot de passe***.
        - Trois options de connection: 
            - **Pour Windows** : Compte Windows (informations d’identification Azure Active Directory).
            - **Base de données**: Informations d’identification de base de donnée
            - **Compte Microsoft**: Informations d’identification du compte Microsoft. *Option est souvent utilisée pour les services Azure.*
    ![](https://learn.microsoft.com/fr-fr/training/modules/get-data/media/3-sql-creds-ssm.png)
2. **Selection des données à importer**
    - Une fois que la base de données a été connectée à Power BI Desktop, la fenêtre Navigateur affiche les données qui sont disponibles dans la source de données
        - Il est possible de selectionner une table ou une entité pour afficher un aperçu de son contenu, et pour vérifier que les données correctes seront chargées dans le modèle Power BI.
            - On coche la ou les cases de la ou des tables que l'on souhaite importer dans Power BI Desktop, puis sélection l’option: 
                - **Charger** : Charger automatiquement vos données dans un modèle Power BI dans son état actuel.
                - **Transformer les données**: Ouvrez les données dans Microsoft Power Query, où il est possible d'effectuer des actions comme supprimer des lignes ou des colonnes inutiles, regrouper les données, supprimer les erreurs, et de nombreuses autres tâches liées à la qualité des données.
    ![](https://learn.microsoft.com/fr-fr/training/modules/get-data/media/3-table-selection-ssm.png)



3. **Changement des parametres de la source de données**
- Sous l’onglet **Accueil**, sélection **Transformer les données**, puis sélection de l’option **Paramètres de la source de données**.
![](https://learn.microsoft.com/fr-fr/training/modules/get-data/media/3-change-sql-settings-ssm.png)

- Dans la liste des sources de données qui s’affiche, sélection de la source de données à mettre à jour. Ensuite, click avec le bouton droit sur cette source de données pour voir les options de mise à jour disponibles, ou utilisation les boutons d’option de mise à jour en bas à gauche de la fenêtre. Sélection de l’option de mise à jour souhaité, modification des paramètres, puis appliquer les modifications
![](https://learn.microsoft.com/fr-fr/training/modules/get-data/media/3-sql-data-source-edit-ssm.png)

- Il est également possible de modifier les paramètres de la source de données dans Power Query. 
    - Sélection de la table, puis sélection l’option  **Paramètres de la source de données** dans le ruban **Accueil**. - Il est aussi possible d'accéder au panneau **Paramètres de la requête** sur le côté droit de l’écran et de sélectionner l’icône des paramètres en regard de Source (ou double-cliquez sur Source). Dans la fenêtre qui s’affiche, mettre à jour les informations détaillées du serveur et de la base de données, puis **OK**. En fin **Fermer et appliquer**
    ![](https://learn.microsoft.com/fr-fr/training/modules/get-data/media/3-edit-creds-ssm.png)

##### Importer des données en écrivant une requête SQL  
- Une autre façon d’importer des données est d’écrire une requête SQL pour spécifier seulement les tables et les colonnes souhaités.
    - Pour écrire une requête SQL, dans la fenêtre **Base de données SQL Server**, on introduit les noms du serveur et de la base de données, puis sélection de la flèche en regard de **Options avancées** pour développer cette section et voir vos options. Dans la zone  **Instruction SQL**, on ecrit l’instruction de la requête, puis **OK**.
![](https://learn.microsoft.com/fr-fr/training/modules/get-data/media/3-sql-statement-ss.png)

##### Écrire une instruction SQL
- SQL permet de charger seulement le jeu de données nécessaire en spécifiant certaines colonnes et certaines tables dans les instruction SQL en les important dans le modèle de données.
- Il est égaliment possible de joindre différentes tables, effectuer des calculs spécifiques, créer des instructions logiques et filtrer les données dans les requêtes SQL.

#### Obtenir des données d'une base de données NoSQL
- Une base de données NoSQL (également appelée non-SQL, pas seulement SQL ou non relationnelle) est un type de base de données flexible qui n’utilise pas de tables pour stocker les données. 

1. **Se connecter à une base de données NoSQL**
    - Utilisation dela fonctionnalité **Obtenir les données** dans Power BI Desktop. Selection de l'option **plus**
    - Dansl'exemple ci dessous on selectionne la catégorie **Azure** => **Azure Cosmos DB** => **Se connecter**
    ![](https://learn.microsoft.com/fr-fr/training/modules/get-data/media/4-get-data-cosmos-ssm.png)

    - *NB: Dans la fenêtre* **Connecteur en préversion** *, sélection* **Continuer**
        - *Introduire les informations d’identification de la base de données.*
        - *Introduire les détails de la base de données.* 
        - *Spécifier l’URL du point de terminaison du compte Azure Cosmos DB à partir duquel on obtient les données (Possibilité d'obtenir l’URL dans le panneau Clés du portail Azure).*
        - *Ou alors introduire le nom de la base de données, le nom de la collection, ou utiliser le navigateur pour sélectionner la base de données et la collection afin d’identifier la source de données.*
        - ***Si une premiere connection introduire la clé du compte. ette clé se trouve dans la zone Clé principale du panneau Clés en lecture seule de votre Portail Azure.***
2. **Importation d'un fichier JSON**
    - Les enregistrements de type JSON doivent être extraits et normalisés avant de pouvoir produire des rapports à partir de ceux-ci : ***il faut donc transformer les données avant de les charger dans Power BI Desktop.***
    - Une fois que connecté au compte de base de données, la fenêtre  **Navigateur** s’ouvre et affiche la liste des bases de données sous ce compte. 
        - Sélection de la table que l'ont souhaite importer. 
            - Le volet de visualisation montre seulement les éléments **Enregistrement**, car tous les enregistrements du document sont représentés en tant que type Enregistrement dans Power BI.
        ![](https://learn.microsoft.com/fr-fr/training/modules/get-data/media/4-cosmos-navigator-ss.png#lightbox)

        - Click sur **Modifier** pour ouvrir les enregistrements dans Power Query.
            - Dans Power Query:
                - Bouton **Développeur** sur le côté droit de l’en-tête **Colonne1**, ce qui affichera le menu contextuel avec une liste de champs. 
                    - Sélection des champs à charger dans Power BI Desktop, décoche de la case **Utiliser le nom de la colonne d’origine comme préfixe**, puis **OK**.
                ![](https://learn.microsoft.com/fr-fr/training/modules/get-data/media/4-expand-record-ssm.png#lightbox)

                - Vérification des données sélectionnées pour etre sur qu’elles conviennent, puis sélection **Fermer et appliquer** pour charger les données dans Power BI Desktop.

                ![](https://learn.microsoft.com/fr-fr/training/modules/get-data/media/4-cosmos-results-ssm.png)

                - Les données de Cosmos DB peuvent maintenant être liées à des données provenant d’autres sources de données et être finalement utilisées dans un rapport Power BI.

#### Obtenir des données de services en ligne

- Power BI peut combiner les données de plusieurs applications logiciel pour produire des [insights](https://learn.microsoft.com/fr-fr/power-bi/create-reports/insights) et des rapports plus significatifs.
    - SharePoint
    - OneDrive 
    - Dynamics 365 
    - Google Analytics
    - etc...
1. **Se connecter aux données d’une application**
    - Selection de la fonction **Obtenir les données** => **service en ligne** => ...
2. **Choisir les données d'application à importer** 
    - Une fois que Power BI a établi la connexion, la fenêtre **Navigateur** apparaît, comme c’est le cas pour d’autres sources de données. La fenêtre affiche les tables et les entités. 
        - Sélection de la liste à charger dans Power BI Desktop. 
        - Option **charger** automatiquement les données dans le modèle Power BI ou **transformer vos données** avant de les charger.
    ![](https://learn.microsoft.com/fr-fr/training/modules/get-data/media/5-navigator-window-view-tables-ss.png#lightbox)

#### Selection d'un mode de stockage
[Voir Doc](https://learn.microsoft.com/fr-fr/power-bi/transform-model/desktop-storage-mode)
- Il y a trois types de mode de stockage :
    1. Importer
    2. DirectQuery
    3. Double (Composite)
- On accede aux modes de stockage en passant à la vue **MOdele**, selection d'une table de données, dans le volet **Proppriété**, selection du mode sohaitédans la liste déroulante **Mode de stockage**

![](https://learn.microsoft.com/fr-fr/training/modules/get-data/media/6-storage-mode-ssm.png#lightbox)

1. **Mode Importation** 
    - Le mode Importation permet de créer une copie Power BI locale des jeux de données à partir de la source de données. 
    - On peut utiliser toutes les fonctionnalités du service Power BI avec ce mode de stockage, y compris Questions et réponses et Quick Insights. 
    - Les actualisations de données peuvent être planifiées ou à la demande. 
    - ***C'est le mode par défaut pour la création de rapports Power BI.***
2. **Mode DirectQuery**
    - L’option DirectQuery est utile lorsque l'on ne souhaite pas enregistrer des copies locales des données, car les données ne seront pas mises en cache. Au lieu de cela, on peut interroger les tables spécifiques dont on souaite en utilisant des requêtes Power BI natives, et les données nécessaires seront récupérées auprès de la source de données sous-jacente. En fait, on crée une connexion directe à la source de données. 
    - L’utilisation de ce modèle garantit que l'on est toujours les données les plus récentes et que toutes les exigences de sécurité sont satisfaites. 
    - ***Ce mode convient lorsue l'on a des gros jeux de données d’où on doit extraire des données. Au lieu de ralentir les performances en chargeant de grandes quantités de données dans Power BI, on peut utiliser DirectQuery pour créer une connexion à la source et résoudre ainsi les problèmes de latence des données.              
3. **Mode Double (Mode Composite)**
    - En mode Double permet indiquer que certaines données doivent être importées directement et que d’autres doivent faire l’objet d’une requête. 
    - Toute table introduite dans le rapport est un produit à la fois du mode Importation et du mode DirectQuery. 
    - ***L’utilisation du mode Double permet à Power BI de choisir la forme de récupération de données la plus efficace.***

#### Se connecter aux donner d'Azure Analysis Service
[Voir doc](https://learn.microsoft.com/fr-fr/azure/analysis-services/analysis-services-connect-pbi)
- Azure Analysis Services permet d’ingérer des données provenant de plusieurs sources de données, de créer des relations entre les données et de créer des calculs sur les données. 
    - Les calculs sont créés avec des expressions **DAX (Data Analysis Expressions)**.
    - Il est est similaire à la technologie de modélisation et de stockage des données de Power BI.
- L’obtention de données depuis des cubes Azure Analysis Services cubes est similaire à l’obtention de données depuis **SQL Server**, dans la mesure où vous pouvez :
    - Vous authentifier auprès du serveur.
    - Sélectionner le cube que vous voulez utiliser.
    - Sélectionner les tables dont vous avez besoin.
- ***NB : Les différences notables entre les cubes Azure Analysis Services et SQL Server sont les suivantes :***
    - ***Les cubes Analysis Services intègrent déjà des calculs.***
    - ***Lorsque l'on a pas besoin de la totalité d’une table, on peut interroger les données directement.*** 
        - ***Au lieu d’utiliser Transact-SQL (T-SQL) pour interroger les données, comme on le ferait dans SQL Server,on peut utiliser des expressions MDX (Multidimensional Expressions) ou DAX (Data Analysis Expressions).***
1. **Se connecter à des données dans Azure Analysis Services**
    - Fonction **Obtenir des données** => Selection **Analsis Services**
    - Introduction de l’adresse du serveur et le nom de la base de données
        - Deux option: 
            1. **Importer**
            2. **Connexion directe**
                ```
                    Connexion directe est une nouvelle option d’Azure Analysis Services. 
                    Azure Analysis Services utilise le modèle tabulaire et DAX pour créer des calculs, d’une façon similaire à Power BI. 
                    Ces modèles sont compatibles les uns avec les autres. L’utilisation de l’option Connexion directe vous permet de conserver les données et les calculs DAX à leur emplacement d’origine, sans devoir les importer dans Power BI.
                    Azure Analysis Services peut avoir une planification d’actualisation rapide, ce qui signifie que quand les données sont actualisées dans le service, les rapports Power BI sont immédiatement mis à jour, sans qu’il soit nécessaire de lancer une planification d’actualisation Power BI. 
                    Ce processus peut améliorer le caractère à jour des données dans le rapport.
                ```
    ![](https://learn.microsoft.com/fr-fr/training/modules/get-data/media/7-analysis-services-connection-ss.png)

**NB:** ***Une alternative acceptable est d’importer toutes les autres données souhaitées (depuis Excel, SQL Server, etc.) dans le modèle Azure Analysis Services, puis à utiliser une connexion active. Avec cette approche, la modélisation des données et les mesures DAX sont toutes effectuées à un même emplacement, et il s’agit d’un moyen beaucoup plus simple et plus facile de gérer les solution***

#### Résoudre les problèmes de performances
- Power BI fournit l’outil Analyseur de performances pour aider à résoudre les problèmes et à rationaliser le processus.
    - Par exemple 
        ```
            Quand lorsque l'on crée des visuels et des filtres préliminaires, et que l'on remarque que l’interrogation de certaines tables est plus rapide que pour d’autres, et que certains filtres prennent plus de temps à être traités que d’autres filtres.
        ```
1. **Optimisation des performances dans Power Query**
    - Les performances de Power Query dépendent des performances au niveau de la source de données. La variété de sources de données offertes par Power Query est très grande et les techniques d’optimisation des performances pour chaque source sont également très variées. 
        - Exemple 
        ```
            Si on extrait des données d’un serveur Microsoft SQL Server, on doit suivre les instructions d’optimisation des performances pour le produit. Les bonnes techniques d’optimisation des performances de SQL Server incluent la création d’index, les mises à niveau du matériel, l’optimisation des plans d’exécution et la compression des données.
        ```
    - Power Query tire parti des bonnes performances de la source de données via une technique appelée « **Query Folding** ».
2. **Query Folding**
- [Voir Doc  Aide sur le Query Folding ](https://learn.microsoft.com/fr-fr/power-bi/guidance/power-query-folding) et [Doc Query Folding](https://learn.microsoft.com/fr-fr/power-query/power-query-folding)

    - Le Query Folding est le processus par lequel les transformations et les modifications que l'on apporte dans l’éditeur Power Query sont suivies simultanément en tant que requêtes natives, ou en tant que simples instructions SQL Select, pendant que l'on effectue activement des transformations. La raison de l’implémentation de ce processus est de garantir que ces transformations peuvent avoir lieu dans le serveur de la source de données d’origine et ne pas surcharger les ressources informatiques de Power BI.
    - ***On peut utiliser Power Query pour charger des données dans Power BI. Avec l’éditeur Power Query, on peut ensuite effectuer des transformations sur les données, comme renommer ou supprimer des colonnes, ajouter, décomposer, filtrer ou regrouper les données.***
        ```
            Imaginons un scénario où on a renommé quelques colonnes dans les données des ventes, et où on a fusionné une colonne Ville et Département selon un format « Ville Département ». Pendant cette opération, la fonctionnalité Query Folding effectue le suivi de ces modifications dans les requêtes natives. Ensuite, quand on charge les données, les transformations s’effectuent indépendamment dans la source d’origine, ce qui garantit l’optimisation des performances dans Power BI.
        ```
    - **Les avantages du Query Folding :**
        1. ***Plus d’efficacité dans l’actualisation des données et les actualisations incrémentielles.***
            - Quand on importe des tables de données en utilisant le Query Folding, Power BI est plus à même d’allouer des ressources et d’actualiser les données plus rapidement, car Power BI n’a pas besoin d’exécuter chaque transformation localement.
        2. ***Compatibilité automatique avec les modes de stockage DirectQuery et Double.***
            - Toutes les sources de données en mode de stockage DirectQuery et Double doivent avoir les capacités de traitement du serveur back-end pour créer une connexion directe, ce qui signifie que Query Folding est une fonctionnalité automatique que l'on peut utiliser. Si toutes les transformations peuvent être réduites à une seule instruction Select, le Query Folding peut être effectué.
        
    - ***Le scénario suivant montre le Query Folding en action. Dans ce scénario, on applique un ensemble de requêtes à plusieurs tables. Une fois que l'on a ajouté une nouvelle source de données avec Power Query et que l'on est dirigé vers l’éditeur Power Query, on accéde au volet*** **Paramètres de la requête*****, où on peut cliquer avec le bouton droit sur la dernière étape appliquée, comme illustré dans la figure ci-dessous.***

    ![](https://learn.microsoft.com/fr-fr/training/modules/get-data/media/8-view-native-query-ss.png)

    - ***Si l’option*** **Afficher la requête native** ***n’est pas disponible (non affichée en gras), le Query Folding n’est pas possible pour cette étape. Il faut alors revenir en arrière dans*** **Étapes appliquées** ***jusqu’à l’étape où*** **Afficher la requête native** ***est disponible (affichée en gras). Ce processus va révéler la requête native utilisée pour transformer le jeu de données.***
        - NB: Les requêtes natives ne sont pas possibles pour les transformations suivantes :
            - Ajout d’une colonne d’index
            - Fusion et ajout de colonnes de différentes tables avec deux sources différentes
            - Modification du type de données d’une colonne
    -   ```
            Une bonne règle à mémoriser est que si on peut traduire une transformation en une instruction SQL Select qui comprend des opérateurs et des clauses comme GROUP BY, SORT BY, WHERE, UNION ALL et JOIN, il faut utiliser le Query Folding.
        ```
    - Si le Query Folding est une option permettant d’optimiser les performances lors de la récupération, de l’importation et de la préparation des données, une autre option est d’effectuer des **diagnostics de requête**.

3. **Diagnostics de requête**  
    - Cette fonctionnalité permet de déterminer les goulots d’étranglement (le cas échéant) qui se produisent lors du chargement et de la transformation de vos données, lors de l’actualisation de vos données dans Power Query, lors de l’exécution des instructions SQL dans l’éditeur de requête, etc.
    - Pour accéder aux diagnostics de requête dans l’éditeur Power Query, 
        - **Aceuil** => **Outils**. 
            - Lorsqu'on est prêt à commencer la transformation des données ou à effectuer d’autres modifications dans l’éditeur Power Query, on sélectionne **Démarrer les diagnostics** dans la section **Diagnostics de la session**. 
                - Une fois terminer => **Arrêter les diagnostics**.

        ![](https://learn.microsoft.com/fr-fr/training/modules/get-data/media/8-navigating-query-diagnostics-ss.png)
    
    - La sélection de Diagnostiquer l’étape vous montre la durée nécessaire à l’exécution de cette étape

    ![](https://learn.microsoft.com/fr-fr/training/modules/get-data/media/8-applying-query-diagnostics-ss.png)

    - ***Cette sélection peut vous indiquer si une étape prend plus de temps que d’autres, ce qui sert ensuite de point de départ pour un examen plus approfondi.***
    ```
        Cet outil est pratique quand vous voulez analyser les performances du côté Power Query pour des tâches comme le chargement de jeux de données, l’exécution d’actualisations de données ou l’exécution d’autres tâches de transformation.
    ```
#### Autres techniques pour optimiser les performances 

- ***Traiter autant de données que possible dans la source de données d’origine*** *Power Query et l’éditeur Power Query permettent de traiter les données ; cependant, la puissance de traitement nécessaire pour effectuer cette tâche peut réduire les performances pour d’autres aspects du rapports.*
- ***Utiliser des requêtes SQL natives*** *Quand on utilise **DirectQuery** pour des bases de données SQL, on veuille à ne pas extraire des données de procédures stockées ou d’expressions de table communes.*
- ***Séparer la date et l’heure si elles sont stockées ensemble.*** *Si les tables ont des colonnes qui combinent la date et l’heure, il faut les séparer en colonnes distinctes avant de les importer dans Power BI. Cette approche augmente les capacités de compression.*

#### Résoudre les erreurs d’importation de données