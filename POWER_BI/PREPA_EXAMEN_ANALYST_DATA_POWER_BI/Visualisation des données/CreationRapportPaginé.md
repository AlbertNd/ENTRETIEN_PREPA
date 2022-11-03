# Créer des rapport paginés 
- Les rapports paginés permettent aux développeurs de rapports de créer des artefacts Power BI ayant des exigences de rendu étroitement contrôlées. 
    - Les rapports paginés sont idéaux pour créer:
        - Des factures de ventes, 
        - Des reçus, 
        - Des bons de commande 
        - Des données tabulaires. 
- Les rapports paginés offrent une vue en pixel parfait des données. 
    - Le pixel parfait signifie que on a un contrôle total sur le mode de rendu du rapport. 
        - *Si on souhaite un pied de page sur chaque reçu de vente qu'on crée, un rapport paginé est la solution appropriée.*
        - *Si on souhaite qu’un certain nom de client apparaisse toujours en vert dans un rapport, on peut le faire dans un rapport paginé.*

```
Les rapports paginés Power BI sont des descendants de SQL Server Reporting Services (SSRS), Les rapports paginés Power BI
et SSRS ont beaucoup de choses en commun. 
Si on recherche des informations sur des rapports paginés, la recherche sur Internet et dans la documentation Microsoft 
sur SSRS est une excellente idée, car on y trouvere de nombreux billets de blog, vidéos et documentation.
```
![](https://learn.microsoft.com/fr-fr/training/modules/create-paginated-reports-power-bi/media/04-power-bi-report-builder-ssm.png)

- On peut utiliser des rapports paginés pour des rapports opérationnels avec des tables de détails et des en-têtes et pieds de page facultatifs.
- utiliser des rapports paginés lorsque on prévoit d’imprimer le rapport sur un papier ou lorsque on souhaite recevoir un reçu électronique, un bon de commande ou une facture. 
    - Les rapports paginés affichent également les données tabulaires plus facilement. On peut avoir des ordres de tri personnalisés, des en-têtes interactifs et des URL dans les résultats, ce qui permet une intégration simple avec les applications personnalisées.
- Les rapports paginés Power BI peuvent également afficher toutes les données dans un seul élément de rapport, tel qu’une table. 
    - Si on a 25 000 enregistrements et que on souhaite que les rapports s’impriment sur 100 pages, on peut le faire. 
    - Si on souhaite imprimer chaque troisième enregistrement avec un arrière-plan rose clair, on peut également le faire.
- **Les rapports paginés Power BI ne sont pas créés dans Power BI Desktop ; ils sont générés à l’aide du Générateur de rapports Power BI.** 
    - ***Les rapports paginés Power BI sont une fonctionnalité de Power BI Premium.***

#### Obtenir des données
- La première étape de création d'un rapport consiste à obtenir des données d’une source de données. 
    - ***Les rapports paginés Power BI n’utilisent pas Power Query lors de la connexion à des sources de données.***
    - ***L’obtention de données dans un rapport paginé Power BI n’implique pas les étapes de nettoyage des données.***
    - ***Les données ne sont pas stockées dans un jeu de données du rapport paginé Power BI.*** 
        - *Lorsque les données sont actualisées dans le rapport, elles sont récupérées dans un formulaire non modifié à partir de la source de données, en fonction de la requête qui a été utilisée pour la récupérer.*
- **Les données peuvent être collectées à partir de plusieurs sources de données, Excel, Oracle, SQL Server...** 
    - ***Une fois les données collectées, les différentes sources de données ne peuvent pas être fusionnées dans un modèle de données unique.*** 
        - *Chaque source doit être utilisée à des fins différentes.* 
            - *Par exemple : les données d’une source Excel peuvent être utilisées pour un graphique, tandis que les données SQL Server peuvent être utilisées pour une table sur un rapport unique.* 
- Les rapports paginés ont un langage d’expression qui peut être utilisé pour rechercher des données dans différents jeux de données, mais ne ressemblent en rien à Power Query.

- **Les rapports paginés Power BI peuvent utiliser un jeu de données à partir du service Power BI.**
    - ***Ces jeux de données ont utilisé Power Query pour nettoyer et modifier les données.*** 
        - *La différence est que ce travail a été effectué dans Power BI Desktop ou SQL Server Data Tools avant l’utilisation du Générateur de rapports Power BI, qui n’a pas cet outil dans l’interface utilisateur.*
1. **Créer et configurer une source de données**
    - Pour recuperer des données:
        1. Ouvir le generateur de rapports Power BI 
        2. Dans l'ecran **Prise en mais**
            - Selection **Nouveau rapport** 
        3. On peut choisir de creer un rapport avec :
            - Une table 
            - Un graphique 
            - Un rapport vide 
    - Un rapport vide permet de creer un visuel par défaut sur un nouveau rapport qui ^eut etre modifier à tout momment. 
        4. Accès à la fenetre **Données de rapport** 
            - *(Le fenetre se trouve generalement sur le coté gauche de l'outil, mais peut etre déplacer)*
        5. Click droit sur le dossier **Source de données** => **Ajouter une source de données**
        6. Sous l'onglet **Général** : On nomme la source de données 

        ![](https://learn.microsoft.com/fr-fr/training/modules/create-paginated-reports-power-bi/media/04-add-data-source-part-1-ssm.png)

        7. Choix de la connexion appropriée => selection **Générer**

        ![](https://learn.microsoft.com/fr-fr/training/modules/create-paginated-reports-power-bi/media/04-data-source-properties-build-button-ssm.png)

        8. **Propriété de la connexion**
            - Les propriétés sont uniques pour chaque source de données.
            - Ci-dessous propriétés d'une connexion **SQL Server**

            ![](https://learn.microsoft.com/fr-fr/training/modules/create-paginated-reports-power-bi/media/04-connection-properties-ssm.png)

            1. *Nom du serveur*
            2. *Nom de la base de données*
            3. *Un bouton pour tester la connexion*
            4. *OK pour continuer*
2. **Créer et configurer un jeu de données**
    - ***Une source de données représente les informations de connexion à une ressource particulière, comme SQL Server.***
    - ***Un jeu de données correspond aux informations de la requête enregistrées par rapport à la source de données et non aux données.***
    - ***Les données résident toujours à leur emplacement d’origine.***
    1. => Dans la fenetre **Affichage du rapport** => Selection ***Ajouter  un jeu de données**
        - Bien verifer que la source de données correcte est bien celle qui est selectionner.
    2. Dans la fentre qui s'affice: 
        1. On nommer la requête
        2. On choisi l’utilisation d’une commande de texte ou d’une procédure stockée
        3. On introduit une requête dans la zone de texte.

        ![](https://learn.microsoft.com/fr-fr/training/modules/create-paginated-reports-power-bi/media/04-dataset-properties-ssm.png)

#### Création d'un rapport paginé
- Pour créer un rapport, il faut ajouter un visuel à la surface de conception, de la même façon qu'on le ferait dans Power BI Desktop. 
    - => Sélection de l’onglet **Insérer** pour consulter les options permettant d’ajouter un visuel

    ![](https://learn.microsoft.com/fr-fr/training/modules/create-paginated-reports-power-bi/media/04-insert-tab-ss.png#lightbox)

    - **Pour une visuel de table**
        - Lorsqu'on selectionne le menu derolant **Table**, on peut choisir deux options: 
            1. **Inserer une table**
            2. **Assistant de table**
        1. Selction **Inserer une table** 

        ![](https://learn.microsoft.com/fr-fr/training/modules/create-paginated-reports-power-bi/media/04-insert-a-table-ss.png)

        2. On dessine une table sur la surface de conception 
        3. Depuis la fenetre **Données du rapport**, on fait glisser les champs du jeu de données vers la table sur la surface de conception.

        ![](https://learn.microsoft.com/fr-fr/training/modules/create-paginated-reports-power-bi/media/04-add-fields-ss.png)

        