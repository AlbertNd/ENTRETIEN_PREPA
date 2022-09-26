# Modéliser les données dans Power BI 

- Un bon modele de donnée offres les avantages suivants :
    1. L’exploration des données est plus rapide.
    2. Les agrégations sont plus simples à générer.
    3. Les rapports sont plus précis.
    4. La génération de rapports prend moins de temps.
    5. Les rapports sont plus faciles à gérer à l’avenir.

![](https://learn.microsoft.com/fr-fr/training/modules/design-model-power-bi/media/01-example-data-model-01-ss.png)

- ***Les zones contiennent des tables de données où chaque élément de ligne dans la zone est une colonne. Les lignes qui connectent les zones représentent les relations entre les tables. Ces relations peuvent être complexes, même dans le cas d’un modèle simpliste. Le modèle de données peut facilement se désorganiser, et le nombre total de tables dans le modèle peut augmenter progressivement.***

- Les relations sont définies entre les tables par le biais des clés primaires et étrangères en commun.:
    1. **clés primaires**:
        - Ce sont des colonnes qui identifient chaque ligne de données **unique et non-Null**.
        - Le processus est important lorsqu'on référence des lignes dans une table différente avec des clés étrangeres
    2. **clés étrangères**: 

#### Schémas en étoile

![](https://learn.microsoft.com/fr-fr/training/modules/design-model-power-bi/media/01-star-schema-example-01-ss.png)

1. **Tables de faits** 
    - Elles contiennent des **valeurs d’observation** ou des **valeurs de données d’événement**:
        - Commandes client
        - Nombre de produits 
        - Prix 
        - Dates et heures des transactions 
        - Quantités
    - Elles peuvent contenir plusieurs valeurs répétées.
        - *Un produit peut apparaître plusieurs fois dans plusieurs lignes, pour différents clients à des dates différentes*
    - Ces valeurs peuvent être agrégées pour créer des visuels
        - *un visuel du total des commandes est une agrégation de toutes les commandes de la table de faits. Dans les tables de faits, les colonnes sont couramment remplies avec des **nombres** et **des dates***
            - Les nombres peuvent être des unités de mesure, comme un montant de vente, ou bien des clés, comme un ID client. 
            - Les dates représentent la valeur de temps qui est enregistrée, comme la date de la commande ou la date d’expédition.
2. **Tables de dimension**
    - Elles contiennent les **détails des données** contenues dans les tables de faits:
        - Produits 
        - Emplacements 
        - Employés et 
        - Types de commandes
    - Ces tables sont connectées à la table de faits par le biais de colonnes clés. 
    - Elles sont utilisées pour **filtrer** et **regrouper les données** dans des **tables de faits**.
    - Elles contiennent des **valeurs uniques**,
        - *Par exemple une ligne pour chaque produit dans la table Products et une ligne pour chaque client dans la table Customer.*
    - NB: Pour le visuel des commandes totales, on peut regrouper les données de façon à voir les ventes totales par produit (le produit étant constitué de données dans la table de dimension).

- **NB:** Les tables de **faits sont généralement beaucoup plus grandes que les tables de dimension** dans la mesure où de **nombreux événements se produisent dans ces tables**, comme des ***ventes individuelles***. Les tables de **dimension sont généralement plus petites**, car on est limité au **nombre d’éléments qu'on peut filtrer et regrouper**. 
    - Par exemple, une année contient un nombre fixe de mois et les États-Unis sont constitués d’un certain nombre d’États. 

- **Exemple parlant** 

![](https://learn.microsoft.com/fr-fr/training/modules/design-model-power-bi/media/01-data-model-relationships-ss.png)

- Des données pertinentes se trouvent dans les deux tables, **Employé** et **Ventes**, .Étant donné que la **table Ventes** contient les **valeurs des commandes**, lesquelles **peuvent être agrégées**, elle sera considérée comme une **table de faits**. La **table Employés** contient le **nom des employés**, ce qui permet de **filtrer les commandes client**. Il s’agit donc d’une **table de dimension**. La colonne commune aux deux tables, qui est la **clé primaire** de la table Employés, est **IDEmployé**. On peut donc établir une relation entre les deux tables en fonction de cette colonne.

![](https://learn.microsoft.com/fr-fr/training/modules/design-model-power-bi/media/01-data-schema-example-04-ss.png)

#### Utilisation des tables 
- Avant de commencer à travailler sur la création de rapports, il est possible de simplifier le modèle de données et la structure des tables.
- Une structure de table simple :
    - Est simple à parcourir grâce à des propriétés de colonne et de table spécifiques et conviviales.
    - Comprend des tables qui ont été fusionnées ou ajoutées pour simplifier les tables dans la structure de données.
    - Présente des relations de bonne qualité et logiques entre les tables.
1. **Configuration de modèle de données et établissement des relations entre les tables**
    - En partant du principe ou on a déjà récupéré les données et qu'on les a nettoyées dans Power Query, on peut accéder à l’**onglet Modèle** où se trouve le modèle de données.

    ![](https://learn.microsoft.com/fr-fr/training/modules/design-model-power-bi/media/02-data-model-example-01-ssm.png)

    - Pour gérer ces relations => **Gérer les relations** dans le ruban.

    ![](https://learn.microsoft.com/fr-fr/training/modules/design-model-power-bi/media/02-manage-relationships-window-02-ss.png)

    - Il est possible de :
        - **Créer**, **modifier** et **supprimer** des relations entre les tables et **détecter automatiquement les relations existantes**.
            - *Lorsqu'on charge vos données dans Power BI, la fonctionnalité Détection automatique vous aide à établir des relations entre les colonnes nommées de façon similaire.
    - Les relations peuvent être **inactives** ou **actives**. ***Une seule relation active peut exister entre les tables***
#### Configuration des propriétés de table et de colonne
- La vue **Modèle** dans **Power BI Desktop** fournit de nombreuses options dans les propriétés de colonne que l'on peut consulter ou mettre à jour. Pour accéder à ce menu et mettre à jour les tables et les champs, le plus simple consiste à cliquer sur les **éléments de la page tout en maintenant la touche Ctrl ou Maj enfoncée**.

![](https://learn.microsoft.com/fr-fr/training/modules/design-model-power-bi/media/02-configure-properties-03-ss.png)

- Sous l’**onglet Général**, il est possible de :
    - Modifier le nom et la description de la colonne.
    - Ajouter des synonymes qui peuvent servir à identifier la colonne quand on utilise la fonctionnalité **Questions et réponses**.
    - Ajouter une colonne dans un dossier pour organiser davantage la structure de la table.
    - Masquer ou afficher la colonne.
- Sous l’**onglet Mise en forme**,il est possible de :
    - Changer le type de données.
    - Mettre en forme la date.
        - Sélection du menu déroulant sous **Tous les formats de date et d’heure**, puis choisir le format de date approprié.
    
        ![](https://learn.microsoft.com/fr-fr/training/modules/design-model-power-bi/media/02-change-date-format-05-ss.png)

- Sous l’**onglet Avancé**, il est possible de :
    - Trier les données en fonction d’une colonne spécifique.
    - Affecter une catégorie spécifique aux données.
    - Récapituler les données.
    - Déterminer si la colonne ou la table contient des valeurs Null.
- ***Power BI propose également une nouvelle fonctionnalité pour mettre à jour ces propriétés sur plusieurs tables et plusieurs champs. Pour cela, click sur les éléments en maintenant la touche Ctrl ou Maj enfoncée.***

#### Création d'un table de Dates
- Power BI détecte automatiquement les colonnes et les tables de dates. Mais dans certains cas, il peut être nécessaire de prendre des mesures supplémentaires pour adapter le format des dates.


