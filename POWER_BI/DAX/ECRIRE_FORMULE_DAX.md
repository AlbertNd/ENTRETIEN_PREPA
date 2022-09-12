# Les formules dax (Data Analysis expression)

[Voir Doc](https://docs.microsoft.com/fr-fr/dax/)

- Il existe trois type de calcule à ajouter au model de donnée à l'aide des DAX. 
    1. **Tables calculées** 
        - Il est possible d'écrire une formule DAX pour ajouter une table calculée au model. 
        - La formule peut dupliquer ou transformer des données de modele existantes 
        - LA formule peut creer une serie de données pour produire une nouvelle table
        - ***NB : Les données de la table calculée augmentent la taille de stockage d u modele et peuvent prolonger le temps d'actualisation des données. Elle ne peuvent pas se connecter à des données externes; il faut utiliser Power Query pour accomplir la tache.***
        - Il sont utiles dans des scenarios tel que : 
            - ***Tables de dates*** 
                ```
                    Des tables de dates sont requises pour appliquer des filtres spéciaux ("Time intelligence").
                        - Les fonction Timing intelligence DAX ne fonctionnent que quand un table de date est configurée. 
                            - Si les données sources n'incluent pas de table date, il possible de creer une en tant que table calculée à l'aide des fonction DAX 
                ```
                - [Calendar](https://docs.microsoft.com/fr-fr/dax/calendar-function-dax) ou [Calendar-Auto](https://docs.microsoft.com/fr-fr/dax/calendarauto-function-dax)
            - ***Dimension de role actif***
                ```
                    Lorsque deux tables de modele ont plusieurs relations, cela peut etre du au fait que le modele a une dimension de role actif
                        - Ex : si une table Ventes comprend deux colonnes de date, OrderDateKey et ShipDateKey, les deux colonnes sont associées dans la table date:
                            - La table Date est décrite comme une dimension de role actif car elle peut jouer le role de date de commande ou de date d'expedition.
                ```
                - ![Ventes Date](https://docs.microsoft.com/fr-fr/training/modules/dax-power-bi-write-formulas/media/dax-sales-data-relationships-1-ss.png) 
                    - Les modeles Power BI **autorise uniquement une relation active entre les tables**
                        - Elle est sous la forme d'une ligne pleine. 
                        - Elle est utilisée par defaut pour propager les filtres (la Table Date vers la colonne OrderDateKey dans la Table Ventes). 
                            - Les relations restantes entre les deux tables sont inactives et presente en pointillés.
                        - ***Les relation inactive sont utilisées lorsqu'elle sont demande dans une formule caluclée à l'aide de la fonction DAX [USERELATIONSHIP](https://docs.microsoft.com/fr-fr/dax/userelationship-function-dax)***
                    - **Une meilleur conception demodele pourait avoir deux tables de date, chacune avec une relation active avec la table Ventes**
                        - De cette facon les utilisateurs peuvent filtrer par la date de comande ou date d'expedition ou les deux en meme temps. 
                - ***Une table calculée peut dupliquer les données de la table Date pour créer la table Ship Date***
                ![table](https://docs.microsoft.com/fr-fr/training/modules/dax-power-bi-write-formulas/media/dax-sales-data-relationships-2-ss.png)

            - ***Analyse de scénarios***
                ``` 
                - Les parametres de scenarios permettent aux utilisateurs de selectionner ou de filtrer les valeurs stockées dans la table calculée. 

                    - Les formules de mesure peuvent utiliser des valeurs selectionnées de maniere explicite ("un paramètre de scénario peut permettre à l’utilisateur du rapport de sélectionner un taux de change de devise hypothétique, et une mesure peut diviser les valeurs de chiffre d’affaires (dans une devise locale) par le taux sélectionné.")

                - En particulier, les tables calculées de scénario ne sont pas associées à d’autres tables de modèle, car elles ne sont pas utilisées pour propager des filtres. Pour cette raison, elles sont parfois appelées "tables déconnectées".
                ```
    2. **Colonnes calculées**
        - Il est possible d'ecrire une formule DAX pour ajouter une colonne calculée à une table du modele
            - *La formule est calculée pour chaque ligne de table et retourne une valeur unique*
        - **En cas d’ajout à une table de mode de stockage Importer**, la formule est évaluée quand le modèle de données est actualisé, et augmente la taille de stockage de votre modèle.
        - **En cas d’ajout à une table en mode de stockage DirectQuery**, la formule est évaluée par la base de données source sous-jacente lors de l’interrogation de la table.
        - Dans le volet Champs, les colonnes calculées sont améliorées avec une icône spéciale.
            - La colonne calculée Age de a table client 
            ![table](https://docs.microsoft.com/fr-fr/training/modules/dax-power-bi-write-formulas/media/dax-fields-pane-calculated-column-ss.png#lightbox)

    3. **Mesures** [Voir Doc](https://docs.microsoft.com/fr-fr/power-bi/transform-model/desktop-measures)
        - Il est possible d'ecrire une formule DAX pour ajouter une mesure à une colonne du modele. 
        - La formule s’intéresse à la réalisation d’un résumé sur les données du modèle
        - La formule retourne une valeur unique
        - ***Contrairement aux colonnes calculées, qui sont évaluées au moment de l’actualisation des données, les mesures sont évaluées au moment de la requête. Leurs résultats ne sont jamais stockés dans le modèle.***
        - Dans le volet Champs, les mesures sont affichées avec l’icône de calculatrice
            - Trois mesures dans la table Ventes sur les colonnes Cost, Profit, Revenu
            ![table](https://docs.microsoft.com/fr-fr/training/modules/dax-power-bi-write-formulas/media/dax-fields-pane-measures-ss.png#lightbox)
        - **NB:** Les mesures peuvent être décrites comme des mesures ***explicites***. les mesures explicites sont des calculs de modèle écrits dans DAX, et elles communément appelées plus simplement mesures.
        - **NB:** Les mesures ***implicites*** sont des colonnes qui peuvent être résumées par des visuels de manière simpliste, comme **Count, Sum, Minimum, Maximum, etc**. 
            - Elles sont indiquées par le symbole Sigma **( ∑ )**.
        - ***Il n’existe pas de concept de*** **mesure calculée** ***dans la modélisation tabulaire. Le mot calculé est utilisé pour décrire les*** **tables calculées** ***et les*** **colonnes calculées** ***,ce qui les distingue des tables et des colonnes provenant de Power Query. Power Query n’a pas de concept de mesure explicite.***

### Ecrire les formules DAX 

- Chaque type de calcul de modèle, de table calculée, de colonne calculée ou de mesure est défini par son **nom**, suivi du symbole égal **=**, suivi par une **formule DAX**
    `<Nom du calcul> = <Formule DAX>`
- **Les formules de stbales caluclée retourne un objet table** 
- **Les formules de colonne et de mesure cocluclées retournent une valeur unique** 
- Les vormules sont rassembler  à l'aide des éléménts suivants 
    - ***Fonctions DAX*** 
    - ***Opérateurs DAX***
    - ***Références aux objets de modele***
    - ***Valeur constntes, comme le nombre 24 ou le txte littéral "FY" (Abreviation pour année fiscale)*** 
    - ***Variables DAX***
    - ***Espace blanc*** 
1. **Les fonction DAX**
    - Les fonctions DAX ont des arguments qui autorisent le passage des variables. 
    - ***Dans une formule, les noms de fonction doivent etre suivis de parentheses. et entre les parenthèses,les variables sont passée***
        - Certenaines fonction ne prennent pas d'arguments.
2. **Opération DAX**
    - Les formules s'apuient sur des opérateurs qui effectuent des calculs arithmétiques, comparent des valeurs, utiliser des chaines ou des testes de condition
3. **References au objets de modele**
    - Les formules peuvent faire reference à trois types d'objets de modele: 
        1. ***Réfrérence des tables***
            - Lorsque l'on reference une table dans une formule, le nom de a table est placé **entre guillemets simpples**.
                - `Ship Date = Date`
                - Les guillemets peuvent etre omis lorsque : 
                    - Le nom de la table n'inclut pas d'espaces incorporés.
                    - Le nom de la table n'est pas un nom reservés qui est utilisé par DAX.
                        - `Arriva Airport = Airport`  
        2. ***Réfrérence des  colonnes***
            - Lorsuqe l'on reference une colonne dans une formule, le nom de la colonne doit etre palce dans **entre crochets** 
                -  Elle peut etre precedé de son nom de table ***(Recommendé)***
                    - `Revenu = SUM([ Ventes Montant])`
                    - `Revenu = SUM(Ventes[Ventes Montant])`
        3. ***Réfrérence des  mesures***
            - Lorsuque l'on refence une mesures dans une formule, le nom dela mesure doit etre placé **entre crochet**
                - `Profit = [Revenue] - [Cout]`
4. **Variable DAX**
    - Les formules peuvent declarer des variable DAX pour stocker les resultats
5. **Espace blanc**
    - Les caractere d'espace blanc sont : 
        - Espaces
        - Onglets
        - Retours chariot
    - [Outils d'aide pour le formatage DAX espace blanc ](http://www.daxformatter.com/)
    - ***Une formule ne peut pas faire référence à une hierarchie ou un niveau de hierarchie.***
        - Un niveau de hierarchie n'est basé que sur une colonne, la formule peut donc faire reference à la colonne d'un niveau de hierarchie.


