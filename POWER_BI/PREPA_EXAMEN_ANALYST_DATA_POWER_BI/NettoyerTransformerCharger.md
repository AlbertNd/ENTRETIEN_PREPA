# Nettoyage, transformation et chargement des données 
- Lorsque l'on importe des données et que l'on les analyse on recontre souvent plusieurs problemes qui peuvent rendre l'analyse incorect. 
    - Une colonne appelée **Employment status** contient seulement des nombres.
    - Plusieurs colonnes contiennent des erreurs.
    - Certaines colonnes contiennent des valeurs Null.
    - L’ID client apparaît dans certaines colonnes comme s’il était dupliqué de façon répétée.
    - Une même colonne d’adresse contient l’adresse postale, la ville, l’état et le code postal combinés.
    - ...
- Power BI et Power Query offrent un environnement puissant pour nettoyer et préparer les données.Les avantages des données propre: 
    - ***Les mesures et les colonnes produisent des résultats plus précis quand des calculs et des agrégations sont effectués sur celles-ci.***
    - ***Les tables sont organisées, où les utilisateurs peuvent trouver les données de façon intuitive.***
    - ***Les doublons sont supprimés, ce qui simplifie la navigation dans les données. Elles se traduisent aussi par des colonnes qui peuvent être utilisées dans des sélecteurs et des filtres.***
    - ***Une colonne complexe peut être fractionnée en deux colonnes plus simples. Plusieurs colonnes peuvent être combinées en une seule colonne pour des raisons de lisibilité.***
    - ***Les codes et les entiers peuvent être remplacés par des valeurs lisibles par les humains.***
#### Mise en forme des données initiales 
- L’éditeur Power Query de Power BI Desktop permet de mettre en forme (transformer) vos données importées:
    - Renommer des colonnes ou des tables, 
    - Changer du texte en nombre, 
    - Supprimer des lignes, 
    - Définir la première ligne comme en-tête, 
    - etc...

