# La matière abordée dans les labos Microsoft Power BI 

1. ## Préparation des données dans Power BI [(Voir Labo)](https://learn.microsoft.com/fr-fr/training/modules/get-data/lab-prepare)

    1. ***Accès à l'espace d'enregistrement***
        - Enregistre sous *Sales Analysis* Dans **D:\PL300\MySolution**
    2. ***Définir les options de telechargement***
        - Desactivation des relations 
    3. ***Chargement des donnée SQL***
        - Serveur => localhost 
        - Dans AventureWorksDW2020
            - Chargement des 6 tables 
                1. DimEmployee
                2. DimEmployeeSalesTerritory
                3. DimProduct
                4. DimReseller
                5. DimSalesTerritory
                6. FactResellerSales 
    4.  ***Analyse et interpretation des metadata***
        - *Qualité des colonnes*
            - Relever des pourcentages des valeurs (**Valide**, **Error**, **Empty**) pour cahque colonne et trouver une explication.
                - Colonne: 
                    - *Position*
        - *Distribution des colonnes*
            - Relever des valeur **distinct** et valeur **unique** Pour chaque colonne et trouver une interpretation (cardinalité .....)
            -   ``` 
                    - Nombre de valeurs distinctes : nombre total de valeurs différentes trouvées dans une colonne donnée.

                    - Nombre de valeurs uniques : nombre total de valeurs qui n’apparaissent qu’une seule fois dans une colonne donnée.
                        1. Une colonne dont la plage contient de nombreuses valeurs répétées(le nombre de valeurs distinctes est faible) présente un niveau de cardinalité bas. 
                        2. Une colonne dont la plage contient de nombreuses valeurs uniques (le nombre de valeurs uniques est élevé) présente un niveau de cardinalité élevé.

                    - NB: Une cardinalité plus faible donnant des performances plus optimisées, vous devrez peut-être réduire le nombre de colonnes présentant un niveau de cardinalité élevé dans votre jeu de données.

                        3. Quand les nombres de valeurs distinctes et uniques sont identiques, cela signifie que la colonne contient que des valeurs uniques.
                ```
        - *Profile des colonnes*
            - Releve les problemes de qualité des données (voir si anomalie dans les graphes)
    5. ***Charger les données d'un fichier TEXT/CSV***
        - Fichier **ResellerSalesTargets.csv** dans **D:\PL300\Resources**
    6. ***Charger les données d'un autre fichier TEXT/CSV***
        - Fichier **D:\PL300\Resources\ColorFormats.csv**   

