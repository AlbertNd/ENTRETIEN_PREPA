# PREPARATION DES DONNEES 

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
1. **Emplacement du fichier plat.**
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

2. **Se connecter aux données d'un fichier**

    ![](https://learn.microsoft.com/fr-fr/training/modules/get-data/media/2-get-data-excel-ssm.png)

    ![](https://learn.microsoft.com/fr-fr/training/modules/get-data/media/2-excel-save-data-ssm.png)

3. **Selection des données du fichier à importer**
    - Une fois le fichier connecté à Power BI Desktop, la fenêtre du Navigateur s’ouvre. 
        - Elle montre les données qui sont disponibles dans la source de données
        - Il est possible de sélectionner une table ou une entité pour afficher un aperçu de son contenu, pour vérifier que les données correctes sont chargées dans le modèle Power BI.

    - On coche la ou les cases à cocher de la ou des tables que l'on souhaite importer dans Power BI. Cette sélection active les boutons:
        - **Charger**: Charger automatiquement vos données dans le modèle Power BI 
        - **Transformer les données** : Lancer l’éditeur Power Query, pour passer en revue et nettoyer les données avant de les charger dans le modèle Power BI.
    ![](https://learn.microsoft.com/fr-fr/training/modules/get-data/media/2-excel-worksheet-ssm.png)

4. **Changer le fichier source** 
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