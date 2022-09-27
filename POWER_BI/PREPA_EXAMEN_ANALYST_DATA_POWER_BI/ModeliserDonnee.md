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
```
    Supposons que l'on veuille élaborez des rapports pour l’équipe commerciale de l'entreprise.
    La base de données contient des tables pour les ventes, les commandes, les produits, etc. 
    Et on remarque que la plupart de ces tables, dont les tables Ventes et Commandes, contiennent
    leurs propres colonnes de dates, comme les colonnes DateExpédition et DateCommande des tables
    Ventes et Commandes. On est chargé de créer une table contenant le total des ventes et des
    commandes par année et par mois. Comment s'y prendre pour créer un visuel avec plusieurs
    tables, chacune faisant référence à ses propres colonnes de dates ? 

     => On crée une table de dates commune qui pourra être utilisée par plusieurs tables.

```
![](https://learn.microsoft.com/fr-fr/training/modules/design-model-power-bi/media/03-data-model-excerpt-ssm.png)

#### Créeation d'une table de dates commune
- Les moyens disponible pour créer une table de date commune: 
    1. Données source 
    2. DAX
    3. Power Query

1. **Données sources** 
    - Parfois, les bases de données sources et les entrepôts de données ont déjà leurs propres tables de dates. Si l’administrateur qui a conçu la base de données a fait un travail consciencieux, ces tables peuvent être utilisées pour effectuer les tâches suivantes :
        - Identifier les jours de fermeture de la société
        - Séparer l’année civile et l’année fiscale
        - Identifier les week-ends et les jours de la semaine
    - *Si les tables de données sources sont abouties et prêtes à être utilisées immédiatement, on l'intégre au modèle de données et on n’utilise pas les autres méthodes. Il est recommandé d’utiliser une table de dates source, car elle est probablement partagée avec d’autres outils qu'on utilise peut-être en plus de Power BI.*
2. **DAX** 
    - Il est possible d'utiliser les fonctions DAX **CALENDAR()** ou **CALENDARAUTO()** pour gerer la table de date commune.
        - **CALENDAR()**: 
            - Elle retourne une plage de dates voisines basée sur des dates de début et de fin entrées sous forme d’**arguments dans la fonction**.
        - **CALENDARAUTO()**: 
            - Elle peut aussi retourner une plage des dates voisines et complète de dates qui sont automatiquement déterminées à partir de votre jeu de données. *(La date de début choisie correspond à la date la plus ancienne dans le jeu de données, et la date de fin est la date la plus récente dans le jeu de données)*
            - Il aussi possible de choisir d’inclure les données qui ont été remplies au **titre du mois fiscal** comme argument de la fonction **CALENDARAUTO()**.
    - Dans **Power BI Desktop** => l’**onglet Table** sur le ruban => Sélection **Nouvelle table** => la formule DAX suivante :

    ![](https://learn.microsoft.com/fr-fr/training/modules/design-model-power-bi/media/03-dax-function-calendar-auto-01-ss.png)

    - ***La fonction **CALENDAR()** a est utilisée, car le but est d’afficher uniquement les données sur 10 ans à compter du 31 mai 2011.***

    - Si on souhaite recuperer les colonnes pour l’**année** uniquement, le **numéro du mois**, la **semaine de l’année** et le **jour de la semaine**. 
        - => sélection **Nouvelle colonne** sur le ruban => équation DAX *(qui récupère l’année dans la table Date.)*

        ![](https://learn.microsoft.com/fr-fr/training/modules/design-model-power-bi/media/03-adding-columns-dax.png)

        - => sélection **Nouvelle colonne** sur le ruban => équation DAX *(qui récupère le mois dans la table Date.)*
            - `MonthNum = MONTH(Dates[Date])`
        - => sélection **Nouvelle colonne** sur le ruban => équation DAX *(qui récupère le numero de la semaine dans la table Date.)*
            - `WeekNum = WEEKNUM(Dates[Date])`
        - => sélection **Nouvelle colonne** sur le ruban => équation DAX *(qui récupère le jour de la semaine dans la table Date.)*
            - `DayoftheWeek = FORMAT(Dates[Date], "DDDD")`

        ![](https://learn.microsoft.com/fr-fr/training/modules/design-model-power-bi/media/03-final-columns-dax-table-2-ss.png)

        - ***Une table de dates commune est créée avec DAX. Ce processus ne fait qu’ajouter une nouvelle table au modèle de données ; il reste encore à **établir des relations entre la table de dates et les tables Ventes et Commandes**, puis à **marquer la table comme étant la table de dates officielle** du modèle de données.***
3. **Power Query**
- Il est possible d'utiliser le langage de **développement M**, qui permet de créer des requêtes dans **Power Query** en vue de définir une table de données commune.
    - Selection **Transformer les données** dans **Power BI Desktop** => **Power Query** => dans l'espace vide du volet **Requetes** de gauche => Click bouton droit => menu deroulant => selection **Nouvelle requete** => **Requete vide**

    ![](https://learn.microsoft.com/fr-fr/training/modules/design-model-power-bi/media/03-new-query-common-date-table-03-ss.png)

    - Dans la vue **Nouvelle requête** qui s’affiche, on entre la **formule M** suivante pour créer une table de calendrier :
        - `= List.Dates(#date(2011,05,31), 365*10, #duration(1,0,0,0))`

        ![](https://learn.microsoft.com/fr-fr/training/modules/design-model-power-bi/media/03-m-query-common-data-table-04-ss.png)

        - *Pour les données de vente, la date de début doit ici correspondre à la date la plus ancienne dans les données : le 31 mai 2011. On souhaite également afficher les dates pour les 11 prochaines années, notamment les dates dans le future. À mesure que les nouvelles données de ventes afflueront, on n’aura pas besoin de recréer cette table. Il est également possible de changer la durée. Dans ce cas, on veut un point de données pour chaque jour, mais il est également possible de définir des incréments par heures, minutes et secondes.*

        ![](https://learn.microsoft.com/fr-fr/training/modules/design-model-power-bi/media/03-list-power-query-11-ss.png)

        - Ici on remarquera que les dates se présentent sous la forme d’une **liste** et non d’une table. Pour corriger cette erreur: l’**onglet Transformer** sur le ruban => sélection **Convertir** => **Dans une table**. Comme le nom l’indique, cette fonctionnalité convertit la liste en table. Il est aussi possible de renommer la colonne ColDate.

        ![](https://learn.microsoft.com/fr-fr/training/modules/design-model-power-bi/media/03-converting-list-table-05-ssm.png)

        - Si souhaite ajouter des colonnes à la nouvelle table pour afficher les dates par **année**, **mois**, **semaine** et **jour** de façon à pouvoir établir une hiérarchie dans le visuel. 
            - => **Changer le type de colonne**. 
                - Sélection **icône en regard du nom de la colonne** => dans le menu déroulant => sélection **Date**.

            ![](https://learn.microsoft.com/fr-fr/training/modules/design-model-power-bi/media/03-change-type-date-3-ss.png)

            - **Ajout des colonnes pour l’année, les mois, les semaines et les jours**
                - => **Ajouter une colonne** => menu déroulant en dessous de **Date** => sélection **Année**

            ![](https://learn.microsoft.com/fr-fr/training/modules/design-model-power-bi/media/03-adding-columns-power-query-5-ss.png)

            ![](https://learn.microsoft.com/fr-fr/training/modules/design-model-power-bi/media/03-adding-columns-table-power-query-6-ss.png)

            ![](https://learn.microsoft.com/fr-fr/training/modules/design-model-power-bi/media/03-final-columns-using-power-query-7-ss.png)

#### Marquer comme table de dates officielle
-  Table dans le **volet Champs** => Click droit sur le nom de la table => sélectionn **Marquer comme table de dates**. 

![](https://learn.microsoft.com/fr-fr/training/modules/design-model-power-bi/media/03-mark-date-table-06-ss.png)

- Ainsi , Power BI effectue des validations pour vérifier que les données ne comportent pas de valeurs null, qu’elles sont uniques et qu’elles contiennent des valeurs de date sur une période.

- Il aussi possible de choisir de marquer certaines colonnes de la table en tant que date, ce qui peut s’avérer utile quand la table compte un grand nombre de colonnes. 
    - Click droit sur la table => sélection **Marquer comme table de dates** => sélection **Paramètres de la table de dates** => choisir la colonne qui doit être marquée comme Date.

![](https://learn.microsoft.com/fr-fr/training/modules/design-model-power-bi/media/03-mark-date-table-07-ss.png#lightbox)

- **NB:** *Si on sélectionne **Marquer comme table de dates**, on supprime les **hiérarchies** générées automatiquement du champ Date de la table que on a marqué comme table de dates. Pour les autres champs de date, la hiérarchie automatique reste présente tant que on n’établit pas de relation entre ce champ et la table de dates ou que on ne désactive pas la fonctionnalité **Date/heure automatique**. On peut ajouter manuellement une hiérarchie à la table de dates commune en cliquant avec le bouton droit sur les colonnes année, mois, semaine ou jour dans le volet Champs, puis en sélectionnant Nouvelle hiérarchie.* 

#### Création du visuel 
- Pour créer le visuel entre les tables Ventes et Commandes, il faut établir une relation entre cette nouvelle table de dates commune et les tables Ventes et Commandes. On pourrait ainsi créer des visuels en utilisant la nouvelle table de dates. 
    - **Onglet Modèle** de modèle => **Gérer les relations** *(où on peut créer des relations entre la table de dates commune et les tables Commandes et Ventes en utilisant la colonne DateCommande)*.

![](https://learn.microsoft.com/fr-fr/training/modules/design-model-power-bi/media/03-create-relationship-8-ss.png)

- Une fois les relations créée, on peut générer le visuel **Total des ventes et quantité commandée par période** avec la table de **dates commune** élaborées à l’aide de la méthode **DAX** ou **Power Query**. 
    - Pour déterminer le total des ventes, il faut ajouter toutes les ventes, car la colonne Quantité de la table Ventes considère uniquement la recette de chaque vente, et non le chiffre d’affaires total. 
        - Utilisez du calcul de mesure
            - `#Total Sales = SUM(Sales[‘Amount’])`
    - Une fois terminé, on peut créer une table en retournant sous l’**onglet Visualisations** et en sélectionnant le **visuel Table**. Si on souhaite afficher le total des commandes et des ventes par année et mois, on inclue uniquement les colonnes Année et Mois de votre table de dates, la colonne **QtéCommandée** et la mesure **#TotalVentes**. Dans la section consacrée aux hiérarchies, il est également possible d’établir une hiérarchie pour une exploration au niveau du détail, de l’année au mois.

    ![](https://learn.microsoft.com/fr-fr/training/modules/design-model-power-bi/media/03-common-date-dax-5-ss.png)