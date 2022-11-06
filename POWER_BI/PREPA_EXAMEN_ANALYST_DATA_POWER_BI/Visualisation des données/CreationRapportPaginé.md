# Créer des rapport paginés 

[Voir doc](https://learn.microsoft.com/fr-fr/power-bi/paginated-reports/paginated-reports-enter-data)

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

        4. On note que le champs a ete rajouté à la partie inferieur de la tabl entre crochet. 
            - Il y a aussi une en-tete
            - On peut nommer ou appliquer une mise en forme aux en-tete. 
        5. On teste le rapport 
            - => **Acceuil** => **Exécuter** 

            ![](https://learn.microsoft.com/fr-fr/training/modules/create-paginated-reports-power-bi/media/04-run-button-ss.png)

            - ***Le rapport s’exécute et affiche les données réelles dans la table.***

            ![](https://learn.microsoft.com/fr-fr/training/modules/create-paginated-reports-power-bi/media/04-display-report-ss.png)

            - Certains éléments ont été modifiés dans le rapport : 
                - Un titre a été entré en haut, 
                - Les en-têtes de la table ont été renommés et sont affichés en gras 
                - Une couleur d’arrière-plan a été sélectionnée dans l’en-tête. 

    - Pour revenir à la surface de conception => **bouton Conception**.
    - Un autre aspect de la création d’un rapport consiste à ajouter un paramètre.
        - Lorsqu'on souhaite que l’utilisateur entre des informations qui s’affichent sur un visuel du rapport. 
            - La raison la plus courante pour ajouter un paramètre consiste à affecter les données extraites de la source de données.
                - *Par exemple si on souhaite crée un rapport qui récupère des données d’une base de données de ventes. et que l'on veut uniquement les données de ventes entre une date de début et une date de fin. Dans ce cas, on cree deux paramètres, puis on modifie la requête de jeu de données pour inclure ces paramètres dans la clause WHERE de la requête. La première étape de cette situation consiste à ajouter un paramètre.*
1. **Ajouter des paramètres**
    1. => Click droit sur **Parametres** => Selection **AJouter un parametres** 
    
    ![](https://learn.microsoft.com/fr-fr/training/modules/create-paginated-reports-power-bi/media/04-add-parameter-ssm.png)

    2. Sous l'onglet **General** => on nommer le parametres et on selectionne le type de donnée => Choix de l'invité que l'utilisateur verra. 

    ![](https://learn.microsoft.com/fr-fr/training/modules/create-paginated-reports-power-bi/media/04-report-parameter-properties-ssm.png)

    3. Sous l'onglet **Valeurs disponible** On introduit les options à partir desquelles l'utilisateur peux choisir. 
        - *L’onglet Valeurs par défaut a la valeur initiale du paramètre lors du chargement du rapport, mais il peut être modifié par l’utilisateur.*
        - IL est aussi possible d'obtenir des valeurs de paramètre à partir d’une requête. [Pour plus d'informations documentation Microsoft sur les paramètres.](https://learn.microsoft.com/fr-fr/power-bi/paginated-reports/paginated-reports-parameters)
    
    4. Une fois le paramatres crée : On peut l'utiliser pour interagir avec le rapport. 
        - Pour connecter le paramettre à la requetes => retour sur le jeu de donnée. 
        
        ![](https://learn.microsoft.com/fr-fr/training/modules/create-paginated-reports-power-bi/media/04-dataset-properties-parameter-ss.png)

        - *La référence de paramètre commence par le symbole **arobase (@)**.*
            - *On ajoute le nom du paramètre au texte de la requête. Et lorsque le rapport s’actualise, les données seront extraites de la source de données conformément à la **clause WHERE et à la valeur du paramètre**.*
#### Utiliser des graphiques sur le rapport
- Il existe deux facons d'ajouter un graphique au rapport.
    1. sélection du bouton **Graphique** => sélection **Insérer un graphique** => on dessine la table sur le canevas.

    ![](https://learn.microsoft.com/fr-fr/training/modules/create-paginated-reports-power-bi/media/04-insert-chart-ssm.png)

    2. Click droit sur le canevas durapport => selection **Inserer** => Selection **Graphique**

    ![](https://learn.microsoft.com/fr-fr/training/modules/create-paginated-reports-power-bi/media/04-insert-chart-2-ssm.png)

    - Choix du type et du styele du graphique 

    ![](https://learn.microsoft.com/fr-fr/training/modules/create-paginated-reports-power-bi/media/04-chart-type-ss.png)

    - Le graphique sera ajouter à la surface de conception 

    ![](https://learn.microsoft.com/fr-fr/training/modules/create-paginated-reports-power-bi/media/04-added-chart-ss.png)

    - ***Lorsqu'on sélection le graphique, une nouvelle fenêtre s’affiche à droite. L’écran **Données du graphique** permet de mettre en forme le graphique en fonction des valeurs et des propriétés de l’axe.***
    - On sélectionne le signe plus (+) à côté de chaque section pour sélectionner les colonnes requises.

    ![](https://learn.microsoft.com/fr-fr/training/modules/create-paginated-reports-power-bi/media/04-chart-sections-ss.png)

    - *Pour plus d’informations sur l’utilisation des graphiques, faure une recherche dans la documentation Microsoft sur les rapports SSRS. Toutes les informations contenues dans la documentation SSRS s’appliquent aux rapports paginés Power BI.*

#### Publier le rapport

[Voir Doc Publier des jeux de données et des rapports à partir de Power BI Desktop.](https://learn.microsoft.com/fr-fr/power-bi/create-reports/desktop-upload-desktop-files)


- => Selection **Fichier** => **Enregistrer sous** => Selection **Service Power Bi** le rapport s'affichera dans le service Power Bi 

![](https://learn.microsoft.com/fr-fr/training/modules/create-paginated-reports-power-bi/media/04-save-ss.png)

- **Meilleures pratiques**
    - La création d’un rapport a pour but d’informer et d’effectuer une action sur la partie de l’utilisateur du rapport. 
    - L’auteur du rapport doit toujours se poser plusieurs questions :
        - À quoi sert ce rapport ?
        - Qui utilise le rapport ?
        - Comment puis-je aider les utilisateurs à améliorer leurs tâches ?
        - Quelles sont les informations les plus importantes et comment puis-je les mettre en surbrillance ?
        - Ce rapport est-il lisible ?
        - Les utilisateurs peuvent-ils modifier les éléments dont ils ont besoin si leurs questions changent ?
        - Ai-je des éléments visuels qui gênent le message de base du rapport ?
        - Ce rapport se concentre-t-il sur une rubrique unique ou sur quelques rubriques seulement ?
        - Puis-je fournir toutes les informations que l’utilisateur s’attend à voir dans le rapport ?

    - *La création d’en-têtes et de pieds de page efficaces est un excellent moyen d’aider l’utilisateur à interpréter le rapport. ***on fournir une aide à l’utilisateur en documentant la raison pour laquelle ce rapport a été créé. L’ajout d’une date et d’une heure d’implémentation du rapport est une excellente pratique***. Parfois, les rapports sont exécutés, puis enregistrés. Les personnes qui consultent un rapport ne savent pas qu’elles cherchent une version antérieure, sauf si ce fait est mis en surbrillance dans un pied de page.*
    - *Cibler le rapport pour la région appropriée. Les conférenciers anglais lisent de haut en bas, de gauche à droite. Le fait de placer des informations importantes, tels que des totaux, en haut du rapport surligne ces informations pour les orateurs anglais. Les européens lisent les dates différemment par rapport aux utilisateurs des États-Unis. Localisez les formats de données sur l’utilisateur cible approprié.*
    - *En plus de se concentrer sur les aspects visuels du rapport, un auteur de rapport approprié prendra en compte la remise de rapports et l’utilisation de la source de données. Une bonne livraison est axée sur la façon dont l’utilisateur souhaite voir le rapport. Par conséquent, les auteurs de rapports doivent se poser les questions suivantes pour tester le format de remise approprié et vérifier que le rendu du rapport est correct dans ce format :
        - L’utilisateur souhaite-t-il lui envoyer le rapport dans un message électronique ?
        - L’utilisateur souhaite-t-il que le rapport soit dans un format imprimable ?
        - L’utilisateur lit-il le rapport dans un navigateur Web ?
    - *Bien faire attention à la hauteur et à la largeur de la page de rapport. Vérifier que le rapport ne s’exécute pas en dehors de la page lorsque le rapport s’affiche pour l’utilisateur.*
    - *Un bon auteur de rapports crée des rapports faciles sur la source de données. Si on continue à rappeler des données dont on n’a pas besoin à partir d’une source de données, on surcharge la source de données et on affecte les performances de manière imprévisible. En se concentrant uniquement sur l’obtention de données pertinentes, on pourrait être responsable des personnes qui utilisent les mêmes données.*