2. ## Nettoyer, transformer et charger des données dans Power BI [(Voir labo)](https://learn.microsoft.com/fr-fr/training/modules/clean-data-power-bi/8-lab)
    1. **Chargement des données** 
        - Accès au fichier **Sales Analysis** dans **D:\PL300\Labs\02-load-data-with-power-query-in-power-bi-desktop\Starter.** 
    2. **Configuration des requetes** 
        1. ***DimEmployee***
            - Renomer la requete : *Salesperson*
            - Trie de la colonne SalesPersonFlag : *True*
            - Choisir les 6 colonnes :
                1. EmployeeKey
                2. EmployeeNationalIDAlternateKey
                3. FirstName
                4. LastName
                5. Title
                6. EmailAddress
            - Fusion des colonnes : *LastName FirstName*
                - Renommer la nouvelle colonne *Salesperson*
            - Renomer les colonnes:
                - *EmployeeNationalIDAlternateKey =>  EmployeeID*
                - *EmailAddress => UPN*
            - Confirmation : 5 colonne 18 lignes 
        2. ***DimEmployeeSalesTerritory***
            - Renommer la requete : *SalespersonRegion*
            - Suppression des deux dernieres colonnes
                - *DimEmployee*
                - *DimSalesTerritory*
            - Confirmation : 2 colonne 39 lignes 
        3. ***DimProduct***
            - Renommer la requete: *Product*
            - Filtrer la colonne FinishedGoodsFlag : *True*
            - Choix des 5 colonnes et supression du reste:
                1. ProductKey
                2. EnglishProductName
                3. StandardCost
                4. Color
                5. DimProductSubcategory *(Qui est une table associée)*
            - Developement de la colonne *DimProductSubcategory* et garder les colonnes suivantes:
                - *EnglishProductSubcategoryName*
                - *DimProductCategory*
                - (NB : Ne pas utiliser le nom de la colonne d’origine comme préfixe)
                    - Expliquer à quoi sert la fonction
            - Developement de la colonne *DimProductCategory* et introduire la colonne suivante: 
                - *EnglishProductCategoryName* 
            - Renommer les colonnes: 
                - *EnglishProductName* => *Product*
                - *StandardCost => *Standard Cost* (incluez un espace
                - *EnglishProductSubcategoryName* => *Subcategory*
                - *EnglishProductCategoryName* => *Category*
             - Confirmation : 6 colonne 397 lignes 
        4. **DimReseller**
            - Renommer la requete : *Reseller* 
            - Choix de 4 colonnes et supression du reste 
                1. ResellerKey
                2. BusinessType
                3. ResellerName
                4. DimGeography
            - Developpement de la colonne *DimGeography* et inclure les 3 colonne suivantes: 
                - City
                - StateProvinceName
                - EnglishCountryRegionName
            - Correction elements dans la colonne *Business Type* 
            - Renommer les colonnes:
                - *BusinessType* => *Business Type* (incluez un espace)
                - *ResellerName* => *Reseller*
                - *StateProvinceName* => *State-Province*
                - *EnglishCountryRegionName* => *Country-Region* 
            - Confirmation : 6 colonne 701 lignes 
        5. **DimSalesTerritory**
            - Renommer la requete : *Region* 
            - filtres sur la colonne *SalesTerritoryAlternateKey* : *suppresion de la valeur 0*
            - Supression des colonnes sauf: 
                1. SalesTerritoryKey
                2. SalesTerritoryRegion
                3. SalesTerritoryCountry
                4. SalesTerritoryGroup
            - Renommer les colonnes suivantes: 
                - *SalesTerritoryRegion* => *Region*
                - *SalesTerritoryCountry* => *Country*
                - *SalesTerritoryGroup* => *Group* 
            - Confirmation : 4 colonne 10 lignes 
        6. **FactResellerSales**
            - Renemmer la requete : *Sales* 
            - Supression des colonnes sauf:
                1. SalesOrderNumber
                2. OrderDate
                3. ProductKey
                4. ResellerKey
                5. EmployeeKey
                6. SalesTerritoryKey
                7. OrderQuantity
                8. UnitPrice
                9. TotalProductCost
                10. SalesAmount
                11. DimProduct
            - Developpement de la colonne *DimProduct* inclure la colonne: 
                - *StandardCost*
            - Création de colonne personnalisée 
                - Nom : Caost 
                - contenu: *Si la valeur de **TotalProductCost** est manquante, elle met le produit de la valeur de **OrderQuantity** par la valeur de **StandardCost** et  sinon, elle met la valeur existante de **TotalProductCost**.*
                     - `if [TotalProductCost] = null then [OrderQuantity] * [StandardCost] else [TotalProductCost]`
            - Suppression des colonnes : 
                - *TotalProductCost*
                - *StandardCost* 
            - Renommer les colonnes 
                - *OrderQuantity* => *Quantity*
                - *UnitPrice* => *Unit Price* (incluez un espace)
                - *SalesAmount* => *Sales*
            - Modifier le type des colonnes:
                - *Quantity* : *Nombre entier*
                - *Unit Price* : *Nombre decimal fixe*
                - *Sales* : *Nombre decimal fixe*
                - *Coût* : *Nombre decimal fixe*
            - Confirmation : 10 colonne 999 lignes 
        7. **ResellerSalesTargets** 
            - Renommer la requete : *Targets* 
            - Depivoter les colonnes correspondant aux 12 Mois(M01-M12) 
            - Filtrer la colonne *valeur* : Suppression de "-"
            - Renommer les colonnes : 
                - *Attribut* => *MonthNumber* (pas d’espace entre les deux mots, il sera supprimé plus tard) 
                - *Valeur* => *Target*
            - Retirer la lettre *M* des mois
                - Changer les type de donnée en *Nombre entier*
            - Création d'une colonne *Date* derivée des colonnes **Year** et **MonthNumber**
                - Utilisation de la fonction : *Colonne à partir d'exemples*
                    - Date format *US* : 7/1/2017
            - Renommer la colonnes : *TargetMonth*
            - Suppression des colonnes
                - *Year* 
                - *MonthNumber*
            - Modification des types de colonnes: 
                - *Target* => *Nombre décimal fixe*
                - *TargetMonth* => *Date*
            - Les valeurs de la colonne *Target* multiple de 1000
                - Pas de création de nouvelle colonne, multiplier la colonne target !!!!
        8. **ColorFormats** 
            - Utiliser la première ligne pour les en-têtes.
            - Confirmation : 3 colonne 10 lignes 
    3. **Mettre à jour la requete product** 
        - Funsionner avec la requete *ColorFormats*
            - Color & color
        - Developpement de la colonne *ColorFormats* inclure les deux colonnes: 
            - Background Color Format 
            - Font Color Format
        - Confirmation : 8 colonne 397 lignes 
    4. **Mettre à jour la requête ColorFormats** 
        - Desactiver le chargement vers le rapport.
    5. **Vérification => fermer et appliquer**

3. ## Modéliser les données dans Power BI Desktop (partie 1) [(Voir labo)](https://learn.microsoft.com/fr-fr/training/modules/design-model-power-bi/8-lab)

    1. ***Créer des relations de modèle***
        1. Demarrage
            - Accès au fichier **Sales Analysis** dans **D:\DA100\Labs\03-configure-data-model-in-power-bi-desktop\Starter**
            - Enregistrer le fichier dans **D:\DA100\MySolution**
        2. Créer des relations de modèle
            - Création d'une relation entre la table **Product** et la tables **Sales** 
                - Via la gestion des relation 
                - Cardinalité :  1 à *
                - Direction du filtre croisé : *à sens unique*
                - Relation active.
            - Création des relations:
                - La table **Region** et la table **Sales**
                - La table **Salesperson** et la table **Sales** 
            - Les manoeuvre
                ```
                    - Dans Power BI Desktop => selection de l'icone Modele => 7 tables 
                    - Dans Power BI Desktop => selection de l'icone Rapport
                    - Creation d'une visuel Product|Categorie & Sales|Sales
                    - relation dela table Product et sales pour le visuel 
                        - Modelisation => relations => gere les relations => nouveau => Fenetre créer une relation => Connection des clef dans les deux tables.
                        - Relation un à plusiers 
                        - Direction du filtre croisé => sens unique 
                        - Rendre cette relation => active 
                ```
    2.  ***Configuration des tables***
        1. **Product**
            - Création d'une hierarchie sur la colonne *Category*
                - Nom : *Products*
                - dans la hierarchie:
                    - *Category*
                    - *Subcategory*
                    - *product*
            - Création d'un dossier d'affichage
                - Nom : Mise en forme
                - Contenu: 
                    - Format de couleur d'arriere plan
                    - Format de couleur de police 
                - Les manoeuvre 
                    ```
                        - Selection des colonnes souhaité => volet Popriétés => zone Dossier d'affichage => introduire mise en forme ( nom du dossier) 
                    ```
                - ***Pour terminer => **Appliquer les changements de niveau** ***  
        2. **Region**
            - Création d'une hiérarchie sur la colonne **Region**
                - Nom :*Regions*
                - Contenu: 
                    - Group
                    - Country ( la colonne)
                    - Région
            - Catégorisation de la colone *country* (pas celle de la hierarchie) dans la catéorie des **Country/region** *
                - Les manoeuvres
                    ```
                        - Volet propriété => Avancé => liste deroulante catégorie de données => Country/Region
                    ```
                
        3. **Reseller**
            - Création d'une hierarchie sur la colonne *resseller* 
                - Nom : *Revendeurs*
                - Contenu:
                    - Business Type
                    - Resseller
            - Création d'une hierarchie sur la colonne *Country-Region*
                - Nom : *Geography*
                - Contenu: 
                    - Country-Region 
                    - Etat-Province
                    - City
                    - Reseller                
            - Categorisation des colonnes : 
                - Country-Region dans la catégorie **Pays/Région**
                - State-Province dans la catégorie **Département ou province**
                - City dans la catégorie **Ville**

        4.  **Sales**
            - Description de la colonne *Cost* : *Based on standard cost*
            - Mise en forme des colonne:
                - Quantity : *Séparateur de milliers* => Oui
                - Unit Price: 
                    - *Nombre de décimales* => 2
                    - *Totaliser par* => *Moyenne*
                - Les manoeuvre
                    ```
                        - Volet propriété => section mise en forme:
                            - Separateur de miliers => Oui 
                            - Nombre deciaml
                        - Avancé 
                            - Totaliser par la moyenne 
                    ``` 
        5. **Mettre à jour en bloc les propriétés**
            - Passer la propriété **est masqué** sur **Active** 
                - Product | ProductKey
                - Region | SalesTerritoryKey
                - Reseller | ResellerKey
                - Sales | EmployeeKey
                - Sales | ProductKey
                - Sales | ResellerKey           
                - Sales | SalesOrderNumber
                - Sales | SalesTerritoryKey
                - Salesperson | EmployeeID
                - Salesperson | EmployeeKey
                - Salesperson | UPN
                - SalespersonRegion | EmployeeKey
                - SalespersonRegion | SalesTerritoryKey
                - Targets | EmployeeID
            - Definir la mise en former : *Nombre decimales* => *0* Pour :
                - Product | Standard Cost
                - Sales | Cost
                - Sales | Sales
    3.  ***Examiner l’interface du modèle***
        - Vue rapport 
        - Volet champs 
            - les colonnes 
            - les hierarchies
            - champs visibles 
            - ornément d'icone et symbole 
            - info bulle
        - Voir dans la colonne **Sales|OrderDate** et la colonne **Target|TargetMonth**
            - desactivation de Date/heure automatique *(Savoir expliquer pour il faut desactiver les date automatique : "l’année de la hiérarchie de dates qui est créée automatiquement commence le 1er janvier de l’année. alors que nous on souhaite que l'année commece en juin")*
                - `fichier => Option et paramettre => options => fichier actif => chargement des données => time intelligence => date/heure automatique.`
            - Noter que les hierarchie ne sont plus disponible.
    4.  ***Création des mesures rapides***
        - Création d'une mesures rapides sur la table *Sales* 
            - Soustraction de : *Sommes des ventes* - *Cout*
            - Renommer la nouvelle colonne *Profit*
        - Création d'une mesure rapide sur la table *Sales*
            - Division de : *Profit* / *Sales*
            - Renommer la nouvelle colonne *Profit Margin*
            - Attriubuer le format *Pourcentage*
        - Mettre les deux mesures dans le visuel

        ![](https://learn.microsoft.com/fr-fr/training/modules/design-model-power-bi/media/lab-19-ss.png)

4. ## Introduction à DAX dans Power BI Desktop [Voir Labo](https://learn.microsoft.com/fr-fr/training/modules/create-measures-dax-power-bi/6-lab)

- Accès aux fichier **Sales Analysis.pbiix** dans **D:\DA100\Labs\04-create-dax-calculations-in-power-bi-desktop\Starter** 

1. **Création des tables calculées** 
    1. ***La table Salesperson*** 
        - Nom : **Salesperson** 
            - La table doit etre une copie de la table *Salesperson (Performance)* 
                - *NB : elle ne copie pas les propriétés comme la visibilité, la mise en forme, etc.*    
        - Création de relation : 
            - *Salesperson | EmployeeKey* et *Sales | EmployeeKey*
            - Suppression de la relation inactive 
        - Masquage des colonnes : 
            - EmployeeID (IDEmployé)
            - EmployeeKey (CléEmployé)
            - UPN
        - Description des tables : 
            - *Salesperson (Performance)* => "Salesperson related to Region(s)"
            - *Salesperson* => "Salesperson related to Sales"
            -   ``` 
                    La table Salesperson (Vendeur) permet d’analyser les ventes effectuées par un
                    vendeur, et la table Salesperson (Performance), celles effectuées dans la ou
                    les régions de vente affectées au vendeur.
                ```
    2. ***La table Date*** 
        - Nom : *Date* 
        - Table a une colonne: 
            - Le mois de juin doit etre considéré comme le dernier mois de l'année.
            - Confirmation de : 1826 lignes.
        - Définition fonction ***CALENDARAUTO()***
            - *C'est une fonction que retoune une table avec une colonne composée de valeur date.*
            - *Elle accepte un seul argument, correspondant au dernier mois de l'année chois*
                - *si l'argumznt n'est pas precisé, le dernier mois est automatiquement 12*
            ```
               Le comportement « automatique » consiste à analyser toutes les colonnes de date du
               modèle de données pour trouver les valeurs de date les plus anciennes et les plus
               récentes qui sont stockées dans le modèle de données. 
               Une ligne est ensuite créée pour chaque date de cette plage, en étendant la plage
               dans les deux sens pour que les années de données stockées soient complètes. 
            ```
2. **Création des colonnes calculées**
    1. ***Colonnes Année*** 
        - Nom : *Année* 
        - A partir de la colonne *Date* de la table 
        - Format d'affichage : *FYANNEE* (Ex : FY2018)
        - Condition d'affichage:
            - Si le mois de l'année est plus grand que juin on rajoute un sur l'année
    2. ***Colonne Trimestre***
        - Nom : *Trimestre* 
        - A partir de la colonne *Date* de la table
        - Format d'affichage : *FYANNEE T1* (Ex : FY2018 T1)
        - Condition d'affichage:  
            - Si le mois est inferieur ou égale à 3 => T3
            - Si le mois est inferieur ou égale à 6 => T4
            - Si les mois est inferieur ou égale à 9 => T1 Sinon T2  
    3. ***Colonne Mois***
        - Nom : *Mois* 
        - A partir de la colonne *Date* 
        - Format d'affichage : *Mois Année* (Ex Juil.2017)
        - Création d'une nouvel page de rapport:
            - Contenu 
                - Visuel matriciel
                    - *Année*
                    - *Month*
        - Ajout de la colonne *MonthKey* à la table *Date*
            - Format d'affichage : *AnnéeMois* (Ex : 201707)
                - `MonthKey = (YEAR('Date'[Date]) * 100) + MONTH('Date'[Date])`
            - Faire le trie des *Mois* par la colonne *MonthKey*
        - Masque la colonne *MonthKey* 
    4. ***Creation d'une hierarchie sur la colonne Année:***
        - Nom : Fiscal 
        - Contenu: 
            - *Année*
            - *Trimestre*
            - *Mois*
    5. ***Creation de relation:*** 
        - Date | Date & Sales | OrderDate
        - Date | Date & Targets | TargetMonth 
    6. ***Masque les colonnes:*** 
        - Sales | OrderDate
        - Targets | TargetMonth 
    7. ***Marquage de la table Date*** 
        - Marque comme table de date
            - `Outils de table => Marquer comme table de date`
3. **Création des mesures**
    ***NB : Créer la mesure, et nom definir l'affichage dans les colonne "Moyenne, median, Min ..." fait qu'il ne soit pas possible de modifier la technique d’agrégation*** 
    1. ***Mesures simples***
        - Average Price
        - Median Price
        - Min Price 
        - Max Price 
        - Orders
            - Fonction *[DISTINCTCOUNT()](https://learn.microsoft.com/en-us/dax/distinctcount-function-dax)* : `DISTINCTCOUNT(<column>)`  
                - Permet de compte les nombre de valeur distinct
        - Order Lines 
            - Fonction *[COUNTROWS()](https://learn.microsoft.com/en-us/dax/countrows-function-dax)* : `COUNTROWS([<table>])` 
                - Permet de compter les lignes d'une table
        - Format à deux decimale pour la moyenne, la median, le minimum et le maximum
        - Création d'un dossier *Tarifs*
            - Contenu:
                - Average Price
                - Median Price
                - Min Price 
                - Max Price 
        - Format avec séparateur de miliers pour les ligne de commande et les commandes 
        - Création d'un dossier *Volumes*
            - Contenu:
                - Lignes de commandes
                - Commande
    2. ***Suppression du prix unitaire dans le visuel*** 
    3. ***Ajout dans le visuel***
        - Median Price (Prix médian)
        - Min Price (Prix minimal)
        - Max Price (Prix maximal)
        - Orders (Commandes)
        - Order Lines (Lignes de commande)
    
    ![](https://learn.microsoft.com/fr-fr/training/modules/create-measures-dax-power-bi/media/lab-6-35-ss.png)

4. **Création des mesures supplémentaires** 
    - Objectif : *Afficher la somme des montant des cibles que si il y a bien un vendeur dan sle filtre*
    - Sur la page 1 
        - Suppression de **Target** du visuel
            - Renomer la colonne 
                - *Targets* => *TargetAmount*
            - Création de la mesure d'affichage 
                - Fonction *[HASONEVALUE()](https://learn.microsoft.com/fr-fr/dax/hasonevalue-function-dax)*:
                    - Retourne TRUE quand il ne reste qu’une valeur distincte après filtrage du contexte pour columnName. Sinon, FALSE.
                    -   ```
                            Target =
                            IF( HASONEVALUE('Salesperson (Performance)'[Salesperson]),
                                SUM(Targets[TargetAmount])
                            )
                        ```
        - Mise en forme de la colonne *Target* : Decimal = 0 
        - Masque la colonne *TargetAmount* 
        - Ajouter la mesure *Target* dans le visuel
        - Création des mesures *Variance* et *Variance Margin* en respectant la manoeuvre precedente:
            - Variance *(Sommes des ventes - Cible)*
                - Format : Pourcentage à 2 decimales
            - Variance Margin *(Varince / Cible)*
        - Ajouter l'ensemble aux visuel 

        ![](https://learn.microsoft.com/fr-fr/training/modules/create-measures-dax-power-bi/media/lab-6-40-ss.png)

5. ## Mesures en DAX  et Time Intelligence [Voir labo](https://learn.microsoft.com/fr-fr/training/modules/create-measures-dax-power-bi/8-lab) 

- Accès au fichier **D:\DA100\Lab05B\starter.** 

1. **Création d'un visuel matrice**
    - Création d'une nouvelle page
    - Ajout du visuel matriciel 
    - Mettre la hiérarchie Region | Regions dans les champs visuel
    - Ajout du champs Sales |Sales
    - Mise à jour du visuel 
        - Propriéte *Disposition échélonnée* : Desactiver 
2. **Manipulation du contexte de filtre** 
    1. ***Création de la mesure "Sales All Region"***
        - Objectif : La mesure doit evaluer la somme des ventes pour **toutes les regions**. *(Elle va filtrer sur toute la table Region)*
            - La fonction *[CALCULATE()](https://learn.microsoft.com/en-us/dax/calculate-function-dax)* : `CALCULATE(<expression>[, <filter1> [, <filter2> [, …]]])`
                - Fonction qui permet de manipuler un contexte de filtre. 
                - Son premier argument est l'expressio ou la mesure
                - Les autre argumentes permettent la modificaton du contexte filtre.
            - La fonction *[REMOVEFILTERS()](https://learn.microsoft.com/en-us/dax/removefilters-function-dax)* :`REMOVEFILTERS([<table> | <column>[, <column>[, <column>[,…]]]])`
                - Fonction qui permet de supprimers les filtres actifs
                - Elle prend comme argument une table, une ou plusieurs colonnes, ou rien. 
        - `Sales All Region = CALCULATE(SUM(Sales[Sales]), REMOVEFILTERS(Region))`
        - Ajout de la mesure *Sales All Region* au visuel 
    2. ***Création de la mesure "Sales % All Region"***
        - Objectif : La mesure doit evaluer le pourcentage de la somme des ventes par region sur le total general .*(Elle va filtrer sur toute la table Region)* *On divise la somme des ventes sur la somme des ventes par region*
            - La fonction *[DEVIDE()](https://learn.microsoft.com/en-us/dax/divide-function-dax)* : `DIVIDE(<numerator>, <denominator> [,<alternateresult>])`
        - Mise en forme de la mesure : *Pourcentage à deux decimales*
        -   ```
                Sales % All Region =
                DIVIDE(
                SUM(Sales[Sales]),
                CALCULATE(
                        SUM(Sales[Sales]),
                        REMOVEFILTERS(Region)
                )
                )
            ``` 
    3. ***Creation de la mesure "Sales % Country"*** 
        - Objectif: la mesure doit evaluer le pourcentage de la somme des ventes **par region**. *(Elle va filtrer sur la colonne region de la table region)* 
            -   ```
                    Sales % Country =
                    DIVIDE(
                    SUM(Sales[Sales]),
                    CALCULATE(
                        SUM(Sales[Sales]),
                        REMOVEFILTERS(Region[Region])
                    )
                    )
                ```
            - Ajout de la mesure qu visuel 
    4. ***Création de la mesure "Sales % country"***
        - Objectif : Amelioration visuel de la mesure precedente *Sales % Country*. affiche que lorsque le la valeur existe dans le niveau de hiérarchie. *(Rajout d'une condition)*
            - Fonction *[ISINSCOPE()](https://learn.microsoft.com/en-us/dax/isinscope-function-dax): `ISINSCOPE(<columnName>)`
                - Elle retourne TRUE lorsque la colonne spécifier est le niveau dans les niveau de hiérarchie sinon elle retourne une veleur vide.
            -   ```
                    Sales % Country =
                    IF(
                        ISINSCOPE(Region[Region]),
                        DIVIDE(
                            SUM(Sales[Sales]),
                            CALCULATE(
                                SUM(Sales[Sales]),
                                REMOVEFILTERS(Region[Region]
                            )
                        ) 
                    )
                ```
    5. ***Création de la mesure "Sales % Groupe"*** 
        - Objectif: Evaluer le pourcentage de la somme des ventes par pays et par region
            -   ```
                    Sales % Group =
                    DIVIDE(
                        SUM(Sales[Sales]),
                        CALCULATE(
                            SUM(Sales[Sales]),
                            REMOVEFILTERS(
                                Region[Region],
                                Region[Country]
                            )
                        )
                    )
                ```
    6. ***Creation de la mesure "Sales % Groupe"***
        - Objectif : Ameliorer le visuel de la mesure precedente à l'aide d'une condition inhérentes à la fonction ISINSCOPE() et permettant de retuourner une valeur que si la region est comprise dans la portée
            -   ```
                    Sales % Group =
                    IF(
                        ISINSCOPE(Region[Region])
                            || ISINSCOPE(Region[Country]),
                        DIVIDE(
                            SUM(Sales[Sales]),
                            CALCULATE(
                                SUM(Sales[Sales]),
                                REMOVEFILTERS(
                                    Region[Region],
                                    Region[Country]
                                )
                            )
                        )
                    )
                ```
3. **Creation d'un dossier Ratio**
    - Contenu: Les 3 mesure de pourcentage. 
4. **Utiliser Time Intelligence**
    1. ***Créer une mesure de ventes cumulées annuelles jusqu'à ce jour***
        - Sur la page 2
        - Objectif : Ventes cumuléé 
        - Fonction *[TOTALYTD()](https://learn.microsoft.com/en-us/dax/totalytd-function-dax)*, Elle évalue la valeur cumulée de l'année de l' expression: `TOTALYTD(<expression>,<dates>[,<filter>][,<year_end_date>])`
            - Expresssion: Une expresion qui retourne une valeur scalaire. 
            - Date : Une colonne contenant des dates.
            - Filtre: Une expression qui spécifie un filtre à appliquer au contexte actuel.
            - Date de fin d'année: Une chaine littérale avec une date qui definit la date de fin d'année. la valeur par defaut est le 31 decembre.
        - `Sales YTD =  TOTALYTD(SUM(Sales[Sales]), 'Date'[Date], "6-30")`
        - Ajout des champs *Sales* et *Sales YTD* dansle visuel
    2. ***Créer une mesure de croissance en glissement annuel*** 
        - Création d'une mesure à la tables *Sales*
            - Nom : Sales YoY Growth
            - Declaration d'une variable permettant de calculer la somme de la colonne *Sales* et revenir en arriere de 12 mois à partir de chaque date dans le filtre.
                - Fonction *[PARALLELPERIOD()](https://learn.microsoft.com/en-us/dax/parallelperiod-function-dax)* Elle renvoie une table qui contient une colonne de dates qui représente une période parallèle aux dates dans la colonne de dates spécifiée, avec les dates décalées d'un certain nombre d'intervalles vers l'avant ou vers l'arrière dans le temps : `PARALLELPERIOD(<dates>,<number_of_intervals>,<interval>)`
                    - Date : la colonne qui contient les dates 
                    - Nombre d'interval : Un entier qui spécifie le nombre d'intervalles à ajouter ou à soustraire des dates. 
                    - intervalle: intervalle de décalage des dates 
                        - valeur : *year*,*quarter*,*month*
                    - Elle retourne une table contenant une seule colonne de valeurs de date.
            -   ```
                    Sales YoY Growth =
                    VAR SalesPriorYear =
                        CALCULATE(
                            SUM(Sales[Sales]),
                            PARALLELPERIOD(
                                'Date'[Date],
                                -12,
                            MONTH
                            )
                        )
                    RETURN
                        SalesPriorYear
                ```
        - Ajout de la mesure dans le visuel 

        ![](https://learn.microsoft.com/fr-fr/training/modules/create-measures-dax-power-bi/media/lab-8-13-ssm.png)

    3. ***Créer une mesure de croissance en glissement annuel***
        - Mise en forme de la mesure en pourcentage calculé
            -   ```
                    Sales YoY Growth =
                    VAR SalesPriorYear =
                        CALCULATE(
                            SUM(Sales[Sales]),
                            PARALLELPERIOD(
                            'Date'[Date],
                            -12,
                            MONTH
                            )
                    )
                    RETURN
                    DIVIDE(
                        (SUM(Sales[Sales]) - SalesPriorYear),
                        SalesPriorYear
                    )
                ```
        ![](https://learn.microsoft.com/fr-fr/training/modules/create-measures-dax-power-bi/media/lab-8-14-ssm.png)
    
    4. ***Creation d'un dossier Time Intelligence*** 
        - Contenu : 
            - Ventes cumulée 
            - Pourcentage de la croissance des ventes 

6. ## Création de rapport Power BI [Voir labo](https://learn.microsoft.com/fr-fr/training/modules/create-measures-dax-power-bi/8-lab-advanced) 

    1. **Activations des visuels de carte et de carte pleine dans power BI service**
    2. **Accès aux données**
        - ***D:\PL300\Labs\06-design-report-in-power-bi-desktop\Starter***
    3. **Conception de la premiere page dans Power Bi Desktop** 
        - Renommer la page: **Overview**
        - Insertion et positionnement du logo : **D:\PL300\Resources\AdventureWorksLogo.jpg**
        - Insertion des segments : 
            1. Date | Champ Année (pas le niveau Année de la hiérarchie).
                - Segment en **Liste deroulant** 
                - Redimension et positionnement du segment
            2. région | Champ Région (pas le niveau Région de la hiérarchie).
                - Segment en **Liste**
                - Redimension et positionnement du segment
        - Insertion graphique:
            - Graphique en courbes et en colonnes empilées.
            - Redimension et positionnement du segment
            - Champs graphique colonnes
                1. Rendez-vous | Mois ***(axe des X)***
                2. Ventes | Ventes ***(axe des Y)***
            - Champs graphique courbes 
                1.  Sales | Marge bénéficiaire ***(axe des y)***
        - Configuration du visuels des mois pour afficher tous les mois
            - Filtrer sur **FY2020** 
        - Insertion d'un graphique **Carte**
        - Redimension et positionnement du visuel
            - Champs visuel carte 
                1. Localisation : Région | Pays
                2. Légende : Produit | Catégorie
                3. Taille : Soldes | Ventes
        - Insertion d'un graphique 
            - Graphique en barre empilées
            - Redimension et positionnement du graphique 
            - Champs graphique 
                1. Axe : Produit | Catégorie
                2. Valeur : Ventes | Quantité
            - Formatage du graphque 
                - Couleur par defaut sur une couleur appropriée
                - Activation des étiquetes de données 
    4. **Conception de la deuxieme page**
        - Renommer la page : **Profit** 
        - Insertion segment
            1. région | Champ Région 
        - Activation de l'option **Selectionner tout** 
        - Redimension et positionnement du graphique 
        - Insertion visuel matriciel 
        - Redimension et positionnement du visuel 
        - Champs du visuel 
            1. Lignes : date | Hiérarchie fiscale
            2. Valeurs : 
                - Commandes (du dossier Comptes )
                - Ventes
                - Coût
                - Profit
                - Marge bénéficiaire
        - Definir un filtre sur page **NB :** ***Les champs ajoutés au volet Filtres peuvent obtenir le même résultat qu'un segment. La seule différence est qu'ils ne prennent pas de place sur la page du rapport. Une autre différence est qu'ils peuvent être configurés pour répondre à des exigences de filtrage plus sophistiquées.***
            - Produit | Catégorie
            - Produit | SousCatégorie
            - Produit | Produit
            - Produit | Couleur 
    5. **Conception de la troisieme page** 
        - Renommer : **Mes performances** 
        - Definir un filtre sur la page 
            - vendeur (Performance) | champ Vendeu
            -   - Selection **MIchel Blythe**
        - Insertion segment 
            - Date | champ Année
            - Liste deroulant 
            - Selection **FY2019**
        - Redimension et positionnement du visuel
        - Insertion visuel **Carte à plusieur lignes**
        - Champs du visuel 
            - Ventes | Ventes
            - Cibles | Cible
            - Cibles | Variance
            - Cibles | Marge de variance
        - Formatage du visuel 
            - Valeurs de légende : Texte 28 pt
            - Arriere plan : Couleur gris claire 
        - Insertion graphique à barre groupées
        - Redimension et positionnement du graphique
        - Champs du graphique 
            - Axe : Date | Mois
            - Valeur : Ventes | Ventes et objectifs | Cible
        - Insertion graphique cluster des colonne 
    6. **Publication du rapport**
    7. **Exploration du rapport** 
        - Mon espace de travail .
            - Rapport d'analyse des ventes
            - Le model des données 
        - Page presentation 
        - Selection de plusieur regions
        - Selection d'une colonne de mois (plusieurs mois )
        - Incone de filtre au dessus des visuel 
        - Icone de mise au point 
        - Les info-bull sur les segments 
        - Option du menu du visuel de la carte 
        - Page profit:
            - région a une sélection différente du trancheur de région sur la page Vue d'ensemble .
            - Volet filtre 
            - Hierarchie dans le visue matriciel 
        - Page Mes performances 
            - affichage en plein ecran 
            - Interagir avec la page en modifiant le segment et en effectuant un filtrage croisé de la page.

        