#### Bien demarrer avec l'editeur Power Query
[Voir Doc Information fonctionalité et fonction ruban](https://learn.microsoft.com/fr-fr/power-query/power-query-ui#the-query-ribbon)

- Onglet **Accueil** => **transformer les données** => **éditeur Power Query**

![](https://learn.microsoft.com/fr-fr/training/modules/clean-data-power-bi/media/02-open-query-editor-transform-button-ssm.png)

- Dans l’éditeur Power Query:
    - Toutes les étapes effectuées pour mettre en forme les données sont enregistrées. 
        - Chaque fois que la requête se connecte à la source de données, elle applique automatiquement les étapes : 
            - Les données sont toujours mises en forme selon ce que l'on a spécifié. 
    - Aucune modification n’est apportée à la source de données d’origine. 
    - On peut voir une liste des étapes sur le côté droit de l’écran, dans le volet  **Paramètres de la requête**, ainsi que les propriétés de la requête. 

#### Les étapes de mise en forme 

1. **Identification des en-tete et des noms de colonnes** 
    - ***La première étape de mise en forme des données initiales consiste à identifier les en-têtes et les noms des colonnes dans les données, puis à déterminer leur emplacement pour être sûr qu’ils se trouvent au bon endroit.***
2. **Promouvoir les en-têtes**
    - Quand une table est créée dans Power BI Desktop, l’éditeur Power Query suppose que toutes les données appartiennent aux lignes de la table. Cependant, une source de données peut avoir une première ligne qui contient les noms des colonnes. 
        - Pour corriger cette interprétation, il faut **promouvoir la première ligne de la table comme en-têtes de colonne.**
    - On peut promouvoir les entete de deux manieres:
        1. Onglet **Acceuil** => Option **Utiliser la premiere ligne comme entete**
        2. Selection du bouton de la liste deroulante en regard de colonne => Selection de l'option **Utiliser la premiere ligne pour les entete**

        ![](https://learn.microsoft.com/fr-fr/training/modules/clean-data-power-bi/media/02-use-first-row-headers-ssm.png)

        ![](https://learn.microsoft.com/fr-fr/training/modules/clean-data-power-bi/media/02-use-first-row-headers-result-ssm.png)

3. **Renommer les colonnes**
    - On peut constater qu’une ou plusieurs colonnes ont des en-têtes incorrects, qu’un en-tête contient une faute d’orthographe, ou que la convention de nommage des en-têtes n’est pas cohérente ou pas conviviale. 
    - On peut renommer les entete de colonne de deux manieres: 
        1. **Bouton droit sur l’en-tête** => sélection **Renommer** => **Entrée.**
        2. Double-cliquer sur l’en-tête de colonne et remplacer le nom par le nom correct. 
    - On peut aussi contourner ce problème en supprimant la premières lignes,et ensuite en renommant les colonnes avec le nom correct. 

4. **Suppression des lignes du haut**
    - Il peut être nécessaire de supprimer certaines lignes du haut, par exemple si elles sont vides ou si elles contiennent des données dont on a pas besoin dans les rapports. 
    - Pour supprimer ces lignes en trop, 
        - Onglet **Acceuil** => **Supprimer des lignes** => **Supprimer les lignes du haut**

        ![](https://learn.microsoft.com/fr-fr/training/modules/clean-data-power-bi/media/02-remove-top-rows-feature-ssm.png)

5. **Suppression des colonnes**
    - Une étape essentielle du processus de mise en forme des données consiste à supprimer les colonnes non nécessaires. Il est préférable de supprimer les colonnes le plus tôt possible. Une façon de supprimer des colonnes est d’ignorer des colonnes quand on récupére les données auprès de la source de données. 
        - Par exemple, si on extrait des données d’une base de données relationnelle en utilisant SQL, on peut ignorer des colonnes en ne les plaçant pas dans la liste de colonnes de l’instruction SELECT.
        - Il est toujours possible d'ajouter une colonne ultérieurement si les besoins évoluent dans le temps. 
    - On peut supprimer des colonnes de deux manières. 
        1. Sélection des colonnes à supprimer puis, sous l’onglet **Accueil** => **sélection Supprimer les colonnes.** 

        ![](https://learn.microsoft.com/fr-fr/training/modules/clean-data-power-bi/media/02-remove-columns-ssm.png)

        2. Sélection des colonnes à conserver puis, sous l’onglet **Accueil** => sélection **Supprimer les colonnes** => **Supprimer les autres colonnes**.

        ![](https://learn.microsoft.com/fr-fr/training/modules/clean-data-power-bi/media/02-remove-other-columsn-ssm.png)

6. **Dépivoter les colonnes**
    - à titre d'exemple: 
        - Donnée excel 
        
        ![](https://learn.microsoft.com/fr-fr/training/modules/clean-data-power-bi/media/02-excel-data-multiple-columns-ss.png)

        - Bien que les données puissent initialement avoir du sens, il est difficile de créer un total de toutes les ventes combinées de 2018 et 2019. **L'objectif est d’utiliser ces données dans Power BI avec trois colonnes : Month, Year et SalesAmount.**
        - Importation dans Power BI 

        ![](https://learn.microsoft.com/fr-fr/training/modules/clean-data-power-bi/media/02-original-data-ss.png)

        - *Ensuite, on renomme la première colonne en* ***Month***. *Cette colonne a été libellée de façon erronée, car cet en-tête dans Excel était un libellé pour les colonnes 2018 et 2019*. 
        - *On met en surbrillance les colonnes 2018 et 2019, puis sélection de l’onglet ***Transformer*** *dans Power Query, puis sélectionnez* ***Dépivoter***.

        ![](https://learn.microsoft.com/fr-fr/training/modules/clean-data-power-bi/media/02-unpivot-ss.png)

        - On renomme la colonne Attribut en Year et la colonne Valeur en SalesAmount.

    - **NB : Le dépivotement simplifie ultérieurement le processus de création de mesures DAX sur les données. En effectuant ce processus,on a créé un moyen plus simple de segmenter les données avec les colonnes Year et Month.** 

7. **Pivoter les colonnes**
    - Si les données que l'on met en forme sont plates (c’est-à-dire si elles ont beaucoup de détails mais ne sont pas organisées ou regroupées de quelque façon que ce soit), l’absence de structure peut compliquer la capacité à identifier des modèles dans les données.
        - On peut utiliser la fonctionnalité **Pivoter la colonne** pour convertir les données plates en une **table** qui contient **une valeur d’agrégation pour chaque valeur unique dans une colonne**. 
            - Par exemple, On peut utiliser cette fonctionnalité pour faire des calculs récapitulatifs sur les données avec différentes fonctions mathématiques, comme  ***Count (Nombre total)***, ***Minimum***, ***Maximum***, ***Median (Médiane)***, ***Average (Moyenne)*** ou ***Sum (Somme)***.

            ![](https://learn.microsoft.com/fr-fr/training/modules/clean-data-power-bi/media/02-pivot-column-feature-display-data-ssm.png) 

        - Onglet **Transformer** => **Transformer** => **Pivoter les colonnes**

        ![](https://learn.microsoft.com/fr-fr/training/modules/clean-data-power-bi/media/02-pivot-column-ssm.png)

        - Dans la fenêtre Pivoter la colonne qui s’affiche, sélection d'une colonne dans la liste **Colonne de valeurs**, par exemple Subcategory name. on développe les options avancées et sélectionne une option dans la liste  **Fonction de la valeur agrégée**, comme  **Nombre (Tout)**, puis **OK**. 

        ![](https://learn.microsoft.com/fr-fr/training/modules/clean-data-power-bi/media/02-aggregate-value-function-ssm.png)

#### Simplification de la structure des données
1. **Renommer une requete**
    - C’est une bonne pratique de changer les noms de requête inhabituels ou qui n’aident pas par des noms qui sont plus évidents ou qui sont plus familiers à l’utilisateur.
    - Dans l'éditeur Power Query
        - Volet **Requetes**  à gauche des données => Selection de la requete à renommer => click bouton droit => **Renommer** => **Entrée**

        ![](https://learn.microsoft.com/fr-fr/training/modules/clean-data-power-bi/media/03-rename-query-ssm.png)

2. **Remplacement des valeurs**
    - Selection de la colonne contenant la valeur à remplacer => Onglet **Transformer** => **Remplacer les valeurs** 
        - Dans la zone **Valeur à rechercher** la valeur à remplacer, dans la zone **Remplacer par** la valeur correct puis **OK**

        ![](https://learn.microsoft.com/fr-fr/training/modules/clean-data-power-bi/media/03-replace-value-ssm.png)

        ![](https://learn.microsoft.com/fr-fr/training/modules/clean-data-power-bi/media/03-value-find-ssm.png)

3. **Remplacement des valeur Null**
    - Il est possible de constater que les sources de données contiennent des valeurs **Null**. *Ex:le montant des frais de transport sur une commande client peut avoir une valeur Null s’il est synonyme de zéro.* Si la valeur reste Null, les ***moyennes ne seront pas calculées correctement***. Une solution serait de ***remplacer les valeurs Null par zéro***, ce qui produira une moyenne des frais de transport plus **précise**.

    ![](https://learn.microsoft.com/fr-fr/training/modules/clean-data-power-bi/media/03-replace-null-zero-ss.png)

4. **Suppression des doublons**
    - Il est possible de supprimer les doublons des colonnes pour ne conserver que les noms uniques dans une colonne sélectionnée en utilisant la fonctionnalité **Supprimer les doublons** de Power Query. 
    - Selection de la colonne => click droit sur l'entete de la colonne => **Supprimer les doublons**
    - *Il peut être judicieux de copier la table avant de supprimer les doublons. L’option Copier se trouve en haut du menu contextuel, comme illustré dans la capture d’écran suivante. Copier la table avant de supprimer les doublons permet de comparer les tables et d’utiliser les deux tables si nécessaire.

    ![](https://learn.microsoft.com/fr-fr/training/modules/clean-data-power-bi/media/03-remove-duplicates-ssm.png)

5. **Bonne pratique pour nommer les tables, les colonnes et les valeurs**
    - Une bonne pratique est de donner aux tables, aux colonnes et aux mesures des termes métier descriptifs, et de remplacer les traits de soulignement (« _ ») par des espaces. Etre cohérent avec les abréviations, les préfixes et les mots comme « nombre » et « ID ». Des abréviations excessivement courtes peuvent entraîner de la confusion si elles ne sont pas utilisées couramment au sein de l’organisation. 

    - Lors du remplacement de valeurs, on essaye d'imaginer comment ces valeurs vont apparaître dans le rapport. Les valeurs trop longues peuvent être difficiles à lire et s’insérer dans un visuel. Les valeurs trop courtes peuvent être difficiles à interpréter. Éviter les acronymes dans les valeurs est également une bonne idée, à condition que le texte tienne sur le visuel.

#### Evaluation et changement des types de données des colonnes 
- Lorsuq'on importe une table depuis une source de données, Power BI Desktop démarre automatiquement l’analyse des 1 000 premières lignes (la valeur par défaut) et essaye de détecter le type des données dans les colonnes.
    - Il est plus probable d'obtenir des erreurs de type de données quand on travaille avec des **fichiers plats**, comme ***des fichiers de valeurs séparées par des virgules*** **(.CSV)** et ***des classeurs Excel*** **(.XLSX)**, car les données ont été entrées manuellement dans les feuilles de calcul et des erreurs ont pu être faites. À l’inverse, dans les bases de données, les types de données sont prédéfinis lors de la création des tables ou des vues.
- Une bonne pratique est d’évaluer les types de données des colonnes dans l’éditeur Power Query avant de charger les données dans un modèle de données Power BI. Si on détermine qu’un type de données est incorrect, on le changer. on peut également appliquer un format aux valeurs d’une colonne et changer la totalisation par défaut pour une colonne.

#### Implication des types de données incorrects 
- Si Power Bi ne detecte pas correctement les types de donnée, 
    - Impossible de créer certains calculs, de dériver des hiérarchies ou de créer des relations appropriées avec d’autres tables.
    - Impossibilité de créer une hiérarchie de dates, qui vous permettrait d’analyser vos données sur une base annuelle, mensuelle ou hebdomadaire ***(Si champs date incorrect)***

    ![](https://learn.microsoft.com/fr-fr/training/modules/clean-data-power-bi/media/04-additions-sales-date-options-ssm.png)

    - ***c’est une bonne pratique que d’utiliser une table de dates et de désactiver la date/heure automatique pour supprimer la hiérarchie générée automatiquement.***
    - [Voir doc Types de données généré automatiquement](https://learn.microsoft.com/fr-fr/training/modules/clean-data-power-bi/media/04-additions-sales-date-options-ssm.png)

#### Changement de types de données d'une colonne

[Voir Doc Types de données dans Power BI Desktop](https://learn.microsoft.com/fr-fr/power-bi/connect-data/desktop-data-types)

- Il est préférable de changer le type de données dans l’éditeur Power Query avant de charger les données.
1. **Changer le type de données d’une colonne dans l’éditeur Power Query**
    - Selection de la colonne => onglet **Transforme** => **Type de données** => selection du type correct dansla liste. 
    
    ![](https://learn.microsoft.com/fr-fr/training/modules/clean-data-power-bi/media/04-select-data-type-ssm.png)

    2. Selection de l'incone de type en regarde de l'entete de colonne => selection du type de donnée corect dans la liste. 

    ![](https://learn.microsoft.com/fr-fr/training/modules/clean-data-power-bi/media/04-select-data-type-from-list-ssm.png)

#### Combiner plusieurs tables en une seule table

[Voir Doc Mettre en forme et combiner les données](https://learn.microsoft.com/fr-fr/power-bi/connect-data/desktop-shape-and-combine-data)
- La possibilité de combiner des requêtes permet d’**ajouter** ou de **fusionner** différentes **tables** ou **requêtes**. 
- On peut combiner des tables en une seule table dans les circonstances telle que :
    - Lorqu'il existe trop de tables, ce qui rend difficile la navigation dans un modèle de données trop complexe.
    - Lorsque plusieurs tables ont un rôle similaire.
    - Lorsque une table n’a qu’une ou deux colonnes qui peuvent être transférées dans une autre table.
    - Lorsque l'on peut utiliser plusieurs colonnes de différentes tables dans une colonne personnalisée.
- Il est possible de combiner des tables de deux mieres differentes: 
    1. **Ajouter des requêtes**:
        - Lorsu'on ajoute des requêtes, on ajoute des lignes de données à une autre table ou une autre requête. Par exemple, on peut avoir deux tables, une avec 300 lignes et une autre avec 100 lignes, et quand on ajoute une requête à l’autre, on obtient 400 lignes.
    2. **Fusionner des requêtes**
        - Lorsu'on fusionne des requêtes, on ajoute des colonnes d’une table (ou d’une requête) dans une autre table ou requête. Pour fusionner deux tables, il faut avoir une colonne qui est la clé entre les deux tables.
- ***Avant de commencer à combiner des requêtes, il faut supprimer des tables les colonnes superflues dont on a pas besoin pour cette tâche. Pour effectuer cette tâche, mettre en forme chaque table de façon à ce qu’elle ne contiennent que des colonnes avec les informations pertinentes, puis renommer de façon à ce qu’elles aient toutes les mêmes en-têtes de colonnes:

![](https://learn.microsoft.com/fr-fr/training/modules/clean-data-power-bi/media/05-reformatting-appending-ss.png)

1. **Ajouter des requete**
    - Onglet **Acceuil** => Liste deroulante => **Ajouter des requetes**
        - **Ajouter les requetes comme etant nouvelles** : Le résultat de l’ajout aboutit à une nouvelle requête ou une nouvelle table,

        ![](https://learn.microsoft.com/fr-fr/training/modules/clean-data-power-bi/media/05-append-new-window-ss.png)

        ![](https://learn.microsoft.com/fr-fr/training/modules/clean-data-power-bi/media/05-appending-new-final-ss.png)

        - **Ajouter des requetes** : Ajoute les lignes d’une table existante dans une autre.

2. **Fusionner des requêtes**
    - Onglet **Acceuil** => selection dans le menu deroulant **Fusionner des requetes** ou **Fusionner les requetes comme nouvelles** :
        - Cette sélection ouvre une nouvelle fenêtre, où on peut choisir dans la liste déroulante les tables que l'on veut fusionner, puis sélectionner la colonne commune aux tables.

        ![](https://learn.microsoft.com/fr-fr/training/modules/clean-data-power-bi/media/05-merge-queries-new-ss.png)

    - Lorsque l'on fusionne des requêtes, on combine les données de plusieurs tables en une seule, sur la base d’une **colonne commune entre les tables**. Ce processus est similaire à la clause **JOIN dans SQL**.

    ![](https://learn.microsoft.com/fr-fr/training/modules/clean-data-power-bi/media/05-merging-tables-example-ss.png)

    - *** La colonne qui est partagée entre ces deux tables est  OrderID.**
    - Il est egalement possible de choisir comment joindre les deux tables, un processus qui est également similaire aux instructions **JOIN dans SQL**. Ces options de jointure incluent : 
        1. **Externe gauche** : Affiche toutes les lignes de la première table et seulement les lignes correspondantes de la seconde.
        2. **Externe entière** : Affiche toutes les lignes des deux tables.
        3. **Interne** : Affiche les lignes correspondantes entre les deux tables.

#### Profiler les données 

