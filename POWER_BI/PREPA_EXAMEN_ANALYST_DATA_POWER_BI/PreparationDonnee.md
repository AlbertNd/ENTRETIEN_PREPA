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
            Si on change un chemin de fichier, il faut veiller à se reconnecter au même fichier avec la même structure de fichier. Toute modification structurelle apportée à un fichier, comme la suppression ou le renommage des colonnes dans le fichier source, interrompt le bon fonctionnement du modèle de génération de rapports.
        ```
#### Obtention des données de sources de données relationnelles 