#  création de mesures à l’aide de DAX dans Power BI

- DAX (Data Analysis Expressions) est un langage de programmation utilisé dans Microsoft Power BI pour créer des colonnes calculées, des mesures et des tables personnalisées. Il s’agit d’une collection de fonctions, d’opérateurs et de constantes qui peuvent être utilisés dans une formule ou une expression pour calculer et retourner une ou plusieurs valeurs.
- Dans Power BI, il existe différentes techniques et fonctions de calcul permettant de créer des mesures ou des colonnes calculées. i lest possible d'obtenir le même résultat à l’aide de ces techniques.

#### Usage des colonnes calculées
- DAX permet de créer une colonne calculée qui n’existait pas à l’origine dans les sources en question.

![](https://learn.microsoft.com/fr-fr/training/modules/create-measures-dax-power-bi/media/02-table-visual-ss.png)

- On peut créer une colonne calculée qui multiplie le prix unitaire par la quantité
    - Elle produit une valeur pour chaque ligne, appelée **Total Price** (Prix total)
- Pour se faire => sélection du bouton points de **suspension (…)** sur la **table** dans la **liste Champs**, =>  sélection **Nouvelle colonne**.

![](https://learn.microsoft.com/fr-fr/training/modules/create-measures-dax-power-bi/media/02-new-column-ss.png)

- ***Une nouvelle formule DAX apparaît dans la barre de formule qui se trouve sous le ruban du haut.***

![](https://learn.microsoft.com/fr-fr/training/modules/create-measures-dax-power-bi/media/02-new-dax-column-ss.png)

- On peut remplacer le texte par defaut "Column = "
    - `Total Price = 'Sales OrderDetails'[Quantity] * 'Sales OrderDetails'[Unit Price]`
        - La valeur à gauche du signe égal correspond au nom de la colonne. 
        - Le texte situé à droite du signe égal est l’expression DAX. 
            - Cette expression DAX simple prend la valeur Quantity (Quantité) et la multiplie par la valeur Unit Price (Prix unitaire) pour chaque ligne. *Elle produira une valeur pour chacun des enregistrements de la table*. 
        - Si on fait glisser la nouvelle colonne de la liste Champs vers le visuel, il y aura les nouvelles valeurs.

        ![](https://learn.microsoft.com/fr-fr/training/modules/create-measures-dax-power-bi/media/02-new-total-price-ss.png)

        - **NB:** ***Les colonnes calculées sont matérialisées dans l’extension de fichier Power BI. pbix, ce qui signifie que, chaque fois qu’une colonne calculée est ajoutée, la taille de l’ensemble du fichier augmente. Un trop grand nombre de colonnes calculées ralentit les performances et fait atteindre plus rapidement la taille de fichier maximale Power BI.***

1. **Création d’une colonne personnalisée** 
    - Il existe trois façons de créer une colonne personnalisée dans Power BI :
        1. Créez la colonne dans la requête source lorsque vous récupérez les données, par exemple en ajoutant le calcul à une vue dans une base de données relationnelle.
        2. Créez la colonne personnalisée dans Power Query.
        3. Créez une colonne calculée à l’aide de DAX dans Power BI Desktop.
    1. **Creation dans la requete source**
        - Il est possible de créer une colonne calculée lorsque on extrayait les données de la source. 
            - Chaque source de données impose une technique spécifique pour effectuer cette action. 
            - Par exemple, l’extraction de données d’une source de données relationnelle à l’aide d’une vue écrite dans le langage SQL se présenterait ainsi :
            -   ```
                    CREATE VIEW OrdersWithTotalPrice
                    AS
                    SELECT unitprice, qty, unitprice * qty as TotalPrice 
                    FROM sales.salesorders
                ```
                - *Le langage SQL est un moyen efficace de créer une colonne, car c’est la source de données qui effectue les calculs. Dans Power BI, la colonne calculée apparaîtrait comme n’importe quelle autre colonne.*
    2. **Création de la colonne dans Power Query** 
        
        ![](https://learn.microsoft.com/fr-fr/training/modules/create-measures-dax-power-bi/media/02-custom-column-ss.png)

        - *La boîte de dialogue Colonne personnalisée utilise le langage M pour créer la nouvelle colonne.*

    3. **Cration d'une colonne à l'aide de DAX** 
        - Voir avant 

**NB: Lorsque on crée une colonne calculée à l’aide de DAX, on a pas besoin d’actualiser le jeu de données pour afficher la nouvelle colonne. Avec les autres méthodes, une actualisation serait nécessaire pour voir les modifications. Ce processus peut être long en présence d’un gros volume de données. Toutefois, ce problème n’est pas pertinent car, une fois créées, les colonnes sont rarement modifiées.**

**La colonne calculée DAX ne présente pas une aussi bonne compression que les autres méthodes. Les autres types de colonnes sont compressés, ce qui permet d’obtenir un fichier ".pbix" plus petit et des performances généralement plus rapides.**

**En règle générale, plus tôt la colonne est créée, mieux c’est. L’utilisation de DAX n’est pas considérée comme une pratique optimale pour les calculs si l’utilisation d’un autre mécanisme est possible.**

**Par ailleurs, l’une des techniques permettant d’éviter d’utiliser une colonne calculée consiste à avoir recours à l’une des fonctions X,** 
- comme SUMX, 
- COUNTX ou MINX. 

**Elles permettent de créer des mesures qui tiennent compte des données présentes dans chacune des lignes et calculent des totaux en fonction des totaux de la ligne.** 
**Ces fonctions sont appelées fonctions d’itérateur, car, bien qu’elles soient utilisées dans les mesures, elles effectuent une itération sur les différentes lignes pour réaliser leurs calculs.** 

***Une fonction X est plus performante et utilise moins d’espace disque qu’une colonne calculée.*** 

[Pour plus d'informations sur les fonctions X](https://learn.microsoft.com/fr-fr/dax/sumx-function-dax) 

#### Usage des mesures

- Les colonnes calculées sont utiles, mais elles imposent de travailler ligne par ligne. D’autres situations peuvent réclamer une méthode plus simple. 
    - *Supposons par exemple que l'on souhaite une agrégation qui s’applique à l’ensemble du jeu de données pour obtenir le total des ventes de toutes les lignes. On veut également découper les données selon d’autres critères, comme le total des ventes par année, par employé ou par produit.*
        - Pour accomplir ces tâches, Il faut utiliser **une mesure**. 
- **Il est possible d’élaborer une mesure sans écrire de formule DAX. Power BI l’écrit automatiquement lorsqu'on crée une mesure rapide.**

1. **Création d’une mesure rapide**

[Voir doc Calculs courants à l’aide des mesures rapides.](https://learn.microsoft.com/fr-fr/power-bi/transform-model/desktop-quick-measures)

- click droit ou sélection du bouton points de suspension (…) à côté d’un élément dans le volet Champs, puis sélection de **Nouvelle mesure rapide** dans le menu qui s’affiche. L’écran Mesures rapides s’affiche.

![](https://learn.microsoft.com/fr-fr/training/modules/create-measures-dax-power-bi/media/02-quick-measure-ssm.png)

- Dans la fenêtre Mesures rapides, on peut sélectionner le calcul que l'on souhaite et les champs sur lesquels il sera réalisé, par exemple une colonne. Power BI crée automatiquement la mesure DAX et affiche la formule DAX. 

2. **Création d’une mesure**
- click droit ou sélection du bouton points de suspension (…) à côté d’un élément dans le volet Champs, puis sélection de **Nouvelle mesure** dans le menu qui s’affiche. L’écran Mesures rapides s’affiche.

![](https://learn.microsoft.com/fr-fr/training/modules/create-measures-dax-power-bi/media/02-new-measure-ss.png)

- On peut replacer le texte mesure par :
    - `Total Sales = sum('Sales OrderDetails'[Total Price])`
    - La nouvelle mesure apparaît maintenant dans la liste Champs.

    ![](https://learn.microsoft.com/fr-fr/training/modules/create-measures-dax-power-bi/media/02-new-measure-fields-ss.png)

3. **Différences entre une colonne calculée et une mesure** 
- La différence fondamentale entre une colonne calculée et une mesure est que la première crée une valeur pour chacune des lignes d’une table, Par exemple, si la table contient 1 000 lignes. 
    - la colonne calculée comportera 1 000 valeurs. 
        - Les valeurs des colonnes calculées sont stockées dans le fichier .pbix Power BI. Chaque colonne calculée augmente l’espace utilisé dans ce fichier, et éventuellement le temps d’actualisation.
    - Les mesures sont calculées à la demande. 
        - Power BI calcule la valeur lorsque l’utilisateur le réclame. Lorsque on fait glisser la mesure Total Sales (Total des ventes) sur le rapport, Power BI a calculé le total et affiché le visuel. Les mesures n’augmentent pas l’espace disque global du fichier .pbix Power BI.
        - Les mesures sont calculées en fonction des filtres appliqués par l’utilisateur du rapport, qui se combinent pour donner le contexte de filtre.

#### Presentation du contxte 
- Les trois visuels suivants utilisent exactement la même mesure DAX : Total Sales (Total des ventes).

![](https://learn.microsoft.com/fr-fr/training/modules/create-measures-dax-power-bi/media/02-total-sales-visuals-ss.png)

- Bien qu’ils utilisent tous la même mesure DAX et, par conséquent, la même formule DAX, les visuels produisent des résultats différents.
    - le premier affiche la mesure Total Sales (Total des ventes) pour l’ensemble du jeu de données, soit 1,35 million de dollars USD.
    - le deuxième visuel, le total des ventes est décomposé année par année, par exemple, 0,23 million de dollars USD en 2014. 
    - Le troisième visuel ventile le total des ventes selon l’ID de produit.

- *Avec Power BI, une mesure peut être utilisée dans ces visuels de différentes façons même si elle n’a été définie qu’une seule fois. Chacun des totaux est exact et est obtenu rapidement. C’est le contexte d’utilisation de la mesure DAX qui permet de les calculer avec précision.
Les interactions entre les visuels modifient également le mode de calcul de la mesure DAX. Par exemple, si on sélectionne le deuxième visuel, puis 2015, les résultats s’affichent ainsi:*

![](https://learn.microsoft.com/fr-fr/training/modules/create-measures-dax-power-bi/media/02-filter-context-change-ss.png)

- *Le fait de sélectionner 2015 dans le deuxième visuel a pour effet de modifier le contexte de filtre de la mesure DAX. Le premier visuel correspond donc aux ventes de l’année 2015 : 0,66 million de dollars USD. Par ailleurs, le total des ventes est maintenant décomposé par ID de produit, mais seuls les résultats de l’année 2015 s’affichent. Ces calculs ont été rapidement modifiés en mémoire et ont affiché les résultats de manière très interactive pour l’utilisateur.*

- *La définition de la mesure DAX n’a pas changé ; il s’agit toujours de la mesure d’origine: *
    - `Total Sales = sum('Sales OrderDetails'[Total Price])`

**NB: Ce scénario est un moyen simple d’expliquer le fonctionnement du contexte avec DAX. De nombreux autres facteurs influent sur la manière dont les formules DAX sont évaluées. Les segments et les filtres de page, entre autres, peuvent avoir une incidence sur le calcul et l’affichage d’une formule DAX.** 

#### Usage de la fonction CALCULATE
- La fonction CALCULATE est une méthode de création d’une mesure DAX qui remplacera certaines parties du contexte utilisées pour exprimer le résultat.
    - Par exemple, une mesure qui calcule toujours le total des ventes pour 2015, quelle que soit l’année sélectionnée dans les autres visuels de Power BI, se présente ainsi :
        - `Total Sales for 2015 = CALCULATE(SUM('Sales OrderDetails'[Total Price]), YEAR('Sales OrderDetails'[orderdate]) = 2015)`
    - Lorsqu'on utilise la fonction CALCULATE pour remplacer le contexte, il est utile de donner à la mesure un nom décrivant précisément le remplacement. Dans cet exemple, CALCULATE agrège la colonne Total Price (Prix total), comme dans la mesure précédente. Toutefois, au lieu de s’appliquer à l’ensemble du jeu de données tout en suivant les instructions du contexte de filtre, elle remplace le contexte de filtre par l’année 2015. Quelle que soit l’année sélectionnée en tant que filtre pour d’autres rapports, on obtient toujours le total pour 2015 à l’aide de cette mesure. Tous les autres filtres s’appliquent toujours. 
    - Lorsque les deux mesures sont ajoutées au visuel précédent, elles ressemblent à la capture d’écran suivante.

    ![](https://learn.microsoft.com/fr-fr/training/modules/create-measures-dax-power-bi/media/02-two-measures-ss.png)

    - Comme le montre la capture d’écran précédente, Total Sales (Total des ventes) vaut toujours 1,35 millions de dollars USD, contre 0,66 million de dollars USD pour 2015 Total Sales (Total des ventes totales 2015).

    - Si on ajoute l’autre visuel dans le rapport et qu'on sélectionne 2015, les résultats sont les suivants. Si on sélectionne 2016, le Total des ventes pour 2015 restera à 0,66 millions USD.

    ![](https://learn.microsoft.com/fr-fr/training/modules/create-measures-dax-power-bi/media/02-two-visuals-with-calculate-ss.png)

    - *Comme on peut le constater, les deux mesures sont désormais égales. Si on filtre selon d’autres critères, notamment la région, l’employé ou le produit, le contexte de filtre sera toujours appliqué aux deux mesures. Seul le filtre Year (Année) ne s’applique pas à cette mesure.*

#### Utilisation efficace des relations
- Il existe une autre fonction DAX permettant de remplacer le comportement par défaut : **USERELATIONSHIP**

![](https://learn.microsoft.com/fr-fr/training/modules/create-measures-dax-power-bi/media/02-manage-relationships-ss.png)

- Une relation établie entre les colonnes  **Date** et **OrderDate (DateCommande)**, comme l’indique la ligne en surbrillance reliant les deux. 
    - La ligne pleine entre les deux tables indique qu’il s’agit de la relation active, ce qui signifie que, par défaut, tous les segments de la table de dates où s’affichent les mesures des données Sales (Ventes) suivront la colonne OrderDate (DateCommande). 
    - La ligne en pointillés, donc inactive, entre les colonnes Date et ShipDate. Cette relation ne sera jamais utilisée, à moins d’être déclarée explicitement dans une mesure. 
- L’objectif est de créer le rapport suivant, comportant deux visuels :  Sales by Ship Date (Ventes par date d’expédition) et  Sales by Order Date (Ventes par date de commande).

![](https://learn.microsoft.com/fr-fr/training/modules/create-measures-dax-power-bi/media/02-two-visuals-with-use-relationship-ssm.png)

- ***Ces visuels affichent les ventes au fil du temps, le premier par date de commande et le second par date d'expédition. Bien qu'il s'agisse de dates dans les deux cas, le point de données associé est différent, ce qui permet d'obtenir les deux ensembles de données sur le même visuel.***

- Pour créer cette mesure pour Ventes par date d’expédition, il faut utiliser la fonction **DAX USERELATIONSHIP()**. 
    - Cette fonction permet d’indiquer une relation à utiliser dans un calcul, et ce, sans remplacer les relations existantes. Il s’agit d’une fonctionnalité intéressante, car elle permet aux développeurs d’effectuer des calculs supplémentaires sur les relations inactives en remplaçant la relation active par défaut entre deux tables dans une expression DAX,
    - `Sales by Ship Date = CALCULATE(Sum(Sales[TotalPrice]), USERELATIONSHIP(Sales[ShipDate],'Calendar'[Date]))`

#### Création de mesures semi-additives





