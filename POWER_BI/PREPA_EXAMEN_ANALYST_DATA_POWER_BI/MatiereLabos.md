# La matière abordée dans les labos Microsoft Power BI 

1. ## Préparation des données dans Power BI [(Voir Labo)](https://learn.microsoft.com/fr-fr/training/modules/get-data/lab-prepare)

    1. ***Enregistrer le fichier Power BI Desktop***
    2. ***Définir les options de Power BI Desktop***
        - Fichier => Options et paramètres => Options => dans le groupe fichier actif => chargement des données *(Les paramètres de Chargement des données pour le fichier actif permettent de définir des options qui déterminent les comportements par défaut lors de la modélisatio)* => Deselection des options de relations
    3. ***Obtenir des données de SQL Server***
        - Acceuil => zone Données => Selection SQL Server 
            - Zone Serveur => localhost => Utiliser mes informations d’identification actuelles.
        - Fenetre de navigation => selection des 6 tables 
        - Tranformer les données => éditeur Power Query 
    4.  ***Afficher un aperçu des requêtes SQL Server***
        - Bare d'etat => statistique de la table 
        - Derniere colonne contenant liens tbales et valeur *(colonnes représentent les relations avec d’autres tables de la base de données. Elles peuvent être utilisées pour joindre des tables ensemble.)*
        - Evaluation de la qualité, distribution, profilage des colonnes 
            - Affichage => zone apercus des données
    5. ***Obtenir des données d’un fichier CSV***
        - Ajout d'une nouvelle requête
            - Acceuil => zone nouvelle requete => Nouvelle source => Texte/CSV 
    6. ***Obtenir des données supplémentaires d’un fichier CSV***   

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
            - Fucion des colonnes : *LastName FirstName*
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
                5. DimProductSubcategory *(Qi est une table associée)*
            - Developement de la colonne *DimProductSubcategory* et garder les colonnes suivantes:
                - *EnglishProductSubcategoryName*
                - *DimProductCategory*
                - (NB : Utiliser le nom de la colonne d’origine comme préfixe)
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
                - *UnitPrice => *Unit Price* (incluez un espace)
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
            - Création d'une colonne *Date* derivée des colonnes **Year** et **MonthNumber**
                - Utilisation de la fonction : *Colonne à partir d'exemples*
            - Renommer la colonnes : *TargetMonth*
            - Suppression des colonnes
                - *Year* 
                - *MonthNumber*
            - Modification des types de colonnes: 
                - *Target* => *Nombre décimal fixe*
                - *TargetMonth* => *Date*
            - Les valeurs de la colonne *Target* multiple de 1000
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
            - Création d'une relation entre la table **Categorie** et la tables **Sales** 
                - Via la gestion des relation 
                - Cardinalité :  1 à *
                - Direction du filtre croisé : *à sens unique*
                - Relation active.
            - Création des relations:
                - La table **Region** et la table **Sales**
                - La table **Salesperson** et la table **Employeekey** 
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
                - Nom : *Product*
                - dans la hierarchie:
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
            - Création d'une categorie sur la colonne *Country-Region*
                - Nom : *Geography*
                - Contenu: 
                    - Country-Region 
                    - Etat-Province
                    - City
                    - Reseller                
            - Categorisation dees colonnes : 
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
        - Volet chammps 
            - les colonnes 
            - les hierarchies
            - champs visibles 
            - ornément d'icone et symbole 
            - info bulle
        - Hierarchie date automatique 
        - desactivation de Date/heure automatique 
            - fichier => Option et paramettre => options => fichier actif => chargement des données => time intelligence => date/heure automatique.
    4.  ***Création des mesures rapides***
        - Création d'une mesures rapides sur la table *Sales* 
            - Soustraction de : *Sommes des ventes* - *Cout*
            - Renommer la nouvelle colonne *Profit*
        - Création d'une mesure rapide sur la table *Slaes*
            - Division de : *Profit* / *Sales*
            - Renommer la nouvelle colonne *Profit Margin*
            - Attriubuer le format *Pourcentage*
        - Mettre les deux mesures dans le visuel